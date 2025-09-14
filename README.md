# BlogSphere

A modern, full-stack MERN blog application with admin-controlled content management. Built with React, Node.js, Express, and MongoDB, featuring a rich text editor for creating engaging blog posts.

## 🚀 Features

- **Admin Control**: Only admin can create, update, and delete blog posts
- **Rich Text Editor**: Powered by ReactQuill for enhanced content creation
- **Responsive Design**: Fully responsive web application that works on all devices
- **Chronological Display**: Blog posts displayed in chronological order on the home page
- **Authentication**: Secure admin login system with JWT tokens
- **Modern UI**: Clean and intuitive user interface

## 🛠️ Tech Stack

- **Frontend**: React 16.12.0, React Router DOM, ReactQuill
- **Backend**: Node.js, Express.js, Mongoose
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)
- **Styling**: CSS3
- **Deployment**: Heroku

## 📋 Prerequisites

Before running this application, make sure you have:

- **Node.js** (v14 or higher)
- **MongoDB** (local installation or MongoDB Atlas account)
- **Git** (for version control)
- **Heroku CLI** (for deployment)

## 🏃‍♂️ Quick Start

### Local Development

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd BlogSphere
   ```

2. **Install dependencies for both client and server**

   ```bash
   # Install server dependencies
   cd server
   npm install

   # Install client dependencies
   cd ../client
   npm install
   ```

3. **Set up environment variables**

   Create a `.env` file in the `server` directory:

   ```env
   DATABASE=mongodb://localhost:27017/blogsphere
   JWT_SECRET=your-secret-key-here
   PASSWORD=admin123
   ```

4. **Start the development servers**

   **Terminal 1 - Backend Server:**

   ```bash
   cd server
   npm run dev
   ```

   **Terminal 2 - Frontend Client:**

   ```bash
   cd client
   npm start
   ```

5. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000

### Admin Login

- **Login Name**: Your name
- **Password**: The password set in your `.env` file (default: `admin123`)

## 🚀 Deployment on Heroku

### Prerequisites for Deployment

1. **MongoDB Atlas Setup**

   - Create a MongoDB Atlas account
   - Create a new cluster
   - Get your connection string
   - Whitelist all IPs (0.0.0.0/0) in Network Access

2. **Heroku CLI Installation**
   - Download and install Heroku CLI
   - Login: `heroku login`

### Backend Deployment

1. **Navigate to server directory**

   ```bash
   cd server
   ```

2. **Initialize Git and deploy**

   ```bash
   git init
   git add .
   git commit -m "Initial backend commit"
   heroku create your-backend-app-name
   git push heroku master
   ```

3. **Set environment variables**

   ```bash
   heroku config:set DATABASE="mongodb+srv://username:password@cluster.mongodb.net/blogsphere"
   heroku config:set JWT_SECRET="your-secret-key-here"
   heroku config:set PASSWORD="admin123"
   ```

4. **Get backend URL**
   ```bash
   heroku open
   ```
   Copy the URL (e.g., `https://your-backend-app-name.herokuapp.com`)

### Frontend Deployment

1. **Build React app**

   ```bash
   cd client
   npm run build
   ```

2. **Create environment file**

   Create `.env` file in client directory:

   ```env
   REACT_APP_API=https://your-backend-app-name.herokuapp.com/api
   ```

3. **Deploy frontend**

   ```bash
   git init
   git add .
   git commit -m "Initial frontend commit"
   heroku create your-frontend-app-name
   git push heroku master
   ```

4. **Set environment variable**
   ```bash
   heroku config:set REACT_APP_API=https://your-backend-app-name.herokuapp.com/api
   ```

## 📁 Project Structure

```
BlogSphere/
├── client/                 # React frontend
│   ├── public/            # Static files
│   ├── src/               # React components and logic
│   │   ├── components/    # Reusable components
│   │   ├── styles/        # CSS files
│   │   └── ...
│   ├── package.json       # Frontend dependencies
│   └── server.js          # Production server
├── server/                # Node.js backend
│   ├── controllers/       # Route controllers
│   ├── models/           # MongoDB models
│   ├── routes/           # API routes
│   ├── package.json      # Backend dependencies
│   └── server.js         # Main server file
├── LICENSE
└── README.md
```

## 🔧 Available Scripts

### Server Scripts

- `npm start` - Start production server
- `npm run dev` - Start development server with nodemon

### Client Scripts

- `npm start` - Start development server
- `npm run build` - Build for production
- `npm test` - Run tests

## 🐛 Troubleshooting

### Common Issues

1. **Database Connection Error**

   - Verify MongoDB connection string
   - Check if MongoDB Atlas allows connections from all IPs

2. **Authentication Issues**

   - Verify JWT_SECRET is set correctly
   - Check password in environment variables

3. **Build Errors**

   - Clear node_modules and reinstall: `rm -rf node_modules && npm install`
   - Check Node.js version compatibility

4. **Heroku Deployment Issues**
   - Check logs: `heroku logs --tail`
   - Verify environment variables: `heroku config`
   - Ensure Procfile exists and is correct

## 📝 API Endpoints

- `GET /api/posts` - Get all blog posts
- `GET /api/post/:slug` - Get single blog post
- `POST /api/post` - Create new blog post (admin only)
- `PUT /api/post/:slug` - Update blog post (admin only)
- `DELETE /api/post/:slug` - Delete blog post (admin only)
- `POST /api/signin` - Admin authentication

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit changes: `git commit -m 'Add feature'`
4. Push to branch: `git push origin feature-name`
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

[@mayankdrvr](https://www.github.com/mayankdrvr)

## 🔗 Live Demo

The application is deployed and available at: [https://mern-blog-3gnt.onrender.com/](https://mern-blog-3gnt.onrender.com/)

---

**Note**: Wait a few seconds for the site to load. If features aren't working, try refreshing the page and clearing browser cache.
