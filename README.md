# BookStore App

This is a CRUD (Create, Read, Update, Delete) application for managing a collection of books. The frontend is built with Angular 18 and Bootstrap, while the backend is developed using .NET Core 8 and C# with JWT-based authentication.

## Features

- User Authentication (Sign Up, Log In, Log Out)
- Add, Edit, Delete Books
- Add and manage favorite quotes
- JWT token management for securing API endpoints
- Responsive design with Bootstrap

## Prerequisites

Before you can run this application locally, ensure you have the following installed:

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- [Node.js (with npm)](https://nodejs.org/en/download/) (v14 or later)
- [Angular CLI](https://angular.io/cli) (v18 or later)
 (if you plan to use a local database, though in-memory storage is used by default)

## Getting Started

### 1. Clone the Repository

2. Backend Setup (.NET Core)
Navigate to the BookStoreApi directory:

bash
Kopiera kod
cd BookStoreApi
Restore the .NET dependencies:

bash
Kopiera kod
dotnet restore
Update the appsettings.json for local development:

json
Kopiera kod
{
  "Jwt": {
    "Key": "your-secure-key",
    "Issuer": "https://localhost:5001",
    "Audience": "https://localhost:4200"
  },
  "AllowedHosts": "*"
}
Run the migrations (if you switch to a database instead of in-memory storage):

bash
Kopiera kod
dotnet ef database update
Build and run the backend server:

bash
Kopiera kod
dotnet build
dotnet run
The backend server should now be running at https://localhost:5001 or http://localhost:5000.

3. Frontend Setup (Angular)
Navigate to the BookStoreClient directory:

bash
Kopiera kod
cd ../BookStoreClient
Install the Angular dependencies:

bash
Kopiera kod
npm install
Start the Angular development server:

bash
Kopiera kod
ng serve
The frontend should now be running at http://localhost:4200.

4. Running the Application
Open your browser and navigate to http://localhost:4200.
You can now interact with the application, sign up, log in, and manage books and quotes.
API Endpoints
Here are some of the available API endpoints:

POST /api/auth/signup: Create a new user
POST /api/auth/login: Log in as an existing user
GET /api/books: Get a list of all books
POST /api/books: Add a new book (Authenticated users only)
PUT /api/books/{id}: Edit an existing book (Authenticated users only)
DELETE /api/books/{id}: Delete a book (Authenticated users only)
POST /api/quotes: Add a new quote (Authenticated users only)
