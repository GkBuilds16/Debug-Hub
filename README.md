<div align="center">

# 🐛 Debug-Hub

### The DSA Debugging Platform — Learn. Debug. Battle. Dominate.

[![React](https://img.shields.io/badge/React-18.2-61DAFB?style=flat-square&logo=react&logoColor=black)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat-square&logo=node.js)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?style=flat-square&logo=mongodb)](https://mongodb.com/)
[![Socket.IO](https://img.shields.io/badge/Socket.IO-Realtime-010101?style=flat-square&logo=socket.io)](https://socket.io/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-412991?style=flat-square&logo=openai)](https://openai.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

---

</div>

## 🚀 About The Project

DebugDSA is a full-stack gamified DSA debugging platform where developers solve real buggy code, participate in live coding battles, earn certifications, and improve debugging skills through AI-powered complexity analysis.

Unlike traditional coding platforms that focus only on writing solutions, DebugDSA emphasizes reading, understanding, and fixing broken code — a crucial real-world engineering skill.

---

## ✨ Features

### 🐛 Bug Challenge System

* Post bugs with code, description, expected output, language, and topic
* Multi-language support: JavaScript, Python, Java, C++, and C
* Difficulty levels: Easy / Medium / Hard
* AI auto-analyzes time & space complexity (Big-O)
* Community-driven upvoting system
* Mark bugs as solved after accepted fixes

---

### ⚔️ Real-Time Battle Arena

* Admin-created timed coding battles
* Battle states: `UPCOMING` -> `LIVE` -> `FINISHED`
* Real-time participant tracking using Socket.IO
* Live submission system during battle windows
* Automatic winner detection
* Dedicated battle leaderboard
* Separate battle points system

---

### 🏆 Gamification & Ranking

* Points awarded for solving bugs and winning battles
* Bronze / Silver / Gold certification system
* Milestone badges and achievements
* Global leaderboard + Battle leaderboard
* Public user profiles with follower/following system

---

### 🤖 AI-Powered Analysis

* GPT-4o-mini analyzes submitted buggy code and returns:
  * Time Complexity
  * Space Complexity
  * Plain-English explanation
* Handles nested loops, recursive functions, recurrence relation derivation, and Master Theorem applications.
* Graceful fallback if API key is not configured.

Every bug posted on the platform is automatically analyzed by the engine:

```json
{
  "timeComplexity": "O(n log n)",
  "spaceComplexity": "O(n)",
  "explanation": "The outer loop runs n times, and the inner binary search runs log n per iteration, giving O(n log n) overall time complexity."
}

