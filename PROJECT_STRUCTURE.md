# Clinic Appointment Frontend - Project Structure Overview

## Overview

This document provides a comprehensive overview of the Clinic Appointment Frontend project structure, components, and functionality.

## Directory Structure

```
Clinic_Appointment_Front/
├── .git/                    # Git repository files
├── .gitignore              # Git ignore rules
├── README.md               # Project documentation
├── index.html              # Main HTML file
├── package.json            # Project dependencies and scripts
├── package-lock.json       # Locked dependency versions
├── vite.config.js          # Vite configuration
├── src/                    # Source code directory
│   ├── App.css             # Main application styles
│   ├── App.jsx             # Main application component
│   ├── index.css           # Global styles
│   ├── main.jsx            # Application entry point
│   ├── assets/             # Static assets (images, icons)
│   ├── components/         # Reusable UI components
│   ├── hooks/              # Custom React hooks
│   ├── pages/              # Page components (routes)
│   ├── services/           # API services and utilities
│   ├── styles/             # Component-specific styles
│   └── utils/              # Utility functions (if any)
└── node_modules/           # Installed dependencies (not in version control)
```

## Components Overview

### Authentication Components
- `LoginForm.jsx` - User login form
- `RegistrationForm.jsx` - User registration form
- `PasswordUpdateForm.jsx` - Password update form
- `PasswordInput.jsx` - Reusable password input with visibility toggle
- `ProtectedRoute.jsx` - Route protection with role-based access control

### Navigation Components
- `Header.jsx` - Application header with branding
- `Nav.jsx` - Main navigation menu

### User Management Components
- `UserProfile.jsx` - User profile display and editing

### Appointment Components
- `AppointmentForm.jsx` - Form for creating/editing appointments
- `AppointmentList.jsx` - List display of appointments

### Prescription Components
- `PrescriptionForm.jsx` - Form for creating prescriptions
- `PrescriptionList.jsx` - List display of prescriptions
- `MedicationDropdown.jsx` - Dropdown for medication selection

## Pages Overview

### Public Pages
- `Home.jsx` - Landing page
- `Login.jsx` - Login page
- `Register.jsx` - Registration page

### Protected Pages
- `Dashboard.jsx` - Patient dashboard
- `DoctorDashboard.jsx` - Doctor dashboard
- `Appointments.jsx` - Appointment listing page
- `NewAppointment.jsx` - New appointment creation page
- `EditAppointment.jsx` - Appointment editing page
- `Prescriptions.jsx` - Prescription listing page
- `CreatePrescription.jsx` - Prescription creation page
- `Profile.jsx` - User profile page
- `PasswordUpdate.jsx` - Password update page

## Services Overview

### API Service (`services/api.js`)
Centralized API client with the following endpoint groups:
- `authAPI` - Authentication endpoints (login, register, password update)
- `userAPI` - User management endpoints
- `appointmentAPI` - Appointment management endpoints
- `prescriptionAPI` - Prescription management endpoints
- `medicationAPI` - Medication management endpoints

### Authentication Service (`services/auth.js`)
Authentication utilities:
- `isAuthenticated()` - Check if user is authenticated
- `getCurrentUser()` - Get current user data
- `login()` - Handle user login
- `register()` - Handle user registration
- `logout()` - Handle user logout

### Utilities (`services/appointmentUtils.js`)
Helper functions for appointment-related operations.

### Mock Data (`services/mockData.js`)
Sample data for development and testing.

## Hooks Overview

### Custom API Hook (`hooks/useApi.js`)
Custom React hook for API calls with loading and error states.

## Styles Overview

Each component has a corresponding CSS file in the `styles/` directory:
- Component-specific styling
- Consistent naming conventions
- CSS modules for style isolation

## Routing

The application uses React Router for client-side routing with protected routes:
- Public routes: Home, Login, Register
- Protected routes: All other pages
- Role-based routes: Doctor dashboard

## Environment Variables

The application uses Vite's environment variable system:
- `VITE_API_BASE_URL` - API base URL (defaults to `http://localhost:5000/api`)

## Key Features

1. **Role-based Access Control**
   - Separate dashboards for patients and doctors
   - Protected routes based on authentication status
   - Role-specific UI elements

2. **Appointment Management**
   - Create, read, update, and delete appointments
   - View appointment lists
   - Edit existing appointments

3. **Prescription Management**
   - Create prescriptions linked to appointments
   - View prescription lists
   - Medication selection with dropdown

4. **User Management**
   - User registration and authentication
   - Profile management
   - Password updates

5. **Responsive Design**
   - Mobile-friendly interface
   - Consistent styling across components
   - Accessible UI components

## Technical Implementation Details

1. **State Management**
   - Component-level state with React hooks
   - Local storage for authentication tokens and user data

2. **API Integration**
   - Axios for HTTP requests
   - Request/response interceptors for authentication
   - Centralized error handling

3. **Form Handling**
   - Controlled components for form inputs
   - Validation and error messaging
   - Loading states during API calls

4. **Security**
   - JWT-based authentication
   - Protected routes with role checking
   - Automatic logout on authentication errors

This structure provides a solid foundation for a clinic appointment management system with clear separation of concerns and scalability.