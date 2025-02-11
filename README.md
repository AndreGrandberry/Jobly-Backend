# Jobly Backend
## Overview
Jobly is a full-stack web application designed to allow users to explore and "apply" for jobs online. This repository contains the backend API, built using Node.js, Express, and PostgreSQL. The API provides endpoints for user authentication, job listings, company profiles, and user applications.
### Features
- User Authentication & Authorization
  - Secure login/logout functionality
  - Token-based authentication using JWT
  - Role-based authorization (admin vs regular users)
- Companies API
  - Retrieve company profiles
  - Filter companies by name
  - Admins can create, update, and delete companies
- Jobs API
  - Retrieve job listings
  - Filter jobs by title, salary, and equity
  - Admins can create, update, and delete jobs
- Users API
  - Retrieve user profiles
  - Users can update their profile information
  - Users can apply for jobs
### Technologies Used
- Node.js (backend runtime)
- Express.js (web framework for handling API routes)
- PostgreSQL (relational database for storing users, jobs, and company data)
- JWT (JSON Web Tokens) (authentication & security)
- bcrypt (password hashing)
- pg (node-postgres) (PostgreSQL database client for Node.js)
### Installation & Setup

#### Prerequisites

Ensure you have the following installed:
- Node.js
- PostgreSQL

#### Steps to Set Up Locally

1. Clone the Repository

git clone https://github.com/YOUR_USERNAME/jobly-backend.git
cd jobly-backend

2. Install Dependencies

npm install

3. Set Up Environment Variables

Create a .env file in the root directory with the following variables:

DATABASE_URL=postgresql://your_user:your_password@localhost/jobly
SECRET_KEY=your_secret_key
NODE_ENV=development

4. Set Up Database

Create and seed the PostgreSQL database:

createdb jobly
psql jobly < jobly-schema.sql

5. Run the Server

npm start

The backend should now be running at http://localhost:3001.

## API Endpoints

### Authentication
- POST /auth/login - Authenticate user and return JWT
- POST /auth/register - Register a new user
### Companies
- GET /companies - Retrieve all companies
- GET /companies/:handle - Retrieve a single company by handle
- POST /companies - (Admin only) Create a new company
- PATCH /companies/:handle - (Admin only) Update company details
- DELETE /companies/:handle - (Admin only) Delete a company
### Jobs
- GET /jobs - Retrieve all job listings
- GET /jobs/:id - Retrieve a specific job
- POST /jobs - (Admin only) Create a job
- PATCH /jobs/:id - (Admin only) Update a job listing
- DELETE /jobs/:id - (Admin only) Delete a job listing
### Users
- GET /users - (Admin only) Retrieve all users
- GET /users/:username - Retrieve a user profile
- PATCH /users/:username - Update user profile
- POST /users/:username/jobs/:id - Apply for a job
### Testing
Run the test suite using Jest: npm test
