# MedShakti - AI-Powered Generic Medicine Platform

<div align="center">

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white)
![Dart](https://img.shields.io/badge/dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white)

![PostgreSQL](https://img.shields.io/badge/postgresql-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=for-the-badge&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white)

![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)

</div>

MedShakti is a comprehensive healthcare platform that helps users find affordable generic alternatives to branded medicines through AI-powered prescription scanning and Jan Aushadhi store locator services.

## 🏗️ System Architecture

### Tech Stack
<div align="center">

**Backend Technologies**
<br>
![Python](https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=flat-square&logo=django&logoColor=white)
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=flat-square&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![Celery](https://img.shields.io/badge/celery-%23a9cc54.svg?style=flat-square&logo=celery&logoColor=ddf4a4)

**Frontend Technologies**
<br>
![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=flat-square&logo=Flutter&logoColor=white)
![Dart](https://img.shields.io/badge/dart-%230175C2.svg?style=flat-square&logo=dart&logoColor=white)

**Database & Cache**
<br>
![PostgreSQL](https://img.shields.io/badge/postgresql-%23316192.svg?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/redis-%23DD0031.svg?style=flat-square&logo=redis&logoColor=white)

**DevOps & Infrastructure**
<br>
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat-square&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/nginx-%23009639.svg?style=flat-square&logo=nginx&logoColor=white)

**AI & Cloud Services**
<br>
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=flat-square&logo=TensorFlow&logoColor=white)
![OpenCV](https://img.shields.io/badge/opencv-%23white.svg?style=flat-square&logo=opencv&logoColor=white)
![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=flat-square&logo=google-cloud&logoColor=white)

</div>

### Microservices Architecture
- **Auth Service** - User authentication and authorization
- **Medicine Service** - Medicine database and alternatives
- **Store Service** - Jan Aushadhi store management
- **Prescription Service** - OCR and prescription processing  
- **Notification Service** - Push notifications and alerts
- **API Gateway** - Central request routing and load balancing

### Database Layer
- **PostgreSQL** - Separate databases for each microservice
- **Redis** - Caching and session management

### Infrastructure
- **Docker** - Containerized deployment
- **Nginx** - Load balancer and reverse proxy

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose installed
- Git for version control
- 8GB+ RAM recommended

### 1. Clone Repository
```bash
git clone <repository-url>
cd medshakti
```

### 2. Environment Setup
Create environment files for each service:

```bash
# Create .env files for each service
touch services/auth_service/.env
touch services/medicine_service/.env
touch services/store_service/.env
touch services/prescription_service/.env
touch services/notification_service/.env
touch services/api_gateway/.env
```

### 3. Start All Services
```bash
# Build and start all services
docker-compose up --build

# Or run in detached mode
docker-compose up -d --build
```

### 4. Verify Installation
- **API Gateway**: http://localhost:8000
- **Auth Service**: http://localhost:8001
- **Medicine Service**: http://localhost:8002
- **Store Service**: http://localhost:8003
- **Prescription Service**: http://localhost:8004
- **Notification Service**: http://localhost:8005
- **Nginx Load Balancer**: http://localhost:80

## 📁 Project Structure

```
medshakti/
├── services/
│   ├── auth_service/           # User authentication & authorization
│   ├── medicine_service/       # Medicine database & alternatives
│   ├── store_service/          # Jan Aushadhi store management
│   ├── prescription_service/   # OCR & prescription processing
│   ├── notification_service/   # Push notifications
│   └── api_gateway/           # Request routing & load balancing
├── infrastructure/
│   ├── nginx/                 # Load balancer configuration
│   ├── postgres/              # Database initialization scripts
│   └── redis/                 # Cache configuration
├── frontend/                  # Flutter mobile application
├── docs/                      # Documentation
└── docker-compose.yml         # Container orchestration
```

## 🗄️ Database Configuration

### PostgreSQL Databases
- **medshakti_auth** (Port: 5432) - User management
- **medshakti_medicine** (Port: 5433) - Medicine catalog
- **medshakti_store** (Port: 5434) - Store information
- **medshakti_prescription** (Port: 5435) - Prescription data
- **medshakti_notification** (Port: 5436) - Notification logs

### Redis Instances
- **redis_auth** (Port: 6379) - Authentication cache
- **redis_cache** (Port: 6380) - General caching

### Default Credentials
- **PostgreSQL**: `postgres` / `postgres123`
- **Redis**: No authentication (development only)

## 🔧 Development Setup

### Individual Service Development
```bash
# Start only required services
docker-compose up postgres_auth redis_auth

# Run auth service locally
cd services/auth_service
pip install -r requirements.txt
python manage.py runserver 8001
```

### Database Migrations
```bash
# Run migrations for all services
docker-compose exec auth_service python manage.py migrate
docker-compose exec medicine_service python manage.py migrate
docker-compose exec store_service python manage.py migrate
docker-compose exec prescription_service python manage.py migrate
docker-compose exec notification_service python manage.py migrate
```

### View Logs
```bash
# View all service logs
docker-compose logs -f

# View specific service logs
docker-compose logs -f auth_service
docker-compose logs -f medicine_service
```

## 🔐 Environment Configuration

### Development Environment Variables
Create `.env` files for each service with:

```bash
# Common environment variables
DEBUG=1
SECRET_KEY=your-development-secret-key

# Database Configuration (using default Docker setup)
DATABASE_URL=postgresql://postgres:postgres123@postgres_service:5432/database_name

# Redis Configuration  
REDIS_URL=redis://redis_service:6379/db_number

# API Keys (for development/testing)
GOOGLE_VISION_API_KEY=your-api-key
SMS_GATEWAY_API_KEY=your-sms-api-key
```

## 📱 Frontend Development

### Flutter Setup
```bash
cd frontend
flutter pub get
flutter run
```

### API Configuration
Update API endpoints in Flutter app:
```dart
// lib/config/api_config.dart
class ApiConfig {
  static const String baseUrl = 'http://localhost:8000';
  static const String authService = '$baseUrl/auth';
  static const String medicineService = '$baseUrl/medicine';
  // ... other endpoints
}
```

## 🧪 Testing

### Backend Testing
```bash
# Run tests for specific service
docker-compose exec auth_service python manage.py test

# Run with coverage
docker-compose exec auth_service coverage run manage.py test
docker-compose exec auth_service coverage report
```

### API Testing
```bash
# Health check endpoints
curl http://localhost:8000/health/
curl http://localhost:8001/auth/health/
curl http://localhost:8002/medicine/health/
```

## 🚀 Development Deployment

### Local Development
```bash
# Start all services for development
docker-compose up --build

# Start specific services
docker-compose up postgres_auth redis_auth auth_service

# Rebuild and restart services
docker-compose up --build --force-recreate
```

## 📊 Monitoring & Maintenance

### Container Health Monitoring
```bash
# Check container status
docker-compose ps

# Monitor resource usage
docker stats

# Check container logs
docker-compose logs --tail=100 -f service_name
```

### Database Backup
```bash
# Backup all databases
./scripts/backup_databases.sh

# Restore from backup
./scripts/restore_databases.sh backup_file.sql
```

## 🔧 Troubleshooting

### Common Issues

**Port Already in Use**
```bash
# Check port usage
lsof -ti:8000
# Kill process if needed
kill -9 $(lsof -ti:8000)
```

**Database Connection Issues**
```bash
# Reset database volumes
docker-compose down -v
docker-compose up --build
```

**Service Dependencies**
```bash
# Restart services in order
docker-compose restart postgres_auth redis_auth
docker-compose restart auth_service
```

### Performance Tips
- **Redis Caching**: Monitor cache hit rates in development
- **Database Queries**: Use Django Debug Toolbar to optimize queries
- **Container Resources**: Adjust Docker memory limits if needed

## 🤝 Contributing

### Development Workflow
1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Make changes and test thoroughly
4. Commit changes: `git commit -m 'Add amazing feature'`
5. Push to branch: `git push origin feature/amazing-feature`
6. Open Pull Request

### Code Standards
- Follow PEP 8 for Python code
- Use Black for code formatting
- Write comprehensive tests
- Update documentation

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Support

For support and questions:
- Create an issue on GitHub
- Contact the development team
- Check the documentation in `/docs`

## 🔗 Related Links

- [API Documentation](docs/api.md)
- [Frontend Documentation](docs/frontend.md)
- [Deployment Guide](docs/deployment.md)
- [Contributing Guidelines](CONTRIBUTING.md)
