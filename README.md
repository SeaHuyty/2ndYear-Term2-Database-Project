# QR Code Event Ticketing System

This project is a **new version** of a [previous project that used Python](https://github.com/SeaHuyty/photo-phnom-penh-festival-ticket-system) and stored data in a CSV file for **Tuk Tuk Tour** of **15th Photo Phnom Penh Festival**.

## Features

- User registration with **name, email, phone number, and event selection**
- QR code generation containing a unique user ID
- Admin QR code scanner for verification
- **Two event days** with a maximum of 200 tickets each
- **MySQL database** integration to store user and event details
- Express.js backend and React frontend

## Tech Stack

- **Frontend:** React
- **Backend:** Express.js (Node.js)
- **Database:** MySQL

## Database Schema

### `users` Table

| Column  | Type         | Description                                        |
| ------- | ------------ | -------------------------------------------------- |
| id      | INT (PK)     | Unique user ID                                     |
| name    | VARCHAR(100) | User's full name                                   |
| email   | VARCHAR(100) | User's email                                       |
| phone   | VARCHAR(20)  | User's phone number                                |
| used    | TINYINT(1)   | Whether the ticket has been used (0 = No, 1 = Yes) |
| eventId | INT (FK)     | Associated event ID                                |

### `event` Table

| Column | Type         | Description                     |
| ------ | ------------ | ------------------------------- |
| id     | INT (PK)     | Unique event ID                 |
| name   | VARCHAR(100) | Event name (e.g., Day 1, Day 2) |
| ticket | INT          | Number of remaining tickets     |

## `admins` Table

| Column     | Type         | Description                     |
| ---------- | ------------ | --------------------------------|
| id         | INT (PK)     | Unique admin ID                 |
| username   | VARCHAR(100) | Admin username                  |
| password   | VARCHAR(100) | Admin password                  |

## Installation

1. Clone the repository:

   ```sh
   git clone https://github.com/SeaHuyty/2ndYear-Term2-Database-Project.git
   cd 2ndYear-Term2-Database-Project
   ```

2. Install Libraries and Dependency

   1. Backend: 
   
      ```sh
      cd backend
      npm install
      ```

   2. Frontend: 
      
      ```sh
      cd frontend
      npm install
      ```

3. Start the backend:

   ```sh
   node server.js
   ```

4. Start the frontend:

   ```sh
   npm run dev
   ```

## Usage

1. **User Registration**: Fill out the form and select an event day.
2. **QR Code Generation**: A unique QR code will be displayed after successful registration.
3. **Scanning & Verification**: The admin scans the QR code, and the system verifies if it is valid and unused.

## License

This project is licensed under the [MIT License](LICENSE).
