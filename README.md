# 🔧 TypeScript API Boilerplate

Production-ready REST API boilerplate на TypeScript с полным набором инструментов для разработки.

## ✨ Возможности
- 🚀 TypeScript + Node.js
- 🔐 JWT аутентификация
- 📊 Prisma ORM
- 🧪 Jest тестирование
- 📝 OpenAPI документация
- 🐳 Docker поддержка

## 🚀 Быстрый старт
```bash
git clone https://github.com/beocch/ts-api-boilerplate
cd ts-api-boilerplate
npm install
npm run dev
```

## 📖 API Документация
- [OpenAPI Spec](http://localhost:3000/api-docs)
- [Postman Collection](docs/postman-collection.json)

## 🏗 Архитектура
```
src/
├── controllers/
├── services/
├── middleware/
├── models/
├── routes/
├── utils/
└── types/
```

## 🧪 Тесты
```bash
npm test
npm run test:coverage
npm run test:e2e
```

## 📊 CI/CD
- ✅ Автоматические тесты
- ✅ Линтинг и форматирование
- ✅ Docker образы
- ✅ Деплой на Vercel/Railway

## 🛠 Технологический стек
- **Runtime:** Node.js 18+
- **Language:** TypeScript 5+
- **Framework:** Express.js
- **ORM:** Prisma
- **Database:** PostgreSQL
- **Authentication:** JWT (jsonwebtoken)
- **Validation:** Zod
- **Testing:** Jest + Supertest
- **Linting:** ESLint + Prettier
- **Documentation:** OpenAPI/Swagger
- **Containerization:** Docker + Docker Compose
- **Logging:** Winston
- **Rate Limiting:** express-rate-limit
- **CORS:** cors
- **Environment:** dotenv

## 🎯 API Endpoints

### Auth Routes
```
POST   /api/auth/register     # Регистрация
POST   /api/auth/login        # Вход
POST   /api/auth/refresh      # Обновление токена
POST   /api/auth/logout       # Выход
POST   /api/auth/forgot-password  # Забыли пароль
POST   /api/auth/reset-password   # Сброс пароля
```

### User Routes
```
GET    /api/users/profile     # Получить профиль
PUT    /api/users/profile     # Обновить профиль
DELETE /api/users/profile     # Удалить аккаунт
GET    /api/users/:id         # Получить пользователя (Admin)
PUT    /api/users/:id         # Обновить пользователя (Admin)
DELETE /api/users/:id         # Удалить пользователя (Admin)
```

### Health Routes
```
GET    /api/health            # Health check
GET    /api/health/db         # Database health
GET    /api/health/redis      # Redis health
```

## 🔧 Установка и настройка

### Предварительные требования
- Node.js 18+
- PostgreSQL
- Docker (опционально)

### Установка зависимостей
```bash
npm install
```

### Настройка базы данных
```bash
# Создание миграций
npx prisma migrate dev

# Заполнение тестовыми данными
npm run seed
```

### Запуск в режиме разработки
```bash
npm run dev
```

### Запуск тестов
```bash
npm test
npm run test:coverage
```

## 🐳 Docker

### Запуск с Docker Compose
```bash
docker-compose up -d
```

### Сборка образа
```bash
docker build -t ts-api-boilerplate .
```

## 📊 Переменные окружения

Создайте файл `.env` на основе `env.example`:

```env
# Database
DATABASE_URL="postgresql://user:password@localhost:5432/dbname"

# JWT
JWT_SECRET="your-super-secret-jwt-key"
JWT_REFRESH_SECRET="your-super-secret-refresh-key"
JWT_EXPIRES_IN="15m"
JWT_REFRESH_EXPIRES_IN="7d"

# Server
PORT=3000
NODE_ENV="development"

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100

# CORS
CORS_ORIGIN="http://localhost:3000"
```

## 🤝 Вклад в проект

1. Fork репозитория
2. Создайте feature branch (`git checkout -b feature/amazing-feature`)
3. Commit изменения (`git commit -m 'Add amazing feature'`)
4. Push в branch (`git push origin feature/amazing-feature`)
5. Откройте Pull Request

## 📄 Лицензия

Этот проект лицензирован под MIT License - см. файл [LICENSE](LICENSE) для деталей.

## 🆘 Поддержка

Если у вас есть вопросы или проблемы, создайте issue в репозитории.

---

**Разработано с ❤️ для современной веб-разработки** 