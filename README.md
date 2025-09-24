Campus Course & Records Manager (CCRM)

Project Overview The Campus Course & Records Manager (CCRM) is a console-based Java application designed to manage student records, courses, and enrollments for an educational institution. It demonstrates core Java SE principles, including a layered architecture, object-oriented design, and modern Java APIs like Streams and NIO.2 for file handling.

Implementation Strategy The application is built with a clean, layered architecture separating concerns into distinct packages: domain for data models, service for business logic, io for file operations, and cli for the user interface. It heavily utilizes Object-Oriented principles (Encapsulation, Inheritance, Abstraction, Polymorphism) and incorporates the Singleton and Builder design patterns for robustness. Modern Java features like the Streams API, NIO.2, and the Date/Time API are used for efficient and readable code.

Setting Up and Running the Project Follow these steps to compile and run the CCRM application from the command line.

Prerequisites Java Development Kit (JDK) version 11 or newer.

Step 1: Arrange the Folder Structure Create a root folder (e.g., CCRM_Project). Inside it, create a src directory. Replicate the package structure and place each .java file in its corresponding directory. For example, CliManager.java should be at src/edu/ccrm/cli/CliManager.java.

Step 2: Compile the Source Code Open a terminal, navigate to your root CCRM_Project folder, and execute the following command:

This command compiles all necessary files into a new 'out' directory.
javac -d out src/edu/ccrm/cli/CliManager.java

Step 3: Execute the Application Once compiled, run the application using this command from the same root directory:

The '-cp out' flag sets the classpath to our output directory.
The '-ea' flag is optional but recommended to enable assertions.
java -cp out -ea edu.ccrm.cli.CliManager 
<img width="639" height="272" alt="Screenshot 2025-09-24 145759" src="https://github.com/user-attachments/assets/a126acff-46b7-4de4-99ac-993f539343ff" />
<img width="1844" height="951" alt="Screenshot 2025-09-24 145818" src="https://github.com/user-attachments/assets/4aa1a8d7-eeee-4c64-a34b-856dc5c4dd35" />

