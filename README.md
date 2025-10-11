# 🎬 CineSeek – Modern Movie Discovery App  
**Project:** ProDev Frontend – API Explorer: Mastering RESTful Connections  
**Average:** 115.0%  
**Weight:** 1  
**Duration:** Oct 6 – Oct 13, 2025  

![Next.js](https://img.shields.io/badge/Next.js-14-blue)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)
![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-3.4-06B6D4)
![Status](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-green)

---

## 🧠 Project Overview

**CineSeek** is a **modern movie discovery web application** built with **Next.js**, **TypeScript**, and **Tailwind CSS**.  
It integrates the **MoviesDatabase API** to fetch, search, and display movie details dynamically.  

The project demonstrates:
- Proper API documentation reading and implementation  
- TypeScript interface design for API data  
- Reusable React component creation  
- Responsive layouts using Tailwind CSS  
- Secure API key handling via environment variables  
- Pagination, filtering, and error handling for real-world performance  

---

## 🎯 Learning Objectives

- Understand and use RESTful APIs  
- Implement TypeScript interfaces for typed API responses  
- Build reusable, modular components  
- Use Tailwind CSS for responsive UIs  
- Manage state, filtering, and pagination  
- Implement proper error handling and loading states  
- Use Next.js API routes for secure data fetching  
- Handle environment variables for API key management  

---

## 🧰 Tech Stack

| Category | Tools |
|-----------|--------|
| **Framework** | Next.js 14 (Pages Router) |
| **Language** | TypeScript |
| **Styling** | Tailwind CSS |
| **Icons** | Font Awesome |
| **API Source** | MoviesDatabase API |
| **Version Control** | Git + GitHub |
| **Runtime** | Node.js v16+ |

---

## 📁 Project Architecture

```bash
alx-movie-app/
├── components/
│   ├── commons/
│   │   ├── Button.tsx
│   │   ├── Loading.tsx
│   │   └── MovieCard.tsx
│   └── layouts/
│       ├── Footer.tsx
│       ├── Header.tsx
│       └── Layout.tsx
├── interfaces/
│   └── index.ts
├── pages/
│   ├── api/
│   │   └── fetch-movies.ts
│   ├── movies/
│   │   └── index.tsx
│   ├── _app.tsx
│   └── index.tsx
├── public/
├── styles/
│   └── globals.css
├── .env.local
├── .eslintrc.json
├── .gitignore
├── next.config.js
├── package.json
└── tsconfig.json

---

## Review API Documentation
The **MoviesDatabase API** is a RESTful web service that provides structured access to a wide range of movie data.  
It enables developers to retrieve, search, and filter movie titles using various parameters such as **year**, **genre**, or **title keyword**.  

Developers can use this API to:
- Fetch lists of movies with pagination
- Access detailed movie information including ratings, genres, and release dates
- Perform search queries based on titles or keywords
- Filter movies by release year or genre  

All API responses are returned in **JSON format**, making them ideal for integration with front-end applications like **Next.js** and **TypeScript** projects.

---

## API Overview
The **MoviesDatabase API** allows seamless access to thousands of movie titles and related data through RESTful endpoints.  
It provides features for retrieving popular movies, filtering results by criteria, searching by title, and viewing detailed metadata for individual films.

Key features include:
- Pagination support for browsing large datasets
- Search functionality with flexible parameters
- JSON response format for easy parsing
- Support for genre and year filtering
- Well-documented request and response structures  

---

## API Version
**Version:** `v1`  

This version provides stable endpoints for retrieving movie information, supporting filters, search queries, and detailed metadata about each movie. Future updates may extend features but maintain backward compatibility.

---

## Available Endpoints

| Endpoint | Method | Description |
|-----------|---------|-------------|
| `/titles` | GET | Retrieves a list of movies with optional filters like year, genre, and pagination. |
| `/titles/:id` | GET | Returns detailed information for a single movie based on its unique ID. |
| `/genres` | GET | Returns all available movie genres to help filter movie queries. |
| `/search` | GET | Searches for movies by title or keyword. |

Each endpoint supports query parameters that enhance filtering and searching capabilities.

---

## Request and Response Format

### Example Request
```bash
GET https://api.themoviedb.org/v1/titles?year=2024&genre=action&page=1
Headers:
  Accept: application/json
  Authorization: Bearer YOUR_API_KEY

{
  "page": 1,
  "total_pages": 50,
  "results": [
    {
      "id": "tt8765432",
      "title": "Action Reborn",
      "year": 2024,
      "genre": ["Action", "Adventure"],
      "rating": 8.1,
      "poster": "https://image.url/actionreborn.jpg"
    }
  ]
}

### Example TypeScript interface 
```bash
interface Movie {
  id: string;
  title: string;
  year: number;
  genre: string[];
  rating: number;
  poster: string;
}

interface ApiResponse {
  page: number;
  total_pages: number;
  results: Movie[];
}

---

## Authentication 

All requests to the MoviesDatabase API require authentication using an API key.
You must include your key securely in the request headers to access data.

Steps:

1. Obtain your API key from the MoviesDatabase platform.


2. Create a .env.local file in your project’s root directory.


3. Store your key as:

MOVIE_API_KEY=your_api_key_here


4. Use it in your code as:

const apiKey = process.env.MOVIE_API_KEY;


5. Add it to your request headers:

Authorization: Bearer YOUR_API_KEY



> ⚠️ Important: Never expose your API key in public repositories. Always use environment variables to secure it.

---

Error Handling

Common Error Codes

Status Code	Meaning	Description

400	Bad Request	The request parameters are invalid or malformed.
401	Unauthorized	Missing or invalid API key in the header.
404	Not Found	The requested resource or endpoint does not exist.
500	Internal Server Error	An unexpected error occurred on the server.


Example Error Handling in TypeScript

try {
  const response = await fetch("/api/fetch-movies");
  if (!response.ok) {
    throw new Error(`Request failed with status ${response.status}`);
  }
  const data = await response.json();
} catch (error) {
  console.error("Error fetching movies:", error);
}

Best Practices:

Always include try/catch blocks when making API calls.

Display user-friendly error messages for failed requests.

Use a loading component for pending states.



---

Usage Limits and Best Practices

Usage Limits

The API enforces rate limiting (approx. 50 requests per minute).

Exceeding this limit will result in temporary request blocking (429 Too Many Requests).


Best Practices

Use pagination (page, limit) to manage large data requests efficiently.

Cache frequently accessed data to reduce API load.

Store API keys securely in environment variables.

Always check for and handle error responses gracefully.

Define TypeScript interfaces to ensure type safety for all data structures.

Implement responsive layouts when displaying API data in front-end applications.