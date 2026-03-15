# alitrack-platform
version: '3.8'
services:
  db:
    image: postgres:15-alpine
    environment:
      POSTGRES_PASSWORD: password123
  backend:
    build: ./backend
    ports: ["8080:8080"]
    depends_on: [db]
  frontend:
    build: ./frontend
    ports: ["3000:3000"]
    
