# Course Hub - Modern LMS & Course Selling Platform

A comprehensive Learning Management System (LMS) and course selling platform built with modern web technologies.

## 🌟 Features

### User Features
- **Authentication System** - Secure signup/login with JWT
- **Course Catalog** - Browse and filter courses
- **Single Course Pages** - Detailed course information with video preview
- **Student Dashboard** - Track progress, access enrolled courses
- **Lesson Player** - Video player with notes and downloadable resources
- **Quiz System** - 20 MCQ questions per course
- **Payment Integration** - EasyPaisa, JazzCash, Bank Transfer
- **Progress Tracking** - Monitor learning progress
- **Certificate System** - Digital certificates upon course completion

### Instructor Features
- **Instructor Profile** - Showcase skills and experience
- **Course Management** - Create and manage courses
- **Curriculum Management** - Add lessons and quizzes
- **Social Links** - GitHub, LinkedIn, and other profiles

### Admin Features
- **Admin Panel** - Manage courses and users
- **User Management** - View and manage all users
- **Course Moderation** - Approve/reject courses
- **Payment Tracking** - Monitor all transactions
- **Analytics** - Course performance metrics

## 🛠 Tech Stack

### Frontend
- **React** - UI library
- **React Router** - Client-side routing
- **Tailwind CSS** - Responsive styling
- **Context API** - State management
- **Axios** - HTTP client
- **React Player** - Video player component
- **React Icons** - Icon library

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **CORS** - Cross-origin requests

## 📦 Project Structure

```
course_hub/
├── client/                          # React Frontend
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.jsx
│   │   │   └── Footer.jsx
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   └── CourseContext.jsx
│   │   ├── pages/
│   │   │   ├── HomePage.jsx
│   │   │   ├── CoursesPage.jsx
│   │   │   ├── CourseDetailPage.jsx
│   │   │   ├── StudentDashboard.jsx
│   │   │   ├── LessonPage.jsx
│   │   │   ├── QuizPage.jsx
│   │   │   ├── PaymentPage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   ├── SignupPage.jsx
│   │   │   ├── AboutPage.jsx
│   │   │   └── ContactPage.jsx
│   │   ├── styles/
│   │   │   └── tailwind.css
│   │   ├── App.jsx
│   │   └── index.jsx
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── package.json
├── server/                          # Node.js Backend
│   ├── models/
│   │   ├── User.js
│   │   ├── Course.js
│   │   ├── Payment.js
│   │   └── Enrollment.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── courses.js
│   │   ├── payments.js
│   │   ├── enrollments.js
│   │   └── users.js
│   ├── middleware/
│   │   ├── auth.js
│   │   ├── authorize.js
│   │   └── errorHandler.js
│   ├── index.js
│   ├── .env.example
│   └── package.json
├── package.json                    # Root package.json
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v14+)
- MongoDB
- npm or yarn

### Installation

1. **Clone repository**
```bash
git clone https://github.com/Atifullah431/course_hub.git
cd course_hub
```

2. **Install dependencies**
```bash
npm install
cd server && npm install
cd ../client && npm install
```

3. **Setup environment variables**
```bash
cp server/.env.example server/.env
# Edit server/.env with your configuration
```

4. **Start development server**
```bash
npm run dev
```

Frontend runs on `http://localhost:3000`
Backend runs on `http://localhost:5000`

## 📄 Available Scripts

### Root Level
- `npm run dev` - Start both frontend and backend in development mode
- `npm start` - Start production servers
- `npm run build` - Build frontend for production

### Server
- `npm run dev` - Start with nodemon
- `npm start` - Start production server

### Client
- `npm start` - Start development server
- `npm run build` - Build for production

## 🎯 Page Components to Build

| Page | Status | Features |
|------|--------|----------|
| Home | ⏳ | Hero, Featured Courses, Testimonials, CTA |
| Courses | ⏳ | Course Catalog, Filters, Search |
| Course Detail | ⏳ | Video, Description, Curriculum, Instructor, Buy Button |
| Student Dashboard | ⏳ | Profile, Enrollments, Progress, Certificates |
| Lesson Player | ⏳ | Video Player, Notes, Resources, Next/Prev |
| Quiz | ⏳ | 20 MCQ Questions, Score Calculation |
| Payment | ⏳ | Multi-method Payment, Instructions |
| Auth | ⏳ | Login, Signup Forms |
| About | ⏳ | Mission, Team, Why Choose Us |
| Contact | ⏳ | Form, Location, Social Links |
| Admin Panel | ⏳ | Course Management, User Management |

## 🔐 API Endpoints

### Authentication
- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `POST /api/auth/logout` - User logout

### Courses
- `GET /api/courses` - Get all courses
- `GET /api/courses/:id` - Get course details
- `POST /api/courses` - Create course (Instructor)
- `PUT /api/courses/:id` - Update course (Instructor)
- `DELETE /api/courses/:id` - Delete course (Admin)

### Enrollments
- `POST /api/enrollments` - Enroll in course
- `GET /api/enrollments/user` - Get user's enrollments
- `GET /api/enrollments/:id/progress` - Get course progress
- `POST /api/enrollments/:id/quiz` - Submit quiz
- `GET /api/enrollments/:id/certificate` - Get certificate

### Payments
- `POST /api/payments` - Create payment record
- `PUT /api/payments/:id/confirm` - Confirm payment
- `GET /api/payments/user` - Get user's payments
- `GET /api/payments` - Get all payments (Admin)

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/:id` - Update profile
- `GET /api/users` - Get all users (Admin)

## 💳 Payment Methods Supported

- **EasyPaisa** - Pakistani mobile payment
- **JazzCash** - Pakistani mobile payment
- **Bank Transfer** - Direct bank transfer

## 🔒 Role-Based Access

- **Student** - Can enroll, view courses, take quizzes
- **Instructor** - Can create and manage courses
- **Admin** - Full access to manage system

## 📝 Database Schema

### User Model
```javascript
{
  name, email, password, role, avatar,
  enrolledCourses, createdCourses, 
  socialLinks: { github, linkedin },
  createdAt, updatedAt
}
```

### Course Model
```javascript
{
  title, description, thumbnail, price,
  instructor, lessons, quizzes, ratings,
  students, createdAt, updatedAt
}
```

### Enrollment Model
```javascript
{
  student, course, progress, quizScores,
  certificateIssued, purchaseDate, expiryDate
}
```

### Payment Model
```javascript
{
  user, amount, method, status,
  transactionId, enrollment, createdAt
}
```

## 🎓 Course Structure

Each course includes:
- **Lessons** - Video content with titles and descriptions
- **Quizzes** - 20 multiple-choice questions
- **Resources** - Downloadable files
- **Ratings** - Student reviews and ratings
- **Instructor Info** - Profile and credentials

## 📱 Responsive Design

- Mobile-first approach
- Breakpoints: sm (640px), md (768px), lg (1024px), xl (1280px)
- Touch-friendly interface
- Optimized images and lazy loading

## 🚢 Deployment

### Frontend (Vercel/Netlify)
```bash
npm run build
# Deploy the build folder
```

### Backend (Heroku/Railway)
```bash
# Set environment variables
# Deploy using Git
```

## 📧 Contact & Support

- Email: support@coursehub.com
- WhatsApp: +92-XXX-XXXXXXX
- GitHub: https://github.com/Atifullah431

## 📄 License

MIT License - See LICENSE file for details

## 🤝 Contributing

Contributions are welcome! Please follow the standard Git workflow.

---

**Built with ❤️ by Atifullah431**
