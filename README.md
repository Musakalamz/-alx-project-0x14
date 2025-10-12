# MoviesDatabase API Documentation

---

## API Overview

The **MoviesDatabase API** provides a comprehensive and frequently updated collection of data for over **9 million titles** (movies, series, and episodes) and **11 million actors/crew members**. It's an excellent resource for building applications that need detailed information, including **YouTube trailer URLs, awards, full biographies, ratings, and box office data.**

Key features:
* **Vast Dataset:** Over 9M titles and 11M actors/crew.
* **Data Freshness:** Recent titles are updated weekly; ratings and light episode data are updated daily.
* **Extensive Filtering:** Supports filtering by title type, year range, genre, and predefined lists (e.g., *most popular*, *top rated*).
* **Customizable Responses (Senior Developer Note):** The `info` query parameter allows for precise control over the data returned in a title object, significantly optimizing payload size and network performance.

---

## API Version

The API documentation does not explicitly state a version number (e.g., `v1`, `v2`).

---

## Available Endpoints

The API is structured logically around **Titles**, **Actors**, **Search**, and **Utils**.

### Titles Endpoints

| Endpoint | Path | Description |
| :--- | :--- | :--- |
| **Titles - Multiple** | `/titles` | Returns an array of titles based on filters/sorting. |
| **Title By ID** | `/titles/{id}` | Returns a single title's details by its IMDb ID. |
| **Title Rating** | `/titles/{id}/ratings` | Returns the title's rating and vote count. |
| **Seasons and Episodes (Series)** | `/titles/series/{id}` | Returns an array of light episodes (ID, number, season) for a series. |
| **Episode** | `/titles/episode/{id}` | Returns details for a single episode by its IMDb ID. |
| **Upcoming Titles** | `/titles/x/upcoming` | Returns an array of titles scheduled for future release. |

### Search Endpoints

| Endpoint | Path | Description |
| :--- | :--- | :--- |
| **Titles by Keyword** | `/titles/search/keyword/{keyword}` | Searches titles using a specific keyword. |
| **Titles by Title** | `/titles/search/title/{title}` | Searches titles using a full or partial title string. Supports exact match via `exact` query param. |

### Actors Endpoints

| Endpoint | Path | Description |
| :--- | :--- | :--- |
| **Actors** | `/actors` | Returns an array of actors based on limits/pagination. |
| **Actor By Id** | `/actors/{id}` | Returns full details for a single actor by their IMDb ID. |

### Utility Endpoints (Metadata)

| Endpoint | Path | Description |
| :--- | :--- | :--- |
| **Title Type** | `/title/utils/titleType` | Returns an array of valid title types for use in filters. |
| **Genres** | `/title/utils/genres` | Returns an array of valid genres for use in filters (Note: case-sensitive, must be capitalized). |
| **Titles Lists** | `/title/utils/lists` | Returns options for the `list` query parameter (e.g., `most_pop_movies`, `top_rated_250`). |

---

## Request and Response Format

All successful API requests return a JSON object with a primary key of **`results`**, which contains the main data array. Endpoints supporting pagination will include additional keys: **`page`**, **`next`**, and **`entries`**.

### Request Query Parameters (Senior Developer Note)

The API is highly flexible, supporting numerous optional query parameters for filtering and controlling the response payload.

| Parameter | Type | Default | Key Functionality |
| :--- | :--- | :--- | :--- |
| **`info`** | `STRING` | `mini_info` | **Payload Customization.** Accepts predefined options (e.g., `base_info`, `extendedCast`, `awards`) or *any* specific key from the full `title` object model. Use this to design lean response models. |
| **`limit`** | `NUMBER` | `10` | Pagination limit (Max 50 objects per page). |
| **`page`** | `NUMBER` | `1` | Pagination offset. |
| **`titleType`** | `STRING` | - | Filter by title type (e.g., `movie`, `tvSeries`). Options from `/title/utils/titleType`. |
| **`genre`** | `STRING` | - | Filter by genre (Case-Sensitive, e.g., `Action`). Options from `/title/utils/genres`. |
| **`sort`** | `STRING` | - | Sorts the result (e.g., `year.incr`, `year.decr`). |
| **`list`** | `STRING` | `titles` | Queries predefined collections (e.g., `most_pop_movies`). Options from `/title/utils/lists`. |

### Response Model Examples

#### 1. Titles - Using `info=mini_info` (Default)

The default **`mini_info`** is an excellent lightweight model for list views:

```json
{
  "results": [
    {
      "titleText": "...",
      "id": "tt0000270",
      "primaryImage": "...",
      "titleType": "...",
      "releaseDate": "..."
    }
    // ... more titles
  ],
  "page": 1,
  "next": "/titles?page=2&limit=10",
  "entries": 9000000
}
