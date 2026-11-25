# PrepPilot

AI-powered mock interview platform that conducts personalized technical interviews based on a user's resume and selected job role.

## Objective

We had created a platform that helps users prepare for job interviews through AI-powered mock interviews.

Users can create an account, securely log in, and upload their resume. They can then select the role and difficulty level for their mock interview and specify the interview duration. Each user has a personalized dashboard where they can view their previous mock interviews, track statistics such as total interviews, average score, and best score, and filter their interview history by role and difficulty. The platform will conduct an AI-powered interview tailored to the user's resume, selected role, and difficulty level. After the interview, the user's responses will be evaluated and they will receive a score out of 100.

The system is designed using a **multi-agent architecture**, where multiple asynchronous AI agents work together to handle different stages of the interview preparation and evaluation process. This approach allows the platform to perform tasks concurrently and create a more modular and scalable interview workflow.

We had also created a **custom resume parser built using C++** to efficiently extract and process relevant information from uploaded resumes. The parsed resume data is then used to personalize the interview experience based on the user's background, skills, experience, and target role.

## Features

- User authentication with Email/Password and OTP verification
- Google Authentication
- Resume upload and management
- Resume analysis based on selected role
- AI-generated personalized interview questions
- Difficulty-based interviews
- Video and audio recording
- Speech-to-text conversion
- AI evaluation of interview responses
- Dynamic follow-up questions
- Interview scoring
- Interview history and review
- Protected interview sessions
- Cloud-based resume storage

## Tech Stack

### Frontend

- React
- Vite
- Tailwind CSS
- React Router
- MediaRecorder API
- Google OAuth

### Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- Multer
- Nodemailer
- Cloudinary
- bcrypt

## System Architecture

```text
React + Vite
     |
     | HTTP Requests
     v
Node.js + Express
     |
     +------ MongoDB
     |
     +------ Cloudinary
     |
     +------ Google OAuth
     |
     +------ Email / OTP
     |
     v
FastAPI AI Engine
```

## Prerequisites

Before running PrepPilot locally, make sure you have:

- Node.js
- npm
- Git
- MongoDB Atlas account
- Google Cloud account for OAuth
- Cloudinary account
- Gmail account with an App Password for OTP emails

## Project Structure

```text
PrepPilot/
│
├── Frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
│
├── Backend/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── utils/
│   ├── parser/
│   ├── server.js
│   ├── package.json
│   └── ...
│
└── README.md
```

# Installation

## 1. Clone the Repository

```bash
git clone https://github.com/Evanshu24/PrepPilot
cd PrepPilot
```

## 2. Frontend Setup

Navigate to the frontend directory:

```bash
cd Frontend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `Frontend` directory:

```env
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

Start the development server:

```bash
npm run dev
```

The frontend will be available at:

```text
http://localhost:10000
```

## 3. Backend Setup

Open a new terminal and navigate to the backend:

```bash
cd Backend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `Backend` directory:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret

GOOGLE_CLIENT_ID=your_google_client_id

EMAIL_USER=your_email
EMAIL_PASS=your_gmail_app_password

GROQ_API_KEY=your_groq_api_key

CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

```

Start the backend:

```bash
npm run dev
```

The backend will run at:

```text
http://localhost:5000
```

# Environment Variables

The following environment variables are required by the application.

| Variable                | Description                        |
| ----------------------- | ---------------------------------- |
| `MONGO_URI`             | MongoDB connection string          |
| `JWT_SECRET`            | Secret used for JWT authentication |
| `GOOGLE_CLIENT_ID`      | Google OAuth client ID             |
| `EMAIL_USER`            | Email address used to send OTPs    |
| `EMAIL_PASS`            | Gmail App Password                 |
| `CLOUDINARY_CLOUD_NAME` | Cloudinary cloud name              |
| `CLOUDINARY_API_KEY`    | Cloudinary API key                 |
| `CLOUDINARY_API_SECRET` | Cloudinary API secret              |

For the frontend:

| Variable                | Description            |
| ----------------------- | ---------------------- |
| `VITE_GOOGLE_CLIENT_ID` | Google OAuth client ID |

> Never commit `.env` files or API keys to the repository.

## Running the Application

PrepPilot requires all three frontend, node backend and ai backend to be running simultaneously.

### Terminal 1 — Frontend

```bash
cd Frontend
npm run dev
```

### Terminal 2 — Backend

```bash
cd Backend
npm run dev
```

### Terminal 3 — AI Backend

```bash
cd AI
uvicorn main:app --reload
```

Then open:

http://localhost:10000

## Authentication

PrepPilot supports:

- Email/Password authentication
- Email verification using OTP
- Google Authentication
- JWT-based session authentication

For Google Authentication, configure the Google OAuth Client ID in both the frontend and backend environment variables.

## Resume Management

Users can:

- Upload their resume
- Replace an existing resume
- View their uploaded resume
- Store resumes securely using Cloudinary

## Interview Flow

```text
User
  |
  v
Select Role, Difficulty & Duration
  |
  v
Resume Analysis
  |
  v
Start Interview
  |
  v
AI Generated Question
  |
  v
User Answer
  |
  v
Speech-to-Text
  |
  v
AI Evaluation
  |
  v
Follow-up / Next Question
  |
  v
Final Score
  |
  v
Interview Review
```

## Future Improvements

- Real-time interview analytics
- More advanced resume analysis
- Improved AI evaluation
- Topic-wise performance analytics



