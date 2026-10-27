# Express + MongoDB API template (functional style)

A TypeScript starter for REST APIs on Express and MongoDB, organized as plain functions instead of classes.

## What is included

- **Users and sessions:** registration (`POST /register`) and session creation with bcrypt password hashing
- **JWT auth:** a `deserializeUser` middleware that reads the Bearer token into `res.locals.user`, and a `requireUser` guard for protected routes
- **Validation:** zod schemas checked by one `validateResource` middleware before any controller runs
- **Layers:** routers → controllers → services → mongoose models, so business logic stays out of route handlers
- **Config and logging:** `config` for per-environment settings, pino for structured logs

## Structure

```
src/
  routers/      route definitions
  controllers/  request and response handling
  service/      business logic and database calls
  models/       mongoose models (user, session)
  schema/       zod request schemas
  middleware/   auth and validation
  utils/        DB connection, JWT helpers, logger
config/default.ts
```

## Run

```bash
npm install
npm run dev
```

Set the MongoDB URI and the JWT keys in `config/default.ts` (or an environment-specific config file) first.

See also the [object-oriented version](https://github.com/minhnguyen99x/MTD__project-template__express-mongo-oop) of this template.
