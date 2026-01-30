# Free-API-keys

A curated collection of free (or freemium) public APIs, with quick usage notes and example requests to help you prototype and learn.


## What this repo contains

- A curated index of free or freemium public APIs (by category).
- Notes on authentication, rate limits, and useful links (documentation, sign-up).
- Contribution guidelines so the list stays high-quality and up-to-date.

## Included APIs

1. OpenWeatherMap
   - Category: Weather
   - Description: Global weather data (current weather, forecasts, historical).
   - Auth: API key (free tier available)
   - Quick example:
     ```bash
     export OPENWEATHER_API_KEY="your_api_key"
     curl "https://api.openweathermap.org/data/2.5/weather?q=London&appid=${OPENWEATHER_API_KEY}"
     ```
   - Docs: https://openweathermap.org/api
   - API Key: 24c3f07df526f5a03c6fa099be50a257

2. REST Countries
   - Category: Geolocation / Country data
   - Description: Information about countries (names, capitals, population, flags).
   - Auth: None
   - Quick example:
     ```bash
     curl "https://restcountries.com/v3.1/name/Canada"
     ```
   - Docs: https://restcountries.com

3. NewsAPI
   - Category: News / Headlines
   - Description: Search and retrieve live news headlines and articles from many sources.
   - Auth: API key (free tier with limited requests)
   - Quick example:
     ```bash
     export NEWSAPI_KEY="your_api_key"
     curl "https://newsapi.org/v2/top-headlines?country=us&apiKey=${NEWSAPI_KEY}"
     ```
   - Docs: https://newsapi.org
   - API Key: 92f99b8c1f564c1eacb876692cde29fb

4. NASA API
   - Category: Space / Science
   - Description: Access NASA imagery, astronomy data, and other mission endpoints.
   - Auth: API key (a demo key is available; register for a personal key)
   - Quick example:
     ```bash
     export NASA_API_KEY="DEMO_KEY"
     curl "https://api.nasa.gov/planetary/apod?api_key=${NASA_API_KEY}"
     ```
   - Docs: https://api.nasa.gov
   - API Key: o6ixYloELK4VQaxEDIUtkzWlKzGaNqgab8ZfoeXm

5. JokeAPI
   - Category: Entertainment
   - Description: Programmable jokes (single and two-part jokes, filters by category and flags).
   - Auth: None
   - Quick example:
     ```bash
     curl "https://v2.jokeapi.dev/joke/Any"
     ```
   - Docs: https://jokeapi.dev

6. GitHub API
   - Category: Developer / VCS
   - Description: Access GitHub data (repositories, issues, pulls, users). Useful for automation and integrations.
   - Auth: None for many public endpoints; OAuth or personal access token recommended for higher rate limits and private resources
   - Quick example (unauthenticated:
     ```bash
     curl "https://api.github.com/repos/octocat/Hello-World"
     ```
     Authenticated (token):
     ```bash
     export GH_TOKEN="your_token"
     curl -H "Authorization: token ${GH_TOKEN}" "https://api.github.com/user/repos"
     ```
   - Docs: https://docs.github.com/en/rest

7. JSONPlaceholder
   - Category: Testing / Mock
   - Description: Fake online REST API for testing and prototyping (posts, comments, todos, users).
   - Auth: None
   - Quick example:
     ```bash
     curl "https://jsonplaceholder.typicode.com/posts/1"
     ```
   - Docs: https://jsonplaceholder.typicode.com

## Usage & examples

- Always check provider docs for the latest endpoints and rate limits.
- Store API keys in environment variables or a secrets manager; never commit them.
- Example pattern for a script using an API key:
  ```bash
  export API_KEY="your_api_key"
  curl "https://provider.example/api/endpoint?key=${API_KEY}"
  ```

## How APIs are documented here

Each entry in this repo should include:
- Name
- Category
- Short description
- Authentication (None / API key / OAuth2)
- Free tier limits (if known)
- Example request(s)
- Link to official docs and sign-up
- Any caveats or notes (rate limits, unstable endpoints, geography restrictions)

If you add an API, prefer adding a single Markdown file under `apis/` using the template above, or append to `APIS.md`.

## Contributing

Contributions are welcome — please follow these steps:

1. Fork the repository.
2. Add or update an API entry in `APIS.md` or create a file under `apis/` with:
   - Name
   - Category
   - Short description
   - Auth
   - Free tier
   - Examples
   - Links
3. Open a pull request describing the change.
