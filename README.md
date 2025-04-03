# CSE 360 Help System

## Overview

The **CSE 360 Help System** is a role-based assistance application developed for the **CSE 360** course at Arizona State University. This system allows students, instructors, and admins to securely access and manage course materials. Each user has distinct permissions, ensuring that the system remains organized and efficient for everyone involved. The system features secure login, personalized learning resources, and an intuitive user interface.

## Features

- **Role-based Access Control (RBAC):** 
  - Admin, Instructor, and Student roles with specific permissions.
- **Secure Login System:** 
  - Users must authenticate themselves to access the platform.
- **Course Resource Management:** 
  - Admins and instructors can add, edit, or remove help articles.
  - Students can view and access learning materials based on their needs.
- **Personalized Learning:** 
  - Students can find materials relevant to their course topics, assignments, and exams.
  
## Technologies Used

- **JavaFX** for building the graphical user interface (GUI).
- **Java** for backend development, including logic implementation and data handling.
- **Role-based access control (RBAC)** to ensure secure and differentiated user access.

## Installation

1. Clone the repository to your local machine:
    ```bash
    git clone https://github.com/gayathrikota/CSE360-Help-System.git
    ```

2. Navigate into the project directory:
    ```bash
    cd CSE360-Help-System
    ```

3. Ensure that you have Java and JavaFX installed on your system. If not, follow the installation instructions for Java and JavaFX [here](https://openjfx.io/).

4. Compile and run the application using the following command:
    ```bash
    javac -d bin src/*.java
    java -cp bin Main
    ```

## Usage

1. **Login**: 
   - Upon running the program, users are prompted to log in with their username and password.
2. **For Students**: 
   - After successful login, students can view available help articles and resources.
3. **For Instructors**: 
   - Instructors have access to create, edit, and delete articles, along with viewing student interactions.
4. **For Admins**: 
   - Admins can manage users and ensure the system runs smoothly by monitoring usage and ensuring secure access.

## Project Structure

```plaintext
CSE360-Help-System/
├── src/
│   ├── Main.java
│   ├── User.java
│   ├── Article.java
│   ├── Admin.java
│   ├── Instructor.java
│   └── Student.java
├── bin/
├── README.md
└── .gitignore
