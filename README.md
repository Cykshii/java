# Campus Course & Records Manager (CCRM)

### Project Overview & How to Run

[cite_start]The Campus Course & Records Manager (CCRM) is a console-based Java application for an educational institute[cite: 4]. [cite_start]It is designed to manage students, courses, enrollments, and grades, and includes utilities for file import/export and data backup[cite: 5, 8, 9, 10]. [cite_start]This project demonstrates core Java principles, object-oriented programming, and modern Java APIs[cite: 12].

#### How to Run:
1.  **Prerequisites:** You must have **JDK 11** or a later version installed.
2.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/](https://github.com/)[your-username]/CCRM-Java-Project.git
    cd CCRM-Java-Project
    ```
3.  **Compile the Code:** Navigate to the `src` directory and use `javac` to compile the source files into a `bin` directory.
4.  **Run the Application:** From the project's root directory, execute the main class located in the `bin` folder.
    ```bash
    java -cp bin edu.ccrm.cli.Main
    ```
5.  [cite_start]**Run with Assertions Enabled:** To run the application with assertions for checking program invariants [cite: 89][cite_start], use the `-ea` (enable assertions) flag[cite: 137].
    ```bash
    java -ea -cp bin edu.ccrm.cli.Main
    ```
---

### Evolution of Java ☕

[cite_start]This section provides a brief timeline of Java's evolution as required[cite: 42].

* **JDK 1.0 (1996):** The first public release of Java, codenamed "Oak."
* **J2SE 5.0 (2004):** A major update that introduced generics, enums, annotations, and the `for-each` loop.
* [cite_start]**Java SE 8 (2014):** A landmark release that added lambda expressions, the Stream API, and a new Date and Time API[cite: 12].
* **Java SE 11 (2018):** The first Long-Term Support (LTS) release under the new six-month release cycle, introducing the `var` keyword for local variables.
* **Java SE 17 (2021):** A recent LTS release that brought sealed classes and enhanced pattern matching.

---

### Java ME vs. SE vs. EE

[cite_start]This project is built using **Java SE**[cite: 11]. [cite_start]Here is a breakdown of the different Java editions as required[cite: 43].

| Feature | Java Platform, Micro Edition (Java ME) | Java Platform, Standard Edition (Java SE) | Java Platform, Enterprise Edition (Java EE) |
| :--- | :--- | :--- | :--- |
| **Target** | Resource-constrained devices like mobile phones and embedded systems. | General-purpose desktop, server, and console applications. | Large-scale, distributed, and web-based enterprise applications. |
| **Core API** | A subset of the Java SE API, plus specific libraries for small devices. | The foundational API for Java, including collections, I/O, and networking. | Extends Java SE with APIs for web services, servlets, and persistence. |

---

### Java Architecture: JDK, JRE, & JVM

[cite_start]The Java platform is composed of several key components that work together[cite: 44].



* **JVM (Java Virtual Machine):** An abstract machine that provides a runtime environment to execute Java bytecode. It is what makes Java platform-independent.
* **JRE (Java Runtime Environment):** The software package that contains the JVM, class libraries, and other files necessary to *run* Java applications.
* **JDK (Java Development Kit):** The full development kit. It includes everything in the JRE, plus tools needed to *develop* Java applications, such as the compiler (`javac`) and debugger (`jdb`).

---

### Installation & Setup (Windows & Eclipse)

#### [cite_start]Java JDK Installation on Windows [cite: 45]
1.  Download the JDK installer from an official source (e.g., Oracle or OpenJDK).
2.  Run the installer and follow the setup wizard.
3.  Set the `JAVA_HOME` environment variable to the JDK installation path.
4.  Add the JDK's `bin` directory to the system `Path` variable.
5.  Verify the installation by opening Command Prompt and running `java -version`.
    

#### [cite_start]Eclipse Project Setup [cite: 46]
1.  Open Eclipse IDE and select `File` > `New` > `Java Project`.
2.  Give the project a name (e.g., `CCRM-Project`).
3.  Ensure the correct JRE is selected.
4.  Click `Finish`.
5.  [cite_start]Right-click the `src` folder to create packages (`edu.ccrm.domain`, `edu.ccrm.service`, etc.) as specified in the project structure[cite: 49].
    

---

### Mapping: Syllabus Topic → Project Implementation

[cite_start]This table maps the mandatory technical requirements to their implementation locations within the project's source code, as required[cite: 136].

| Syllabus Topic/Requirement | Location in Project (`src/` folder) |
| :--- | :--- |
| **OOP: Encapsulation** | [cite_start]`edu.ccrm.domain.Student` and `Course` classes use private fields with public getters/setters[cite: 59]. |
| **OOP: Inheritance & Abstraction** | [cite_start]`edu.ccrm.domain.Person` is an abstract class [cite: 61] [cite_start]extended by `Student` and `Instructor`[cite: 60]. |
| **OOP: Polymorphism** | [cite_start]The `TranscriptService` uses a `Person` reference to invoke overridden `toString()` methods on `Student` and `Instructor` objects[cite: 62]. |
| **Interfaces** | [cite_start]`edu.ccrm.io.Persistable` is an interface implemented by services that handle data import/export[cite: 69]. |
| **Enums with Constructors** | [cite_start]`edu.ccrm.domain.Semester` and `edu.ccrm.domain.Grade` are enums with custom fields and constructors[cite: 74, 27]. |
| **Lambdas & Functional Interfaces** | [cite_start]The `CourseService` class uses lambda expressions with the Stream API for filtering courses by instructor or department[cite: 72, 23]. |
| **Design Pattern: Singleton** | [cite_start]`edu.ccrm.config.AppConfig` is implemented as a Singleton to manage global application settings[cite: 80]. |
| **Design Pattern: Builder** | [cite_start]The `Course` class has a static nested `CourseBuilder` class for object construction[cite: 81]. |
| **Custom Exceptions** | [cite_start]`edu.ccrm.util.exceptions.DuplicateEnrollmentException` and `MaxCreditLimitExceededException` are custom checked exceptions[cite: 86, 87, 88]. |
| **File I/O (NIO.2)** | [cite_start]`edu.ccrm.io.BackupService` uses `Path` and `Files` for creating timestamped backup folders and copying files[cite: 91, 32]. |
| **I/O with Streams** | [cite_start]The `ImportExportService` uses `Files.lines()` (a Stream) to read and process lines from CSV files[cite: 92]. |
| **Recursion** | [cite_start]`edu.ccrm.util.FileUtils` contains a recursive method to calculate the total size of a backup directory[cite: 33]. |
| **Date/Time API** | [cite_start]The `Student` class uses `LocalDate` for date fields [cite: 18][cite_start], and backups use `LocalDateTime` for timestamps[cite: 94]. |
| **Nested Classes** | [cite_start]A static nested `CourseBuilder` is in `Course`; an inner class is used for a custom comparator in `StudentService`[cite: 67]. |
| **Assertions** | [cite_start]Assertions are used in service classes to check for invariants like non-null IDs or valid credit values[cite: 89]. |