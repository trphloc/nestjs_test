# AI Agent Sandbox (NestJS Example)

This repository is a tiny, clean NestJS app used to try out an AI coding agent in a realistic Node/TypeScript project. NestJS is here purely as an example framework to give the agent something concrete to scaffold, lint, test, and run.

## What’s inside

- NestJS 11, TypeScript 5, Node.js runtime
- Jest for unit and e2e tests
- ESLint + Prettier
- Minimal example endpoint at `GET /` returning `Hello World!`

## Quickstart

```bash
# install deps
npm install

# start in watch mode
npm run start:dev

# open http://localhost:3000
```

Environment:

- `PORT` (optional): overrides the default port 3000. Example:

```bash
PORT=4000 npm run start:dev
```

## Scripts

```bash
# start (one-off)
npm run start

# start with watch (recommended during development)
npm run start:dev

# production start (after build)
npm run start:prod

# build TypeScript to dist/
npm run build

# lint and auto-fix
npm run lint

# format source and tests
npm run format

# unit tests / e2e tests / coverage
npm test
npm run test:e2e
npm run test:cov
```

## HTTP API

- `GET /` → returns `Hello World!`

Example:

```bash
curl http://localhost:3000/
```

## Using this repo with an AI agent

This project is a safe playground for common agent tasks:

- Generate a new module/controller/service
- Add DTOs with validation and write tests
- Introduce a `/health` endpoint
- Add configuration support (e.g. `@nestjs/config`)
- Wire a database layer (Prisma/TypeORM) with a sample entity
- Add Dockerfile and docker-compose.yml

Feel free to iterate—tests and linting will help keep changes healthy.

## Project structure (short)

- `src/main.ts` – app bootstrap (respects `PORT` env)
- `src/app.module.ts` – root module
- `src/app.controller.ts` / `src/app.service.ts` – example endpoint
- `test/` – e2e test setup and sample test

## Requirements

- Node.js 18+ (recommended 20+)
- npm (bundled with Node)

## License

UNLICENSED (for now). Use at your own discretion.
