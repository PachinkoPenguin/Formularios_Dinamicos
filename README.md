# 🎓 Dynamic Forms System with Abstract Method Pattern

> **Universidad XYZ - Software Design Patterns Course**  
> Student: Your Name  
> ID: Your Student ID  
> Professor: Prof. Maria Rodriguez  
> Submission Date: May 16, 2025

## 📝 Project Description

This project implements a dynamic form system that demonstrates the **Abstract Method** design pattern in a practical application. The system shows different forms to users based on their roles (Admin or Guest) and connects to Firebase Firestore for dynamic form configuration storage.

## 🏗️ Technical Overview

- **Backend**: Spring Boot application implementing the Abstract Method pattern
- **Frontend**: React application with dynamic form rendering
- **Database**: Firebase Firestore for storing form configurations
- **Pattern**: Abstract Method pattern for role-based form generation

## 🧩 Project Structure

- `/backend`: Spring Boot backend
- `/frontend`: React frontend

## 🔥 Setting Up Firebase

1. Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Set up a Firestore Database
3. Download your Firebase service account key and save it as `firebase-service-account.json` in the `backend/src/main/resources` directory
4. Set up the following Firestore database structure:

```
Collection: forms
   Document: admin
      formTitle: "Admin Management Form"
      formDescription: "Form for administrative tasks and project management"
      fields: [
         {
            id: "adminField1",
            label: "Project Name",
            type: "text",
            required: true,
            placeholder: "Enter project name"
         },
         {
            id: "adminField2",
            label: "Budget Allocation",
            type: "number",
            required: true,
            placeholder: "Enter budget"
         },
         {
            id: "adminField3",
            label: "Access Level",
            type: "select",
            required: true,
            options: ["High", "Medium", "Low"]
         }
      ]

   Document: guest
      formTitle: "Guest Registration Form"
      formDescription: "Please provide your information to proceed as a guest"
      fields: [
         {
            id: "guestField1",
            label: "Full Name",
            type: "text",
            required: true,
            placeholder: "Enter your full name"
         },
         {
            id: "guestField2",
            label: "Email",
            type: "email",
            required: true,
            placeholder: "Enter your email address"
         },
         {
            id: "guestField3",
            label: "Reason for Visit",
            type: "textarea",
            required: true,
            placeholder: "Please tell us why you're here today"
         }
      ]
```

## 🚀 Running the Project

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Run the Spring Boot application:
   ```bash
   ./mvnw spring-boot:run
   ```
   Or with Maven installed:
   ```bash
   mvn spring-boot:run
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm start
   ```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

## 🧠 Abstract Method Pattern Explanation

The project implements the **Abstract Method** pattern, which allows:

- **Separation of interface from implementation**: `FormGeneratorService` defines the interface, while concrete classes implement specific behaviors
- **Role-based customization**: Different form structures for different user roles
- **Dynamic form generation**: Forms can be configured without changing the code

### Pattern Implementation

1. `FormGeneratorService` - Abstract interface defining the contract for form generation
2. `AdminFormGeneratorService` and `GuestFormGeneratorService` - Concrete implementations for different user roles
3. `FormGeneratorFactory` - Factory class that selects the appropriate implementation based on the user role

## 📱 Application Demo

### Admin Form
The admin form provides fields for project management, including project name, budget allocation, and access level selection.

### Guest Form
The guest form collects basic information from visitors, including name, email, and reason for visit.

## ✨ Features

- Dynamic form generation based on user role
- Firebase integration for form configuration storage
- Responsive UI with Material UI components
- Form validation
- Abstract Method pattern implementation

## 🛠️ Technologies Used

- **Backend**: Java, Spring Boot
- **Frontend**: React, Material UI
- **Database**: Firebase Firestore
- **Build Tools**: Maven, npm

## 📚 Learning Outcomes

This project demonstrates my understanding of:
- Design patterns, specifically the Abstract Method pattern
- Full-stack development with Spring Boot and React
- API integration with Firebase
- Dynamic UI generation
- Software architecture principles

## 🔮 Future Improvements

- Add authentication with Firebase Auth
- Implement form submissions storage
- Add more user roles and form types
- Create a form builder interface for admins
