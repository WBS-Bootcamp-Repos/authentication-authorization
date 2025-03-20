# Travel Journal Application

## Overview

The Travel Journal Application is a full-stack web application developed as part of the authentication and authorization module. It consists of two main components: a frontend single-page application (SPA) built with React and a backend API built with Express.js and MongoDB. The application allows users to register, log in, create travel journal posts, and view posts, with secure user authentication and authorization implemented using JSON Web Tokens (JWT).

This project demonstrates proficiency in modern web development practices, including React for the frontend, Express.js for the backend, MongoDB for data persistence, and Tailwind CSS with DaisyUI for styling. It also showcases the implementation of secure user authentication and authorization, RESTful API design, and error handling.

---

## Project Structure

The application is divided into two repositories:

1. **travel-journal-spa**: The frontend React application.
2. **travel-journal-api**: The backend Express.js API.

### Frontend (travel-journal-spa)

The frontend is a React-based single-page application that provides a user-friendly interface for interacting with the travel journal.

#### Features

- User registration and login with form validation.
- Create, view, and read travel journal posts.
- Responsive design using Tailwind CSS and DaisyUI.
- Client-side routing with React Router.
- Toast notifications for user feedback using `react-toastify`.
- Error handling with custom error pages.

#### Directory Structure

```
travel-journal-spa/
├── src/
│   ├── components/         # Reusable UI components (e.g., Navbar, PostCard)
│   ├── data/              # API request functions (e.g., getPosts, createPost)
│   ├── layouts/           # Layout components (e.g., RootLayout)
│   ├── pages/             # Page components mapped to routes (e.g., Home, Login)
│   ├── App.jsx            # Main app component with routing setup
│   ├── index.css          # Global styles with Tailwind CSS
│   └── main.jsx           # Entry point for React
├── index.html             # HTML template
├── jsconfig.json          # Path alias configuration for imports
├── tailwind.config.js     # Tailwind CSS configuration
├── vite.config.js         # Vite configuration with path alias
└── package.json           # Dependencies and scripts
```

#### Setup Instructions

1. Fork and clone the repository.
2. Navigate to the project directory: `cd travel-journal-spa`.
3. Install dependencies: `npm install`.
4. Create a `.env.development.local` file with the following variable:
   - `VITE_APP_TRAVEL_JOURNAL_API_URL=http://localhost:8000` (adjust if your backend runs on a different port).
5. Start the development server: `npm run dev`.
   - The app will run on `http://localhost:5173` by default.

#### Available Commands

- `npm run dev`: Starts the development server.
- `npm run build`: Builds the app for production.
- `npm run preview`: Previews the production build locally.

---

### Backend (travel-journal-api)

The backend is an Express.js API that provides RESTful endpoints for managing users and travel journal posts, with MongoDB as the database.

#### Features

- User registration and login with JWT-based authentication.
- Role-based authorization (e.g., admin-protected routes).
- CRUD operations for travel journal posts.
- Input validation using Joi.
- Error handling with custom middleware.
- Secure password hashing with `bcrypt`.

#### Directory Structure

```
travel-journal-api/
├── controllers/           # Request handlers (e.g., auth, posts)
├── db/                   # MongoDB connection setup
├── joi/                  # Joi schemas for input validation
├── middlewares/          # Custom middleware (e.g., authenticate, authorize)
├── models/               # Mongoose models (e.g., User, Post)
├── routes/               # API routes (e.g., auth, posts)
├── utils/                # Utility functions (e.g., asyncHandler, ErrorResponse)
├── index.js              # Entry point for the Express server
└── package.json          # Dependencies and scripts
```

#### Setup Instructions

1. Fork and clone the repository.
2. Navigate to the project directory: `cd travel-journal-api`.
3. Install dependencies: `npm install`.
4. Create a `.env` file with the following variables:
   - `MONGO_URI=<your-mongodb-connection-string>`
   - `JWT_SECRET=<your-jwt-secret>`
   - `PORT=8000` (optional, defaults to 8000)
5. Start the development server: `npm run dev`.
   - The API will run on `http://localhost:8000` by default.

#### Available Commands

- `npm run dev`: Starts the development server with auto-restart on file changes.
- `npm start`: Starts the production server.

#### API Endpoints

- **Auth Routes**:
  - `POST /auth/register`: Register a new user.
  - `POST /auth/login`: Log in and receive a JWT token.
  - `GET /auth/profile`: Get the authenticated user's profile (requires authentication).
  - `GET /auth/adminProtectedRoute`: Access an admin-only route (requires authentication and admin role).
- **Post Routes**:
  - `GET /posts`: Retrieve all posts.
  - `POST /posts`: Create a new post.
  - `GET /posts/:id`: Retrieve a single post by ID.
  - `PUT /posts/:id`: Update a post by ID.
  - `DELETE /posts/:id`: Delete a post by ID.

---

## Technologies Used

### Frontend

- **React**: JavaScript library for building user interfaces.
- **React Router**: For client-side routing.
- **Tailwind CSS & DaisyUI**: For styling and responsive design.
- **Vite**: Build tool and development server.
- **React Toastify**: For toast notifications.
- **ESLint**: For linting and maintaining code quality.

### Backend

- **Express.js**: Web framework for Node.js.
- **MongoDB & Mongoose**: Database and ODM for data persistence.
- **JWT (jsonwebtoken)**: For authentication.
- **Bcrypt**: For password hashing.
- **Joi**: For input validation.
- **CORS**: For enabling cross-origin requests.

---

## Usage

1. **Start the Backend**:

   - Follow the setup instructions for `travel-journal-api`.
   - Ensure MongoDB is running and the `MONGO_URI` is correctly configured.

2. **Start the Frontend**:

   - Follow the setup instructions for `travel-journal-spa`.
   - Ensure the backend API URL is correctly set in `.env.development.local`.

3. **Interact with the Application**:
   - Register a new user via the `/register` page.
   - Log in via the `/login` page to receive a JWT token.
   - Create a new travel journal post via the `/create` page.
   - View all posts on the homepage (`/`) and click "Read More" to view a single post.

---

## Development Notes

- **Path Aliases**: The frontend uses a path alias `@/` to simplify imports (e.g., `import { Navbar } from '@/components'`). This is configured in `vite.config.js` and `jsconfig.json`.
- **Error Handling**: Both frontend and backend implement custom error handling. The frontend displays user-friendly error messages via toast notifications and custom error pages, while the backend returns structured error responses.
- **Security**: The backend uses JWT for authentication, bcrypt for password hashing, and Joi for input validation to ensure secure data handling.
- **Styling**: The frontend uses Tailwind CSS with DaisyUI for a consistent and responsive design.

---

## Future Improvements

- Implement protected routes on the frontend to restrict access to certain pages (e.g., `/create`) for authenticated users only.
- Add user profile management features (e.g., update profile, delete account).
- Enhance the backend with additional validation and error handling for edge cases.
- Add pagination for the posts list on the homepage to improve performance with large datasets.

---

## Contact

For questions or feedback, please reach out via GitHub issues on the respective repositories:

- [travel-journal-spa](https://github.com/<your-username>/travel-journal-spa)
- [travel-journal-api](https://github.com/<your-username>/travel-journal-api)

---

## Contributions

Contributions are welcome. Feel free to fork the repo and submit pull requests.
