<div align="center">

# 🐛 Debug-Hub

### The DSA Debugging Platform — Learn. Debug. Battle. Dominate.

[![React](https://img.shields.io/badge/React-18.2-61DAFB?style=flat-square\&logo=react)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat-square\&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=flat-square\&logo=mongodb)](https://mongodb.com/)
[![Socket.IO](https://img.shields.io/badge/Socket.IO-Realtime-010101?style=flat-square\&logo=socket.io)](https://socket.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-412991?style=flat-square\&logo=openai)](https://openai.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

</div>

---

# 🚀 About The Project

Debug-Hub is a full-stack gamified DSA debugging platform where developers solve real buggy code, participate in live coding battles, earn certifications, and improve debugging skills through AI-powered complexity analysis.

Unlike traditional coding platforms that focus only on writing solutions, Debug-Hub emphasizes reading, understanding, and fixing broken code — a crucial real-world engineering skill.

---

# ✨ Features

## 🐛 Bug Challenge System

* Post bugs with code, description, expected output, language, and topic
* Multi-language support:
  * JavaScript
  * Python
  * Java
  * C++
  * C
* Difficulty levels: Easy / Medium / Hard
* AI auto-analyzes time & space complexity (Big-O)
* Community-driven upvoting system
* Mark bugs as solved after accepted fixes

---

## ⚔️ Real-Time Battle Arena

* Admin-created timed coding battles
* Battle states: UPCOMING → LIVE → FINISHED
* Real-time participant tracking using Socket.IO
* Live submission system during battle windows
* Automatic winner detection
* Dedicated battle leaderboard
* Separate battle points system

---

## 🏆 Gamification & Ranking

* Points awarded for solving bugs and winning battles
* Bronze / Silver / Gold certification system
* Milestone badges and achievements
* Global leaderboard + Battle leaderboard
* Public user profiles with follower/following system

---

## 🤖 AI-Powered Analysis

* GPT-4o-mini analyzes submitted buggy code
* Returns:
  * Time Complexity
  * Space Complexity
  * Plain-English explanation
* Handles:
  * Nested loops
  * Recursive functions
  * Recurrence relation derivation
  * Master Theorem applications
* Graceful fallback if API key is not configured
* Every bug posted on the platform is automatically analyzed by GPT-4o-mini:

```json
{
  "timeComplexity": "O(n log n)",
  "spaceComplexity": "O(n)",
  "explanation": "The outer loop runs n times, and the inner binary search runs log n per iteration, giving O(n log n) overall time complexity."
}
🔐 Authentication & SecurityJWT access + refresh token authenticationRefresh token rotationGoogle OAuth 2.0 authenticationFirebase authentication integrationPassword reset via NodemailerAccount lockout after multiple failed attemptsHelmet.js security headersAPI rate limiting protection📊 Personalized RecommendationsTopic-based bug recommendationsRecommendations based on solve historyGraceful fallback for new users🛡️ Admin PanelFull CRUD operations for:UsersBugsSolutionsBattlesBattle creation and managementView all battle submissionsAdmin dashboard controls🏗️ Tech StackCategoryTechnologiesFrontendReact 18, React Router, Framer MotionBackendNode.js, Express.js, Socket.IODatabaseMongoDB, MongooseAuthenticationJWT, Passport.js, Firebase OAuthAI IntegrationOpenAI GPT-4o-miniSecurityHelmet, bcryptjs, express-rate-limitEmail ServiceNodemailerPDF GenerationPDFKit📂 Project ArchitectureBashDebug-Hub-platform/
│
├── backend/                          # Express.js REST API + Socket.IO server
│   │
│   ├── config/
│   │   ├── env.js                    # Environment configuration
│   │   ├── firebase.js               # Firebase Admin SDK setup
│   │   └── passport.js               # Google OAuth strategy
│   │
│   ├── controllers/
│   │   ├── authController.js         # Authentication & JWT handling
│   │   ├── bugController.js          # Bug CRUD + AI analysis
│   │   ├── battleController.js       # Battle management & live events
│   │   ├── solutionController.js     # Solution submission & upvotes
│   │   ├── userController.js         # Profiles, leaderboard, followers
│   │   ├── certificateController.js  # PDF certificate generation
│   │   ├── recommendationController.js # Personalized recommendations
│   │   ├── runCodeController.js      # Code execution endpoint
│   │   └── adminController.js        # Admin CRUD operations
│   │
│   ├── middleware/
│   │   ├── authMiddleware.js         # JWT authentication middleware
│   │   └── adminAuth.js              # Admin authorization middleware
│   │
│   ├── models/
│   │   ├── User.js                   # User schema & gamification
│   │   ├── Bug.js                    # Bug schema with AI fields
│   │   ├── Solution.js               # Solution schema + upvotes
│   │   ├── Battle.js                 # Battle schema & winner logic
│   │   └── BattleSolution.js         # Battle submission model
│   │
│   ├── routes/
│   │   ├── adminRoutes.js            # Admin dashboard & CRUD routes
│   │   ├── authRoutes.js             # Authentication routes
│   │   ├── battleRoutes.js           # Battle management routes
│   │   ├── bugRoutes.js              # Bug challenge routes
│   │   ├── certificateRoutes.js      # Certificate download routes
│   │   ├── recommendationRoutes.js   # Personalized recommendations
│   │   ├── runCode.js                # Code execution routes
│   │   ├── solutionRoutes.js         # Solution submission routes
│   │   └── userRoutes.js             # User profile & leaderboard routes
│   │
│   ├── utils/
│   │   ├── complexityAnalyzer.js     # GPT-4o-mini complexity analysis
│   │   ├── certificationChecker.js   # Certification eligibility logic
│   │   └── sendEmail.js              # Nodemailer email utility
│   │
│   └── server.js                     # Backend entry point
│
├── frontend/                         # React 18 SPA
│   │
│   ├── public/                       # Static assets
│   │
│   ├── src/
│   │   │
│   │   ├── api/
│   │   │   └── axiosInstance.js      # Axios interceptors + auth refresh
│   │   │
│   │   ├── assets/
│   │   │   └── dsaaa.png             # Project assets
│   │   │
│   │   ├── components/               # Reusable UI components
│   │   │   ├── Adminprotected.js
│   │   │   ├── challengeDetails.js
│   │   │   ├── CodeEditor.js
│   │   │   ├── LivesSession.js
│   │   │   ├── Navbar.js
│   │   │   ├── RecommendedBugs.js
│   │   │   └── SolutionCard.js
│   │   │
│   │   ├── context/
│   │   │   └── Authcontext.js        # Global authentication state
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.js
│   │   │   ├── login.js
│   │   │   ├── signup.js
│   │   │   ├── profile.js
│   │   │   ├── userprofile.js
│   │   │   ├── postbug.js
│   │   │   ├── viewbugs.js
│   │   │   ├── viewbug.js
│   │   │   ├── BugSolution.js
│   │   │   ├── Battles.js
│   │   │   ├── BattleRoom.js
│   │   │   ├── BattleLeaderboard.js
│   │   │   ├── leaderboard.js
│   │   │   ├── MySubmissions.js
│   │   │   ├── AllSubmissions.js
│   │   │   ├── ForgotPassword.js
│   │   │   ├── ResetPassword.js
│   │   │   ├── OAuthSuccess.js
│   │   │   ├── ProfileFollowers.js
│   │   │   ├── ProfileFollowing.js
│   │   │   ├── ProfilePoints.js
│   │   │   ├── ProfileUpvotes.js
│   │   │   ├── ProfileBug.js
│   │   │   └── battleSubmissions.js
│   │   │
│   │   │── admin/
│   │   │   ├── AdminDashboard.js
│   │   │   ├── AdminUsers.js
│   │   │   ├── AdminBugs.js
│   │   │   ├── AdminBattles.js
│   │   │   ├── AdminSubmissions.js
│   │   │   ├── adminBattleSubmissions.js
│   │   │   ├── createBattle.js
│   │   │   └── AdminLogin.js
│   │   │
│   │   ├── styles/
│   │   │   └── theme.css             # Global styling
│   │   │
│   │   ├── App.js                    # Application routes
│   │   ├── api.js
│   │   ├── config.js
│   │   ├── firebase.js
│   │   ├── index.js
│   │   └── App.css
│   │
│   ├── .env
│   ├── package.json
│   └── README.md
│
└── README.md
⚙️ Local SetupPrerequisitesNode.js >= 18MongoDBOpenAI API Key (Optional)Google OAuth Credentials (Optional)1️⃣ Clone RepositoryBashgit clone [https://github.com/your-username/Debug-Hub-platform.git](https://github.com/your-username/Debug-Hub-platform.git)
cd Debug-Hub-platform
2️⃣ Backend SetupBashcd backend
npm install
Create .env file:Code snippetPORT=5000
MONGO_URI=your_mongodb_uri

JWT_SECRET=your_jwt_secret
JWT_REFRESH_SECRET=your_refresh_secret

OPENAI_API_KEY=your_openai_key

FRONTEND_URL=http://localhost:3000
Run backend:Bashnpm run dev
3️⃣ Frontend SetupBashcd ../frontend
npm install
npm start
🔐 Security FeaturesJWT Access & Refresh TokensPassword Hashing using bcryptjsHTTP Security Headers using HelmetAPI Rate LimitingGoogle OAuth AuthenticationRefresh Token RotationAccount Lockout ProtectionSecure Password Reset Flow🤝 ContributingContributions are welcome!Bash# Fork the repository
# Create your feature branch
git checkout -b feature/amazing-feature

# Commit changes
git commit -m "Add amazing feature"

# Push changes
git push origin feature/amazing-feature
Then open a Pull Request.📄 LicenseThis project is licensed under the MIT License.Made with ❤️ using MERN Stack + AI⭐ Star this repository if you found it useful!
