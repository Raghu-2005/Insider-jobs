# Insider Jobs

A full-stack job portal application that streamlines the hiring and job application process through a role-based, secure, and responsive web interface.

**Live Demo:** [insider-jobs-jade.vercel.app](https://insider-jobs-jade.vercel.app)

---

## Overview

Insider Jobs bridges the gap between recruiters and job seekers by providing a unified platform where recruiters can manage job listings end-to-end and applicants can discover and apply for opportunities — all within a seamless, authenticated environment.

The application implements a clean separation of concerns across a React frontend and a Node.js/Express backend, with MongoDB as the persistence layer and Clerk handling authentication and role management.

---

## Features

### Recruiter Workflow
- Secure sign-in and session management via Clerk
- Create, edit, and delete job listings from a dedicated dashboard
- View all applicants who have applied to each job posting
- Role-based access control ensuring only authorized recruiters can manage listings

### Applicant Workflow
- Secure sign-in and account creation via Clerk
- Browse and search all active job listings
- View detailed job descriptions and requirements
- Submit applications with a single click

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, Vite, Tailwind CSS, Axios |
| Backend | Node.js, Express.js |
| Database | MongoDB with Mongoose ODM |
| Authentication | Clerk (JWT-based, role-aware) |
| Dev Tooling | Nodemon, Dotenv, CORS |
| Deployment | Vercel (Frontend) |

---

## Project Structure

```
Insider-jobs/
├── client/               # React frontend (Vite)
│   ├── src/
│   │   ├── components/   # Reusable UI components
│   │   ├── pages/        # Route-level page components
│   │   └── main.jsx      # Application entry point
│   ├── index.html
│   └── vite.config.js
│
└── server/               # Node.js/Express backend
    ├── models/           # Mongoose schemas
    ├── routes/           # API route handlers
    ├── middleware/        # Auth and error middleware
    └── index.js          # Server entry point
```

---

## Getting Started

### Prerequisites

Ensure the following are installed on your machine:

- Node.js v18 or higher
- npm v9 or higher
- MongoDB (local instance or MongoDB Atlas connection string)
- A [Clerk](https://clerk.com) account for authentication credentials

### 1. Clone the Repository

```bash
git clone https://github.com/Raghu-2005/Insider-jobs.git
cd Insider-jobs
```

### 2. Configure the Backend

```bash
cd server
npm install
```

Create a `.env` file in the `server/` directory:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
CLERK_SECRET_KEY=your_clerk_secret_key
```

Start the backend server:

```bash
npm run dev
```

The server will run at `http://localhost:5000`.

### 3. Configure the Frontend

```bash
cd ../client
npm install
```

Create a `.env` file in the `client/` directory:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_API_BASE_URL=http://localhost:5000
```

Start the development server:

```bash
npm run dev
```

The frontend will be available at `http://localhost:5173`.

---

## Environment Variables Reference

### Server (`server/.env`)

| Variable | Description |
|---|---|
| `PORT` | Port the Express server listens on |
| `MONGODB_URI` | MongoDB connection string (local or Atlas) |
| `CLERK_SECRET_KEY` | Clerk secret key for server-side JWT verification |

### Client (`client/.env`)

| Variable | Description |
|---|---|
| `VITE_CLERK_PUBLISHABLE_KEY` | Clerk publishable key for frontend auth integration |
| `VITE_API_BASE_URL` | Base URL pointing to the Express backend |

---

## Screenshots

### Home Page
![Home Page](https://github.com/user-attachments/assets/059f2156-ea4b-499e-a76b-038871b9ffb9)
![Home Page Continued](https://github.com/user-attachments/assets/782bbbaa-2346-4b3d-b7f0-8b0d3ac81866)

### Recruiter Dashboard
![Recruiter Dashboard](https://github.com/user-attachments/assets/5b93c17b-4663-4988-a0e3-8f0d848ead06)
![Job Listings Management](https://github.com/user-attachments/assets/76ed2331-77a9-411e-82f9-f4efa726abc4)
![Applicant View](https://github.com/user-attachments/assets/6dcd366c-22c3-471e-aed1-ba61d56110e2)

### Authentication
![Sign In](https://github.com/user-attachments/assets/0c4c4644-59cf-47c3-9822-0708fbcdeedd)
![Sign Up](https://github.com/user-attachments/assets/5c423b75-a7c5-4906-83a9-589de4cc7b20)

---

## API Overview

The backend exposes a RESTful API. All protected routes require a valid Clerk JWT passed in the `Authorization` header.

| Method | Endpoint | Description | Auth Required |
|---|---|---|---|
| GET | `/api/jobs` | Retrieve all active job listings | No |
| GET | `/api/jobs/:id` | Retrieve a specific job by ID | No |
| POST | `/api/jobs` | Create a new job listing | Yes (Recruiter) |
| PUT | `/api/jobs/:id` | Update an existing job listing | Yes (Recruiter) |
| DELETE | `/api/jobs/:id` | Delete a job listing | Yes (Recruiter) |
| POST | `/api/applications` | Submit a job application | Yes (Applicant) |
| GET | `/api/applications/:jobId` | Get applicants for a job | Yes (Recruiter) |

---

## Deployment

### Frontend (Vercel)

The frontend is deployed on Vercel. To deploy your own instance:

1. Push the `client/` directory to a GitHub repository.
2. Import the repository in [Vercel](https://vercel.com).
3. Set the root directory to `client`.
4. Add the required environment variables in the Vercel dashboard.
5. Deploy.

### Backend

The Express server can be deployed to any Node.js-compatible platform such as Railway, Render, or Heroku. Ensure all environment variables are configured in the platform's settings before deploying.

---

## Roadmap

The following enhancements are planned for future releases:

- Resume upload and parsing during application submission
- Real-time application status notifications
- Advanced job filtering by location, salary range, and category
- Recruiter analytics dashboard with application metrics
- Email notification integration for application updates

---

## Contributing

Contributions are welcome. To propose a change:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature-name`)
3. Commit your changes with clear, descriptive messages
4. Open a pull request against the `main` branch

Please ensure any new functionality includes appropriate error handling and does not break existing API contracts.

---

## License

This project is open source and available under the [MIT License](LICENSE).

---

## Contact

**Raghuram L** — Software Developer

- Email: [lraghuram14@gmail.com](mailto:lraghuram14@gmail.com)
- LinkedIn: [linkedin.com/in/raghuram-l-1193b5259](https://www.linkedin.com/in/raghuram-l-1193b5259/)
- GitHub: [github.com/Raghu-2005](https://github.com/Raghu-2005)
