# 🎬 CineSeek — ALX Project 0x14: API Explorer (Movies Database App)

## 📘 Overview
**CineSeek** is a modern, responsive movie discovery web app built with **Next.js**, **TypeScript**, and **Tailwind CSS**.  
It integrates with the **MoviesDatabase API (via RapidAPI)** to allow users to explore, search, and filter movies by year, title, and genre.  

This project demonstrates mastery in **RESTful API integration**, **modular architecture**, and **secure environment management**, developed as part of the **ALX Software Engineering Program**.

---

## 🧠 Learning Objectives
By completing this project, you will learn how to:
- Consume and handle data from RESTful APIs  
- Use **TypeScript interfaces** for strict typing  
- Build **modular React components** for scalability  
- Apply **responsive design** using Tailwind CSS  
- Implement **secure API key handling** using `.env.local`  
- Manage **errors and loading states** effectively  
- Apply **clean architecture** for maintainable front-end apps  

---

## ⚙️ Tech Stack
| Category | Technology |
|-----------|-------------|
| Framework | **Next.js 14** |
| Language | **TypeScript** |
| Styling | **Tailwind CSS** |
| Icons | **Font Awesome** |
| API Source | **MoviesDatabase API (RapidAPI)** |
| Version Control | **Git & GitHub** |
| Runtime | **Node.js v16+** |

---

## 🧱 System Architecture (Markdown Diagram)

Below is the **logical architecture diagram** represented in markdown for GitHub rendering clarity:

### **CineSeek System Architecture**
```text
┌───────────────────────────────────────────────┐
│                  User Interface               │
│    (React Components rendered by Next.js)     │
│                                               │
│  ┌─────────────────────────────────────────┐  │
│  │ Components/                             │  │
│  │   ├── commons/  → Buttons, Cards, etc.  │  │
│  │   └── layouts/  → Header, Footer, Layout│  │
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
│          │  pages/api/fetch-movies │           │
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


---

alx-project-0x14/
│
├── README.md                       # Main documentation file
│
└── alx-movie-app/
    ├── components/
    │   ├── commons/                # Reusable UI components
    │   │   ├── Button.tsx
    │   │   ├── Loading.tsx
    │   │   └── MovieCard.tsx
    │   └── layouts/                # Page structure components
    │       ├── Header.tsx
    │       ├── Footer.tsx
    │       └── Layout.tsx
    │
    ├── interfaces/                 # TypeScript interfaces
    │   └── index.ts
    │
    ├── pages/                      # Next.js routes
    │   ├── api/
    │   │   └── fetch-movies.ts     # Secure API route to RapidAPI
    │   ├── movies/
    │   │   └── index.tsx           # Movies listing page
    │   ├── _app.tsx                # Root application wrapper
    │   └── index.tsx               # Landing page
    │
    ├── public/                     # Static assets (logos, icons)
    │
    ├── styles/                     # Global styles and Tailwind setup
    │   └── globals.css
    │
    ├── .env.local                  # API key (ignored by Git)
    ├── next.config.js              # Next.js configuration
    ├── package.json                # Dependencies and scripts
    ├── tsconfig.json               # TypeScript settings
    └── tailwind.config.js          # Tailwind CSS configuration

---

