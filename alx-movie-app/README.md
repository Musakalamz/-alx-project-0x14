# 🎬 CineSeek — ALX Project 0x14: Movie Database Explorer

## 📘 Overview
**CineSeek** is a responsive movie discovery web app built with **Next.js**, **TypeScript**, and **Tailwind CSS**.  
It integrates with the **MoviesDatabase API (via RapidAPI)** to allow users to explore, search, and filter movies by title, year, and genre.  

This project is part of the **ALX Software Engineering Program (0x14 - API)** and demonstrates skills in:
- RESTful API integration  
- Modular frontend architecture  
- Secure environment management  
- Responsive UI design  

---

## 🧠 Learning Objectives
- Understand and document RESTful API endpoints  
- Use TypeScript interfaces to define data models  
- Build reusable React components and layouts  
- Fetch and render API data securely from a server route  
- Implement loading and error states  
- Apply responsive design with Tailwind CSS  
- Manage environment variables securely  

---

## ⚙️ Tech Stack
| Category | Technology |
|-----------|-------------|
| Framework | **Next.js 14** |
| Language | **TypeScript** |
| Styling | **Tailwind CSS** |
| Icons | **Font Awesome** |
| API | **MoviesDatabase API (RapidAPI)** |
| Version Control | **Git & GitHub** |
| Runtime | **Node.js v16+** |

---

## 🧩 Tasks Overview

### **Task 0 — Reading API Documentation**
- Review the MoviesDatabase API docs via RapidAPI.  
- Document endpoints, authentication, and query parameters.  
- Understand request/response formats and error codes.

### **Task 1 — Bootstrap Movie App**
- Initialize a new Next.js + TypeScript + Tailwind project.
- Create base directories for components, layouts, and interfaces.
- Configure ESLint and TypeScript aliases.
- Commit initial setup to Git.

### **Task 2 — Header, Footer, and Layout**
- Implement shared layout structure across all pages.
- Add navigation bar, footer, and home landing page.
- Wrap all pages with `Layout` in `_app.tsx`.

### **Task 3 — Movies Page**
- Create `/movies` route with filters and pagination.
- Fetch movie data from API via a server route.
- Display results using reusable components.
- Handle loading and error states gracefully.

---

## 🧱 System Architecture (Markdown Diagram)
```text
┌───────────────────────────────────────────────┐
│                  User Interface               │
│     (React Components rendered by Next.js)    │
│  ┌─────────────────────────────────────────┐  │
│  │ Components/                             │  │
│  │   ├── commons/ → Buttons, Cards, etc.   │  │
│  │   └── layouts/ → Header, Footer, Layout │  │
│  └─────────────────────────────────────────┘  │
│                     │                          │
│                     ▼                          │
│          ┌─────────────────────────┐           │
│          │ Routing Layer (pages/)  │           │
│          │ index.tsx, movies/, api/│           │
│          └─────────────────────────┘           │
│                     │                          │
│                     ▼                          │
│          ┌─────────────────────────┐           │
│          │ Server/API Proxy Layer  │           │
│          │ pages/api/fetch-movies  │           │
│          └─────────────────────────┘           │
│                     │                          │
│                     ▼                          │
│          ┌─────────────────────────┐           │
│          │ Type Layer (interfaces/) │           │
│          │ Defines data structures │           │
│          └─────────────────────────┘           │
│                     │                          │
│                     ▼                          │
│       ┌────────────────────────────────────┐   │
│       │ Configuration & Environment Layer  │   │
│       │ (.env.local, next.config.js, etc.) │   │
│       └────────────────────────────────────┘   │
│                     │                          │
│                     ▼                          │
│          ┌────────────────────────────┐         │
│          │ External API (RapidAPI)   │          │
│          │ MoviesDatabase API source │          │
│          └────────────────────────────┘         │
└───────────────────────────────────────────────┘