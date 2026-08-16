Smart City Platform
Enterprise-grade Smart City Operations Management System

https://img.shields.io/badge/Docker-Ready-blue.svg
https://img.shields.io/badge/Next.js-14.2-black
https://img.shields.io/badge/NestJS-10.0-red
https://img.shields.io/badge/MongoDB-8.5-green
https://img.shields.io/badge/Redis-Alpine-red
https://img.shields.io/badge/License-Proprietary-red.svg
📋 Table of Contents
Overview

Architecture

Tech Stack

Features

Quick Start

Installation

Configuration

Development

Testing

Deployment

API Documentation

Contributing

License

🏙️ Overview
Smart City Platform is a comprehensive, enterprise-grade solution for modern city operations management. It provides real-time monitoring, incident management, analytics, and governance capabilities through an intuitive web interface.

Why Smart City Platform?
🚀 Real-time Operations: Live monitoring and instant incident response

📊 Data-Driven Decisions: Advanced analytics and visualization

🔒 Enterprise Security: JWT authentication, RBAC, and secure APIs

🌐 Scalable Architecture: Microservices ready for city-wide deployment

🎨 Modern UX: Responsive, intuitive interface built with Next.js

🔄 Real-time Communication: WebSocket integration for live updates

┌─────────────────────────────────────────────────────────────────┐
│                         Client Browser                         │
└─────────────────────────────┬───────────────────────────────────┘
                              │
                    ┌─────────▼─────────┐
                    │   Nginx (Port 80) │
                    │  Reverse Proxy    │
                    └─────────┬─────────┘
                              │
              ┌───────────────┼───────────────┐
              │               │               │
    ┌─────────▼─────────┐ ┌───▼───┐ ┌─────────▼─────────┐
    │   Frontend        │ │  API  │ │    Backend        │
    │   (Next.js)       │ │       │ │    (NestJS)       │
    │   Port: 3000      │ │       │ │    Port: 5000     │
    └───────────────────┘ └───────┘ └─────────┬─────────┘
                                              │
                              ┌───────────────┼───────────────┐
                              │               │               │
                    ┌─────────▼─────────┐ ┌───▼───┐ ┌─────────▼─────────┐
                    │    MongoDB        │ │ Redis │ │    BullMQ         │
                    │    Database       │ │ Cache │ │    Queue          │
                    │    Port: 27017    │ │6379   │ │    Processor      │
                    └───────────────────┘ └───────┘ └───────────────────┘
                     Tech Stack
Frontend
Technology	Version	Purpose
Next.js	14.2.5	React Framework
React	18.3.1	UI Library
TypeScript	5.5.4	Type Safety
Redux Toolkit	2.2.7	State Management
React Query	5.51.23	Data Fetching
TailwindCSS	3.4.10	Styling
Leaflet	1.9.4	Maps & Geospatial
Lucide React	0.428.0	Icons
Backend
Technology	Version	Purpose
NestJS	10.4.0	Backend Framework
TypeScript	5.5.4	Type Safety
MongoDB	8.5.3	Database
Mongoose	8.5.3	ODM
Redis	5.4.1	Cache & Queue
BullMQ	5.12.0	Job Queue
JWT	10.2.0	Authentication
Socket.io	4.7.5	WebSockets
Infrastructure
Technology	Version	Purpose
Docker	Latest	Containerization
Nginx	Alpine	Reverse Proxy
MongoDB	Latest	Database
Redis	Alpine	Cache
✨ Features
Core Features
✅ Real-time Dashboard - Live city status monitoring

✅ Interactive Maps - Leaflet-powered geospatial visualization

✅ Incident Management - Report, track, and resolve incidents

✅ Analytics Engine - Advanced data visualization and reporting

✅ Authentication - JWT-based secure access control

✅ Role-Based Access - Granular permission management

✅ WebSocket Integration - Real-time updates and notifications

✅ Queue Management - Background job processing with BullMQ

✅ Responsive Design - Mobile-first, fully responsive

✅ Dark/Light Mode - User preference support

Advanced Features
🚨 Alert System - Real-time notifications and alerts

📊 Data Visualization - Charts, graphs, and dashboards

🔄 Live Updates - WebSocket-powered real-time data

📈 Performance Metrics - System and city performance tracking

🔍 Advanced Search - Full-text search capabilities

📱 Mobile Ready - Responsive design for all devices

🚀 Quick Start
Using Docker (Recommended)
bash
# Clone repository
git clone https://github.com/yourusername/smart-city-platform.git
cd smart-city-platform

# Copy environment configuration
cp backend/.env.example backend/.env

# Start all services
docker-compose up -d

# Access the application
open http://localhost
Manual Installation
bash
# Frontend
cd frontend
npm install
npm run dev

# Backend
cd backend
npm install
npm run start:dev
📦 Installation
Prerequisites
Docker & Docker Compose (Recommended)

Node.js 18+

npm or yarn

Git

4GB+ RAM (8GB recommended)

Step-by-Step Installation
1. Clone Repository
bash
git clone https://github.com/yourusername/smart-city-platform.git
cd smart-city-platform
2. Environment Setup
bash
# Create environment files
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env.local

# Edit configurations
nano backend/.env
3. Start with Docker
bash
# Build and start services
docker-compose up -d --build

# Verify services
docker-compose ps
4. Access Application
Frontend: http://localhost

Backend API: http://localhost:5000

API Documentation: http://localhost:5000/api/docs

⚙️ Configuration
Backend Configuration (backend/.env)
env
# Server
PORT=5000
NODE_ENV=production

# Database
MONGO_URI=mongodb://mongodb:2717/smartcity

# Redis
REDIS_HOST=redis
REDIS_PORT=6379

# JWT Authentication
JWT_SECRET=your_super_secret_key_here
JWT_EXPIRES_IN=7d

# CORS
CORS_ORIGIN=http://localhost:3000,http://localhost:80
Frontend Configuration (frontend/.env.local)
env
# API URLs
NEXT_PUBLIC_API_URL=http://localhost:5000/api
NEXT_PUBLIC_WS_URL=ws://localhost:5000

# Map Services (Optional)
NEXT_PUBLIC_MAPBOX_TOKEN=your_mapbox_token
🛠️ Development
Frontend Development
bash
cd frontend

# Install dependencies
npm install

# Start development server
npm run dev

# Lint and format
npm run lint
npm run format

# Build for production
npm run build

# Preview production build
npm run start
Backend Development
bash
cd backend

# Install dependencies
npm install

# Start development server
npm run start:dev

# Lint and format
npm run lint
npm run format

# Build for production
npm run build

# Start production server
npm run start:prod
Database Management
bash
# MongoDB shell
docker-compose exec mongodb mongosh

# Redis CLI
docker-compose exec redis redis-cli

# Backup database
docker-compose exec mongodb mongodump --out /data/backup

# Restore database
docker-compose exec mongodb mongorestore /data/backup
🧪 Testing
Frontend Tests
bash
cd frontend

# Run tests
npm run test

# Watch mode
npm run test:watch

# Coverage report
npm run test:coverage
Backend Tests
bash
cd backend

# Unit tests
npm run test

# Watch mode
npm run test:watch

# Coverage report
npm run test:cov

# E2E tests
npm run test:e2e
API Testing
bash
# Test health endpoint
curl http://localhost:5000/health

# Test authentication
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"admin@city.gov","password":"password123"}'
🚢 Deployment
Production Docker Deployment
bash
# Build production images
docker-compose -f docker-compose.prod.yml build

# Start production services
docker-compose -f docker-compose.prod.yml up -d

# Scale services
docker-compose -f docker-compose.prod.yml up -d --scale backend=3

# Monitor logs
docker-compose -f docker-compose.prod.yml logs -f
Kubernetes Deployment
bash
# Apply configurations
kubectl apply -f k8s/

# Check status
kubectl get pods
kubectl get services

# Scale deployment
kubectl scale deployment smart-city-backend --replicas=3
CI/CD Pipeline (GitHub Actions)
yaml
name: Deploy to Production

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Build and Deploy
        run: |
          docker-compose build
          docker-compose up -d
📚 API Documentation
Authentication Endpoints
Method	Endpoint	Description
POST	/api/auth/register	Register new user
POST	/api/auth/login	User login
POST	/api/auth/refresh	Refresh token
POST	/api/auth/logout	User logout
GET	/api/auth/profile	Get user profile
City Operations
Method	Endpoint	Description
GET	/api/city/status	Get city status
GET	/api/city/incidents	List incidents
POST	/api/city/incidents	Report incident
GET	/api/city/incidents/:id	Get incident
PUT	/api/city/incidents/:id	Update incident
DELETE	/api/city/incidents/:id	Delete incident
Analytics
Method	Endpoint	Description
GET	/api/analytics/dashboard	Dashboard metrics
GET	/api/analytics/reports	Generate reports
GET	/api/analytics/historical	Historical data
WebSocket Events
Event	Description
incident:new	New incident reported
incident:update	Incident updated
status:change	City status changed
alert:critical	Critical alert
notification:new	New notification
For complete API documentation, visit /api/docs after starting the server.

🤝 Contributing
We welcome contributions! Please follow these steps:

Fork the repository

Create a feature branch

bash
git checkout -b feature/amazing-feature
Commit changes

bash
git commit -m "feat: add amazing feature"
Push to branch

bash
git push origin feature/amazing-feature
Open a Pull Request

Development Guidelines
Frontend: Use functional components with hooks

Backend: Follow NestJS module pattern

Testing: Write unit and integration tests

Documentation: Update API documentation

Commit Messages: Follow conventional commits

📊 Project Status
Current Version: v1.0.0
Component	Status	Coverage
Frontend	✅ Stable	85%
Backend	✅ Stable	92%
API	✅ Stable	95%
Database	✅ Stable	-
WebSocket	✅ Stable	-
Queue	✅ Beta	80%
🔒 Security
Security Features
✅ JWT-based authentication

✅ Role-based access control (RBAC)

✅ Password hashing with bcrypt

✅ Input validation and sanitization

✅ CORS configuration

✅ Rate limiting

✅ Security headers

✅ Environment variable management

Report Security Issues
Please report security vulnerabilities to security@smartcity.com. Do not create public issues for security concerns.

