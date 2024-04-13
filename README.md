# Video Streaming Application

## Tech Stack

- [React](https://github.com/facebook/react) ∙ [Redux](https://github.com/reduxjs/redux)
  - web client & client data management
- [Node.js](https://github.com/nodejs) ∙ [Expressjs](https://github.com/expressjs/express) ∙ [Jayson](https://github.com/tedeh/jayson)
  - web server & services in service oriented architecure
- [Python](https://github.com/python) ∙ [Scrapy](https://github.com/scrapy/scrapy)
  - web scraper, data pipeline
- [ElasticSearch](https://github.com/elastic/elasticsearch)
  - persisted database for movies
- [Postgres](https://github.com/postgres/postgres) ∙ [Sequelize](https://github.com/sequelize/sequelize)
  - persisted database for users

---

## Project Contents

- single page application web client with React & Redux
- service oriented architecure backend
- REST for client server communication, JSON RPC for inter service communication
- scrape raw movie data from imdb
- provides processed imdb movies data with our movie service API
- persisted ElasticSearch for movie's database for optimized searching capability
- PostgreSQL for user's database

### Functions

- users can register and log in to their account
- landing page has collections of movie for recommendations
- users can search for movies
- users can browse search result by pages
- users can select and view details of a movie
- users can see his/her history of browsed movie
- users can add or remove movie to his/her bookmark

#### Tools & Versions

| Tools         | Versions |
| ------------- | -------- |
| npm           | 6.1.0    |
| pip           | 9.0.1    |
| nodejs        | 10.7.0   |
| python        | 2.7      |
| elasticsearch | 6.3.1    |
| postgres      | 10.5     |

### Building Data Pipeline

#### Data Fetcher

- install dependencies

```terminal
pip install -r requirements.txt
```

- start scraper pipeline for fetching raw data from IMDB, process and store to ElasticSearch

```terminal
cd data-pipeline/imdb_scraper
scrapy crawl "imdb_spider"
```

### Serving Application

#### Movie Service

- dependent on ElasticSearch as data source

- install dependencies & start Movie-Service

```terminal
cd movie-service
npm install
npm start
```

Application will be serving on http://localhost:3230

#### User Service

- dependent on PostgreSQL as data source

- install dependencies & start User-Service

```terminal
cd user-service
npm install
npm start
```

Application will be serving on http://localhost:3130

#### Web Server

- install dependencies & start Web-Server

```terminal
cd web-server
npm install
npm start
```

Application will be serving on http://localhost:3030

#### Web Client

- install dependencies & start application

```terminal
cd web-client
npm install
npm start
```

Application will be serving on http://localhost:3000
