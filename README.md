                               HospitalManagementSystem
Hospital Management System  A console-based Hospital Management System built in Java with MySQL integration.   This project allows managing patients, doctors, and appointments through a simple command-line interface.
---

## **Table of Contents**
- [Features](#features)
- [Technologies](#technologies)
- [Database Setup](#database-setup)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Future Improvements](#future-improvements)
- [Author](#author)

---

## **Features**
- Add new patients
- View existing patients
- View available doctors
- Book appointments between patients and doctors
- Check doctor availability before booking
- User-friendly console interface

---

## **Technologies**
- **Java 20** – Object-oriented programming, JDBC  
- **MySQL** – Relational database management  
- **JDBC** – Java Database Connectivity to connect Java with MySQL  

---

## **Database Setup**
1. Install **MySQL** and create a database named `hospital`:

```sql
2.CREATE DATABASE hospital;

CREATE TABLE patients (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctors (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50),
    specialization VARCHAR(50)
);

CREATE TABLE appointments (
    id INT AUTO_INCREMENT PRIMARY KEY,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
3.Insert sample data into doctors table:

INSERT INTO doctors (name, specialization) VALUES
('Chandra Sekhar', 'Cardiologist'),
('Sudharani', 'NeuroSurgeon');

Hospital-Management-System/
├── src/
│   └── HospitalManagementSystem/
│       ├── HospitalManagementSystem.java
│       ├── Patient.java
│       └── Doctor.java
├── lib/
│   └── mysql-connector-j-8.0.xx.jar
├── bin/   (generated after compilation)
└── README.md
Getting Started

Clone the repository:

git clone https://github.com/yourusername/Hospital-Management-System.git


Add MySQL Connector JAR inside the lib/ folder.

Compile the Java files:

javac -d bin -cp "lib/*" src/HospitalManagementSystem/*.java


Run the project:

java -cp "bin;lib/*" HospitalManagementSystem.HospitalManagementSystem

Author

Solagam Chandra Sekhar

GitHub: github.com/Sekhariam

LinkedIn: www.linkedin.com/in/chandra-sekhar-iam
