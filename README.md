# Tech Products Dashboard

This project is a **React-based application** that allows users to view and manage a list of tech products fetched from an external API. The application features authentication via login, a dashboard to list the products in a table, and a detailed view for individual products. This project is designed to handle authentication, product listing, and navigation to a product’s detailed page seamlessly.

## Features

- **Login Page**: Allows users to log in using the `reqres.in` API.
- **Dashboard**: Displays a paginated list of tech products in a table format. Each product can be clicked to view detailed information on a separate page.
- **Single Product Page**: Displays detailed information about a single product when a user clicks on the product's brand on the Dashboard page.
- **Private Routes**: Ensures that only authenticated users can access the Dashboard and Single Product Pages.
- **Responsive Design**: The application is fully responsive, making it accessible across devices like smartphones, tablets, and desktops.

## Installation

To set up the project locally, follow these steps:

1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <project-folder>
Install the dependencies:

bash
Copy
Edit
npm install
To run the application, use:

bash
Copy
Edit
npm start
Open your browser and visit http://localhost:3000.

Project Structure
bash
Copy
Edit
src/
├── components/              # Reusable components
│   ├── ProductCard.jsx      # Component to display each product in the table
│   ├── ProductsTable.jsx    # Table component to display list of products
│   ├── Loader.jsx           # Loader component for showing loading status
│   ├── PrivateRoute.jsx     # Private Route to protect sensitive pages
│   └── AuthContext.jsx      # Context for managing authentication state
├── pages/                   
│   ├── Home.jsx             # Landing page
│   ├── Login.jsx            # Login page for authentication
│   ├── Dashboard.jsx        # Dashboard to show the list of products
│   ├── SingleProductPage.jsx # Page to show individual product details
│   └── AllRoutes.jsx        # All route definitions for the app
├── App.js                   # Main entry point of the app
└── index.js                 # React DOM rendering
API Integration
Products API
GET: /mockapi/get-tech-products

Fetches a list of tech products.

Example response:

json
Copy
Edit
{
  "data": [
    {
      "id": 1,
      "brand": "Apple",
      "category": "Smartphone",
      "price": "$999"
    },
    ...
  ],
  "totalPages": 3
}
GET: /mockapi/get-tech-products/:id

Fetches a specific product by ID.

Example response:

json
Copy
Edit
{
  "data": {
    "id": 1,
    "brand": "Apple",
    "category": "Smartphone",
    "price": "$999",
    "details": "iPhone 13 with A15 Bionic chip"
  }
}
Authentication API
POST: /api/login

Used for logging in users.

Request body:

json
Copy
Edit
{
  "email": "user@example.com",
  "password": "password123"
}
Pages
Home Page
The Home page contains links to navigate to the Login and Dashboard pages.

Login Page
The user can log in by providing an email and password. Upon successful login, the user is redirected to the Dashboard page.

Dashboard Page
Displays a paginated list of products from the API.

The table shows product details like ID, brand, category, and price.

Clicking the product's brand name redirects the user to the Single Product Page.

Single Product Page
Displays detailed information about a product.

Information includes product brand, category, image, price, and description.

This page is accessible only after clicking the brand name on the Dashboard page.

Components
ProductCard
Displays information for a single product.

Accepts id, brand, category, and price as props.

ProductsTable
Displays a table of products, where each row is a ProductCard.

PrivateRoute
Protects routes that require authentication.

Redirects the user to the Login page if they are not authenticated.

AuthContext
Provides authentication state and methods (loginUser, logoutUser) for managing user login status throughout the app.

Loader
Displays a loading spinner while the data is being fetched from the API.

Technologies Used
React: For building the UI and managing components.

React Router: For managing the routes in the app.

Context API: For managing authentication state.

Bootstrap: For responsive design and styling.

Axios: For making HTTP requests to the API.

Known Issues
API Issue: There were issues with the reqres.in API, which caused login failures at the last moment. We had to implement fallback error handling and a mock version for testing.

Conclusion
This application demonstrates how to integrate authentication and API-based data fetching in React. The Dashboard page presents a list of tech products, and each product can be clicked to view more details. The application is designed with security and usability in mind, and follows best practices for managing authentication state using Context API.

#Project Video Link
https://drive.google.com/drive/folders/1eln3mQGZj8Q1F53zKKHPOkJfO4Hp6yF3
