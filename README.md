<div align="center">
  <h1>🎥 Zoom Call - Video Conferencing Application</h1>
  
  [![Node.js](https://img.shields.io/badge/Node.js-18.x-green?logo=node.js)](https://nodejs.org/)
  [![React](https://img.shields.io/badge/React-18.x-blue?logo=react)](https://reactjs.org/)
  [![MongoDB](https://img.shields.io/badge/MongoDB-Latest-green?logo=mongodb)](https://www.mongodb.com/)
  [![Express.js](https://img.shields.io/badge/Express.js-4.18-black?logo=express)](https://expressjs.com/)
  [![Socket.io](https://img.shields.io/badge/Socket.io-4.7-red?logo=socket.io)](https://socket.io/)
  [![License](https://img.shields.io/badge/License-ISC-yellow)](LICENSE)

  <p>
    <strong>A modern, full-stack real-time video conferencing application built with React, Node.js, and WebSockets.</strong>
  </p>
  
  [Features](#-features) • [Tech Stack](#-tech-stack) • [Installation](#-installation) • [Usage](#-usage) • [Contributing](#-contributing)
</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Endpoints](#-api-endpoints)
- [Environment Variables](#-environment-variables)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 About

ZoomCall is a feature-rich video conferencing application that enables users to host and join video meetings in real-time. Built with modern web technologies, it provides a seamless experience for video communication with a responsive and intuitive user interface.

**Key Highlights:**
- ✨ Real-time video and audio communication
- 🔐 Secure user authentication
- 📱 Fully responsive design
- ⚡ Low-latency WebSocket communication
- 🎨 Modern UI/UX with React

---

## ✨ Features

### 🎥 Core Features
- **Real-time Video Streaming** - Crystal clear video communication using WebRTC
- **Audio Management** - Control microphone input with mute/unmute functionality
- **User Authentication** - Secure login and registration system
- **Meeting Management** - Create, join, and manage video conferences
- **User Profiles** - Personalized user accounts with profile management
- **Meeting History** - Track previous meetings and participants
- **Responsive Design** - Works seamlessly on desktop and tablets

### 🚀 Performance
- Optimized real-time communication with Socket.io
- Efficient state management with React Context API
- Database indexing for fast queries

---

## 🛠 Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| **React 18** | User interface framework |
| **Socket.io Client** | WebSocket communication |
| **CSS Modules** | Component styling |
| **React Router** | Client-side routing |

### Backend
| Technology | Purpose |
|---|---|
| **Node.js** | JavaScript runtime |
| **Express.js** | Web framework |
| **MongoDB** | NoSQL database |
| **Socket.io** | Real-time communication |
| **Mongoose** | MongoDB ODM |
| **CORS** | Cross-origin requests |

---

## 📂 Project Structure

```
Zoom-main/
├── frontend/                 # React frontend application
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/       # Reusable components
│   │   ├── pages/           # Page components
│   │   │   ├── landing.jsx
│   │   │   ├── authentication.jsx
│   │   │   ├── home.jsx
│   │   │   ├── VideoMeet.jsx
│   │   │   └── history.jsx
│   │   ├── contexts/        # React Context
│   │   │   └── AuthContext.jsx
│   │   ├── utils/           # Utility functions
│   │   │   └── withAuth.jsx
│   │   ├── styles/          # Global styles
│   │   ├── App.js
│   │   └── index.js
│   └── package.json
│
├── backend/                  # Node.js backend application
│   ├── src/
│   │   ├── app.js           # Express app configuration
│   │   ├── controllers/     # Route controllers
│   │   │   ├── socketManager.js
│   │   │   └── user.controller.js
│   │   ├── models/          # Database models
│   │   │   ├── user.model.js
│   │   │   └── meeting.model.js
│   │   └── routes/          # API routes
│   │       └── users.routes.js
│   ├── .env.example         # Environment variables template
│   └── package.json
│
└── README.md
```

---

## 🚀 Installation

### Prerequisites
- **Node.js** (v14.0 or higher)
- **npm** or **yarn** package manager
- **MongoDB** (Local or Atlas)
- **Git**

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Create `.env` file:**
   ```bash
   cp .env.example .env
   ```

4. **Configure environment variables:**
   ```env
   PORT=8000
   MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/zoom_db
   ```

5. **Start the backend server:**
   ```bash
   npm run dev    # Development mode with nodemon
   # OR
   npm start      # Production mode
   ```

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure backend URL:**
   Edit `src/environment.js`:
   ```javascript
   export const backend_url = "http://localhost:8000";
   ```

4. **Start the frontend application:**
   ```bash
   npm start
   ```

The application will open at `http://localhost:3000`

---

## 💻 Usage

### Getting Started

1. **Open the Application**
   - Navigate to `http://localhost:3000` in your browser

2. **Authentication**
   - Sign up with your email and password
   - Or log in if you already have an account

3. **Create a Meeting**
   - Click "Start Meeting" to host a new video conference
   - Share the meeting link with participants

4. **Join a Meeting**
   - Click "Join Meeting" and enter the room code
   - Allow camera and microphone permissions when prompted

5. **During the Call**
   - Toggle video/audio with on-screen controls
   - View call history after the meeting ends

### Available Scripts

**Backend:**
```bash
npm run dev      # Run with nodemon (auto-reload)
npm start        # Run production server
npm run prod     # Run with PM2
```

**Frontend:**
```bash
npm start        # Start development server
npm run build    # Build for production
npm test         # Run tests
```

---

## 🔌 API Endpoints

### User Routes
| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/v1/users/register` | Register a new user |
| `POST` | `/api/v1/users/login` | User login |
| `GET` | `/api/v1/users/profile` | Get user profile |
| `PUT` | `/api/v1/users/profile` | Update user profile |
| `GET` | `/api/v1/users/history` | Get meeting history |

### WebSocket Events
| Event | Description |
|---|---|
| `connection` | Establish WebSocket connection |
| `join-room` | Join a video meeting room |
| `disconnect` | Leave the meeting |
| `call-user` | Initiate video call |
| `answer-call` | Answer incoming call |

---

## 🔐 Environment Variables

Create a `.env` file in the backend directory with the following variables:

```env
# Server Configuration
PORT=8000
NODE_ENV=development

# Database Configuration
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/zoom_db

# CORS Configuration
FRONTEND_URL=http://localhost:3000
```

**⚠️ Important Security Notes:**
- Never commit `.env` file to version control
- Use `.env.example` as a template for team members
- Rotate credentials regularly
- Keep sensitive data out of logs

---

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/Shubhankarmaity/ZoomCall.git
   cd ZoomCall
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```

3. **Make Your Changes**
   - Follow the existing code style
   - Write meaningful commit messages
   - Add tests for new features

4. **Commit Your Work**
   ```bash
   git add .
   git commit -m 'Add some AmazingFeature'
   ```

5. **Push to Your Branch**
   ```bash
   git push origin feature/AmazingFeature
   ```

6. **Open a Pull Request**
   - Describe your changes clearly
   - Reference any related issues

### Coding Standards
- Use meaningful variable and function names
- Add comments for complex logic
- Follow React and Node.js best practices
- Ensure code is properly formatted

---

## 📝 License

This project is licensed under the **ISC License** - see the LICENSE file for details.

---

## 👥 Author

**Shubhankar Maity**
- GitHub: [@Shubhankarmaity](https://github.com/Shubhankarmaity)
- Email: indiavivo956@gmail.com

---

## 🙏 Acknowledgments

- [Socket.io](https://socket.io/) for real-time communication
- [MongoDB](https://www.mongodb.com/) for database services
- [React](https://reactjs.org/) for the UI framework
- [Express.js](https://expressjs.com/) for the server framework

---

## 📞 Support

If you encounter any issues or have questions:
1. Check existing [GitHub Issues](https://github.com/Shubhankarmaity/ZoomCall/issues)
2. Create a new issue with detailed information
3. Describe steps to reproduce the problem
4. Include error messages and screenshots if applicable

---

<div align="center">
  <p>Made with ❤️ by Shubhankar Maity</p>
  <p>⭐ If you find this project helpful, please consider giving it a star!</p>
</div>
