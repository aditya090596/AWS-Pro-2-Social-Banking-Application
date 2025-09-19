# AWS-Project-1 Social-Banking-Application

This project is a full-stack banking application that allows users to register, log in, and access various services like account summary, currency conversion, movie booking, food ordering, and more.

The application is built on a 3-tier architecture:
Frontend: ReactJS with Material UI, hosted on Amazon S3.
Backend: Spring Boot microservice with JWT authentication, deployed on AWS Elastic Beanstalk.
Database: Amazon RDS (MySQL) for storing user details and other application data.

# Features
## User Registration & Login

New users can register with details such as name, email, city, phone number, and password.
Login is secured using JWT authentication.
Only registered users can access the application features.
Account Services: View Account Summary.
Secure and personalized access based on JWT tokens.
Currency Converter: A static tool integrated into the frontend for quick conversions.
Movie Booking: Book available movies directly from the application.
Food Ordering: Browse and place orders for available food items.
Logout
Secure session termination.

## Architecture

Architecture Flow
flowchart TD
    A[User - Browser] --> B[React Frontend - S3]
    B --> C[API Calls]
    C --> D[Spring Boot Backend - Elastic Beanstalk]
    D --> E[(MySQL - RDS)]
    D -->|JWT Authentication| A

## AWS Service Flow
graph LR
    User[End User] --> S3[Amazon S3 - React Frontend]
    S3 --> EB[Elastic Beanstalk - Spring Boot]
    EB --> RDS[(Amazon RDS - MySQL)]
    EB --> Auth[JWT Authentication]
    Auth --> User

## Deployment Steps
Backend (Spring Boot)
Build JAR:mvn clean install
Deploy JAR to Elastic Beanstalk using AWS Console or CLI.
Frontend (React)
Build frontend: npm run build
Upload build files to Amazon S3 bucket.
Enable static website hosting in S3.

## Database (MySQL RDS)
Create RDS MySQL instance.
Configure DB schema and user table.
Connect backend to RDS using environment variables.
## Tech Stack
Frontend: React, Material UI
Backend: Spring Boot (Java), JWT Authentication
Database: MySQL on Amazon RDS

## Hosting:
Frontend → Amazon S3
Backend → AWS Elastic Beanstalk
