# CONTAINERIZED URL SHORTENER PLATFORM

A high-performance URL shortener service build with **FastAPI** and **PostgreSQL**

# 🚀 Features
- **FastAPI Backend :** Asynchronous API for high-speed shortening and redirection.
- **PostgreSQL Storage :** Relational database to store URL mappings safely.
- **Data Persistence :** Uses Docker Volumes to ensure data isn't lost when containers stop.
- **Container Orchestration :** One-command deployment via Docker compose.
- **Auto-Documentation :** Interactive API dcos via Swagger UI 

## 🛠 Tech Stack
| Layer | Technology |
|-------|------------|
| Language | Python 3.11 |
| Framework | FastAPI |
| Database | PostgreSQL 15 |
| ORM | SQLAlchemy |
| Infrastructure | Docker, Docker Compose |


## 🚦 Getting Started

### Prerequisites 
- Docker and Docker Compose installed 

### Installation
1. Clone the repository:
```bash
git clone https://github.com/YOUR_USERNAME/url-shortener-docker.git
cd url-shortener-docker

2. Spin up the containers:
```bash
docker-compose up -d --build
```

3. The API will be available at `http://localhost:8000`
4. Swagger UI at `http://localhost:8000/docs`

## 🧪Testing the API 

**Shorten a URL:**
```bash
curl -X POST http://localhost:8000/shorten\
   -H "Content-Type: application/json" \
   -d '{"url":"https://www.google.com"}'
```

## 💾 Volume Persistence 
This project uses a named volume `pgdata`. Even after running `docker-compose down` , your  shortened URLs remain saved in Dokcer-managed local storage.

## 🏗 System Architecture 
The API and database run on an isolated **Docker Bridge Network**. Only the FastAPI service exposes a port to the host - PostgreSQL is unreachable from the public internet, with only the API conatainer permitted to communicate with it . 
