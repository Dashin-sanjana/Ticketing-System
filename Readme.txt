Ticket Simulation System


Overview


The Ticket Simulation System is a real time simulation of an event ticketing system especially for vendors releasing tickets and customers buying them, with emphasis on concurrency and multi threading. The proposed system takes a producer-consumer model in which vendors are the producers who put tickets into circulation while customers are consumers who purchase them.


This system consists of three components:


* Frontend (React): It also offers an interface for a user to configure and manipulate the simulation process.
* Backend (Spring Boot): Engines and manipulators with procedures linked to ticketing, bookings, and simulating synchronization.
* CLI: A terminal and interface for starting up and regulating the simulation when the users want no graphical user interface.


Requirements
* Java (11 or higher) for the backend
* Node.js (for React)
* MySQL for database integration (if configured)
* Maven (for backend dependencies)
Setup Instructions
Backend Setup (Spring Boot)
1. Direct to project:
cd ticket-simulation-backend
2. Install dependencies:
mvn clean install
3. Configure the database: Update application.properties file to match MySQL setup:
spring.datasource.url=jdbc:mysql://localhost:3306/ticket_simulation
spring.datasource.username=root
spring.datasource.password=your_password
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
spring.jpa.hibernate.ddl-auto=update
4. Run the backend:
mvn spring-boot:run
Frontend Setup (React)
1. Direct to project
cd ticket-simulation-frontend
2. Install dependencies:
npm install
3. Run the frontend:
npm start


Usage Instructions
Frontend
Start the Simulation:
In the main menu, we get to set the number of tickets that would be issued, the release rate of tickets, the ticket pick up rate, the maximum number of vendors that can be created, and the number of vendors.
Once you have entered these parameters click on the icon on the top right hand corner of the screen that says start simulation.
View Ticket Availability:
Ticket Display area depicts the number of tickets available in the system at any give time.
Control the Simulation:
The simulation can be stopped at any given time by use of the control panel.
View Logs:
This part ensures logging the text messages of vendors and customers which include ticket releases and bookings to mention but a few.
Simulation Summary:
The Simulation Summary of the page highlights the number of tickets that has gone through the simulation and the number of the tickets still in queue.


Backend
API Endpoints (Backend)
Start Simulation
* Endpoint: /api/tickets/start
* Method: POST
* Request Body:  
{
  "totalTickets": 100,
  "ticketReleaseRate": 5,
  "customerRetrievalRate": 3,
  "maxTicketCapacity": 50,
  "numberOfVendors": 2
}
Stop Simulation
* Endpoint:  /api/tickets/stop
* Method: POST
* Response: simulation stopped


* Get Summary
* Endpoint: /api/tickets/summary
* Method: POST
* Response: Summary of the simulation, such as the total tickets processed.
Get Logs
* Endpoint: /api/tickets/logs
* Method:  POST
* Response: Logs of the simulation, showing ticket releases and bookings.


CLI
* Start the CLI:
Run the CLI program with the following command:
java Main
Provide Configuration:
The program will solicit for configuration parameters like total tickets, release rate, retrieval rate, maximum capacity, and number of vendors.
Start Simulation:
After the configuration has been set, simulation will then commence and vendors will then be releasing tickets while the customers are purchasing them.
View Logs:
All the logs will be stored in a file which will be named simulation_output.txt.
View Summary:
All tickets processed, the program will start exiting and show a summary of the simulation and write it into the log file.