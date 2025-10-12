# 🎬 MoviesDatabase API Integration

This project integrates the **MoviesDatabase API**, a powerful RESTful service that provides complete and up-to-date data for over **9 million movies, TV shows, and episodes**, as well as detailed information on **over 11 million actors, crew, and cast members**.  

The API allows developers to access data such as movie details, genres, ratings, biographies, trailers, and award information to build engaging entertainment applications.

---

## 📘 API Overview

The **MoviesDatabase API** is a comprehensive data source that provides:
- Information for movies, series, and episodes, including titles, release dates, runtime, and genres.
- Actor and crew information such as biographies, roles, and known-for titles.
- Ratings, awards, and box office data.
- Filtering, sorting, and pagination capabilities.
- Multiple levels of data detail through the `info` query parameter (`mini_info`, `base_info`, `extendedCast`, etc.).

All endpoints return JSON objects with a consistent structure that includes the `results` key and, when applicable, pagination data (`page`, `next`, `entries`).

---

## 🧩 API Version

**Version:** 1.0  
> (As referenced from the MoviesDatabase API documentation overview section.)

---

## 📚 Available Endpoints

### 🎥 Titles
| Endpoint | Description |
|-----------|--------------|
| `/titles` | Returns an array of titles filtered or sorted according to query parameters. |
| `/titles/{id}` | Returns a specific title (movie/series/episode) by IMDb ID. |
| `/titles/{id}/ratings` | Returns rating information and total votes for a given title. |
| `/titles/x/upcoming` | Returns a list of upcoming movies or shows. |
| `/titles/search/title/{title}` | Searches for titles by name or keyword. |
| `/titles/search/keyword/{keyword}` | Returns titles related to a specific keyword. |

### 🎬 Series & Episodes
| Endpoint | Description |
|-----------|--------------|
| `/titles/series/{id}` | Returns all episodes of a series by IMDb ID. |
| `/titles/series/{id}/{season}` | Returns episodes within a specific season. |
| `/titles/episode/{id}` | Returns details for a single episode. |
| `/titles/seasons/{id}` | Returns the number of seasons for a series. |

### 👤 Actors
| Endpoint | Description |
|-----------|--------------|
| `/actors` | Returns an array of actors (supports pagination). |
| `/actors/{id}` | Returns detailed information for a specific actor by IMDb ID. |

### ⚙️ Utils
| Endpoint | Description |
|-----------|--------------|
| `/title/utils/titleType` | Returns available title types. |
| `/title/utils/genres` | Returns a list of all genres. |
| `/title/utils/lists` | Returns available title lists (e.g., Top Rated, Most Popular). |

---

## 📨 Request and Response Format

### Example Request

```http
GET /titles?list=top_rated_250&limit=5&info=base_info
Host: moviesdatabase.p.rapidapi.com
Headers:
  X-RapidAPI-Key: YOUR_API_KEY
  X-RapidAPI-Host: moviesdatabase.p.rapidapi.com


---


