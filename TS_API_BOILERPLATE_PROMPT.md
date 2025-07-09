# 🔧 ПРОМТ ДЛЯ РАЗРАБОТКИ: TypeScript API Boilerplate

## 🎯 ЦЕЛЬ ПРОЕКТА

Создать production-ready REST API boilerplate на TypeScript + Node.js с полным набором инструментов для разработки современных веб-приложений.

## 📋 ТЕХНИЧЕСКОЕ ЗАДАНИЕ

### 🏗 СТЕК ТЕХНОЛОГИЙ
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

### ✨ КЛЮЧЕВЫЕ ВОЗМОЖНОСТИ

#### 🔐 Аутентификация и Авторизация
- JWT-based аутентификация
- Role-based авторизация (User, Admin, Moderator)
- Refresh token механизм
- Password hashing с bcrypt
- Middleware для защиты роутов

#### 📊 База данных
- Prisma ORM с миграциями
- PostgreSQL как основная БД
- Seed данные для разработки
- Database connection pooling
- Soft delete для сущностей

#### 🛡️ Безопасность
- Rate limiting (защита от DDoS)
- CORS настройки
- Helmet.js для security headers
- Input validation с Zod
- SQL injection protection через Prisma
- XSS protection

#### 📝 API Документация
- OpenAPI 3.0 спецификация
- Swagger UI интерфейс
- Автоматическая генерация документации
- Postman collection экспорт

#### 🧪 Тестирование
- Unit тесты с Jest
- Integration тесты с Supertest
- E2E тесты для API endpoints
- Test coverage отчеты
- Mock данных для тестов

#### 🚀 Production Features
- Health check endpoints
- Graceful shutdown
- Error handling middleware
- Request/Response logging
- Performance monitoring
- Environment-based конфигурация

## 📁 СТРУКТУРА ПРОЕКТА

```
ts-api-boilerplate/
├── src/
│   ├── controllers/          # HTTP контроллеры
│   │   ├── auth.controller.ts
│   │   ├── user.controller.ts
│   │   └── health.controller.ts
│   ├── services/             # Бизнес-логика
│   │   ├── auth.service.ts
│   │   ├── user.service.ts
│   │   └── email.service.ts
│   ├── middleware/           # Express middleware
│   │   ├── auth.middleware.ts
│   │   ├── validation.middleware.ts
│   │   ├── error.middleware.ts
│   │   └── rate-limit.middleware.ts
│   ├── models/               # Prisma модели
│   │   └── index.ts
│   ├── routes/               # API роуты
│   │   ├── auth.routes.ts
│   │   ├── user.routes.ts
│   │   └── index.ts
│   ├── utils/                # Утилиты
│   │   ├── logger.ts
│   │   ├── jwt.ts
│   │   ├── validation.ts
│   │   └── response.ts
│   ├── types/                # TypeScript типы
│   │   ├── auth.types.ts
│   │   ├── user.types.ts
│   │   └── api.types.ts
│   ├── config/               # Конфигурация
│   │   ├── database.ts
│   │   ├── jwt.ts
│   │   └── app.ts
│   └── app.ts                # Основной файл приложения
├── prisma/
│   ├── schema.prisma         # Prisma схема
│   ├── migrations/           # Миграции БД
│   └── seed.ts               # Seed данные
├── tests/
│   ├── unit/                 # Unit тесты
│   ├── integration/          # Integration тесты
│   ├── e2e/                  # E2E тесты
│   └── fixtures/             # Test данные
├── docs/
│   ├── api.md                # API документация
│   ├── deployment.md         # Инструкции по деплою
│   ├── postman-collection.json
│   └── openapi.yaml
├── scripts/
│   ├── setup.sh              # Скрипт настройки
│   ├── seed.sh               # Скрипт заполнения БД
│   └── deploy.sh             # Скрипт деплоя
├── docker/
│   ├── Dockerfile
│   └── docker-compose.yml
├── .github/
│   └── workflows/
│       ├── ci.yml            # CI pipeline
│       └── deploy.yml        # CD pipeline
├── package.json
├── tsconfig.json
├── jest.config.js
├── .eslintrc.js
├── .prettierrc
├── .env.example
├── README.md
└── CHANGELOG.md
```

## 🎯 ФУНКЦИОНАЛЬНЫЕ ТРЕБОВАНИЯ

### 👤 Система пользователей
- Регистрация пользователей
- Аутентификация (login/logout)
- Профиль пользователя (CRUD)
- Смена пароля
- Восстановление пароля через email
- Роли пользователей (User, Admin, Moderator)

### 🔐 Аутентификация
- JWT токены (access + refresh)
- Автоматическое обновление токенов
- Logout с инвалидацией токенов
- Middleware для защиты роутов
- Rate limiting для auth endpoints

### 📊 API Endpoints

#### Auth Routes
```
POST   /api/auth/register     # Регистрация
POST   /api/auth/login        # Вход
POST   /api/auth/refresh      # Обновление токена
POST   /api/auth/logout       # Выход
POST   /api/auth/forgot-password  # Забыли пароль
POST   /api/auth/reset-password   # Сброс пароля
```

#### User Routes
```
GET    /api/users/profile     # Получить профиль
PUT    /api/users/profile     # Обновить профиль
DELETE /api/users/profile     # Удалить аккаунт
GET    /api/users/:id         # Получить пользователя (Admin)
PUT    /api/users/:id         # Обновить пользователя (Admin)
DELETE /api/users/:id         # Удалить пользователя (Admin)
```

#### Health Routes
```
GET    /api/health            # Health check
GET    /api/health/db         # Database health
GET    /api/health/redis      # Redis health
```

## 🛠 ТЕХНИЧЕСКИЕ ТРЕБОВАНИЯ

### 📦 Зависимости

#### Основные
```json
{
  "express": "^4.18.2",
  "typescript": "^5.0.0",
  "prisma": "^5.0.0",
  "@prisma/client": "^5.0.0",
  "jsonwebtoken": "^9.0.0",
  "bcryptjs": "^2.4.3",
  "zod": "^3.22.0",
  "cors": "^2.8.5",
  "helmet": "^7.0.0",
  "express-rate-limit": "^6.7.0",
  "winston": "^3.10.0",
  "dotenv": "^16.3.0"
}
```

#### Разработка
```json
{
  "jest": "^29.6.0",
  "supertest": "^6.3.0",
  "@types/jest": "^29.5.0",
  "@types/supertest": "^2.0.0",
  "@types/express": "^4.17.17",
  "@types/node": "^20.0.0",
  "@types/jsonwebtoken": "^9.0.0",
  "@types/bcryptjs": "^2.4.2",
  "@types/cors": "^2.8.13",
  "eslint": "^8.45.0",
  "prettier": "^3.0.0",
  "ts-node": "^10.9.0",
  "nodemon": "^3.0.0"
}
```

### 🔧 Конфигурация

#### TypeScript (tsconfig.json)
```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "commonjs",
    "lib": ["ES2022"],
    "outDir": "./dist",
    "rootDir": "./src",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "resolveJsonModule": true,
    "declaration": true,
    "declarationMap": true,
    "sourceMap": true,
    "removeComments": true,
    "noImplicitAny": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "dist", "tests"]
}
```

#### Prisma Schema
```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

model User {
  id        String   @id @default(cuid())
  email     String   @unique
  password  String
  firstName String?
  lastName  String?
  role      Role     @default(USER)
  isActive  Boolean  @default(true)
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
  deletedAt DateTime?

  @@map("users")
}

enum Role {
  USER
  MODERATOR
  ADMIN
}
```

## 🧪 ТЕСТИРОВАНИЕ

### Unit Tests
- Тестирование сервисов
- Тестирование утилит
- Mock внешних зависимостей

### Integration Tests
- Тестирование API endpoints
- Тестирование с реальной БД
- Тестирование middleware

### E2E Tests
- Полные сценарии пользователя
- Тестирование аутентификации
- Тестирование авторизации

### Coverage Requirements
- Минимум 80% покрытия кода
- 100% покрытие критических путей
- Отчеты в HTML формате

## 🚀 ДЕПЛОЙ И CI/CD

### Docker
- Multi-stage Dockerfile
- Docker Compose для разработки
- Production оптимизации

### GitHub Actions
- Автоматические тесты
- Линтинг и форматирование
- Сборка Docker образов
- Деплой на Vercel/Railway

### Environment Variables
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

## 📚 ДОКУМЕНТАЦИЯ

### README.md структура
```markdown
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
```

## 🎯 КРИТЕРИИ ГОТОВНОСТИ

### ✅ MVP (Минимально жизнеспособный продукт)
- [ ] Базовая структура проекта
- [ ] Express.js сервер с TypeScript
- [ ] Prisma + PostgreSQL подключение
- [ ] JWT аутентификация
- [ ] Базовые CRUD операции для пользователей
- [ ] Валидация с Zod
- [ ] Базовые тесты

### ✅ Production Ready
- [ ] Полная документация API
- [ ] Тесты с покрытием >80%
- [ ] Docker контейнеризация
- [ ] CI/CD pipeline
- [ ] Error handling
- [ ] Logging
- [ ] Rate limiting
- [ ] Security headers

### ✅ Extra Features
- [ ] Refresh token механизм
- [ ] Email уведомления
- [ ] File upload
- [ ] Caching с Redis
- [ ] Background jobs
- [ ] API версионирование
- [ ] Monitoring и метрики

## 🚀 СЛЕДУЮЩИЕ ШАГИ

1. **Инициализация проекта**
   - Создать структуру папок
   - Настроить package.json
   - Установить зависимости

2. **Базовая настройка**
   - TypeScript конфигурация
   - ESLint + Prettier
   - Prisma схема

3. **Основная разработка**
   - Express.js сервер
   - Middleware
   - Контроллеры и сервисы
   - Аутентификация

4. **Тестирование**
   - Unit тесты
   - Integration тесты
   - E2E тесты

5. **Документация и деплой**
   - README
   - API документация
   - Docker
   - CI/CD

---

**Цель:** Создать профессиональный, production-ready API boilerplate, который можно использовать как основу для любых веб-приложений и который продемонстрирует навыки работы с современным TypeScript стеком. 