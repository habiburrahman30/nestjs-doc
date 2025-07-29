# 📁 Professional NestJS Folder Structure (for Senior Developers)

This document outlines a robust, scalable folder structure for enterprise-level NestJS applications. It supports best practices, domain-driven design (DDD), third-party integrations, environment management, and advanced tooling.

---
```
npm i cookie-parser express-session bcrypt --loglevel=silly
```
```
npm i --save @nestjs/swagger @nestjs/axios axios @nestjs-modules/mailer nodemailer @nestjs/jwt @nestjs/passport passport passport-local @nestjs/websockets @nestjs/platform-socket.io class-validator class-transformer @nestjs/typeorm typeorm pg @nestjs/config
```
```
npm i --save-dev @types/passport-local @types/nodemailer
```
```
npm i -D @types/cookie-parser @types/multer @types/express-session @types/bcrypt
```

## 📦 Project Structure

```bash
src/
├── main.ts
├── app.module.ts
├── app.service.ts

├── modules/                        # Domain-driven feature modules
│   ├── auth/
│   │   ├── auth.module.ts
│   │   ├── auth.controller.ts
│   │   ├── auth.service.ts
│   │   ├── auth.strategy.ts
│   │   ├── auth.guard.ts
│   │   ├── dto/
│   │   ├── interfaces/
│   │   └── enums/
│   │
│   ├── users/
│   │   ├── users.module.ts
│   │   ├── users.service.ts
│   │   ├── users.controller.ts
│   │   ├── entities/
│   │   ├── dto/
│   │   ├── interfaces/
│   │   └── enums/
│   │
│   └── ... (other features like orders, products, etc.)

├── common/                         # Shared logic
│   ├── decorators/
│   ├── filters/
│   │   └── http-exception.filter.ts
│   ├── interceptors/
│   ├── guards/
│   ├── middlewares/
│   ├── pipes/
│   └── utils/

├── infrastructure/                # External system integrations
│   ├── logger/
│   │   └── logger.service.ts
│   ├── mailer/
│   ├── storage/
│   ├── database/
│   │   ├── database.module.ts
│   │   ├── typeorm.config.ts
│   │   ├── seeds/
│   │   └── migrations/
│   └── ...

├── config/                         # Environment configuration
│   ├── config.module.ts
│   ├── config.service.ts
│   └── validation.ts               # Joi schema for env validation

├── shared/                         # Shared constants, types, enums
│   ├── constants/
│   ├── interfaces/
│   └── enums/

├── third-party/                    # External services and APIs
│   ├── cloudinary/
│   │   ├── cloudinary.module.ts
│   │   ├── cloudinary.service.ts
│   │   └── cloudinary.constants.ts
│   └── ...

├── typings/                        # Type overrides (e.g. Express user)
│   └── express.d.ts
```

---

## 🧩 Other Files & Tools

```bash
.env                            # Main environment file
.env.sample                     # Sample for team/CI use
.prettierrc                     # Code formatting rules
.eslintrc.js                    # Linting rules
Dockerfile                      # Docker container setup
.dockerignore
nestjs-cli.json
package.json
README.md
```

---

## ✅ Best Practices

- Group by domain (not by type)
- Use `modules/` for all business features
- Use `common/` for cross-cutting concerns (filters, guards, pipes, etc.)
- Use `infrastructure/` for low-level implementations (DB, logging, storage)
- Use `third-party/` for external API wrappers (Stripe, Cloudinary, etc.)
- Use `config/` to centralize environment config with validation
- Use `typings/` for TypeScript augmentations

---

Let me know if you need a code scaffold or starter repo based on this!
