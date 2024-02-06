# NLW-Expert

Develop an API using Node.JS and typescript for a create polls and votes in real time.

## Run locally

To run this project, follow the instructions

1. Clone the repository
```
git clone https://github.com/GustavoDeSouzaFonseca/NodeJS-Challenge-AnotaAi-PL.git
cd NodeJS-Challenge-AnotaAi-PL
```

2. Install all depedencies and start the application
OBS.: note we use Node version > v.20.0.0, to see your node version use the command
```
node -v
```
then
```
npm install
npm start
```

## typescript dependencie for node compile

```
    npm install typescript @types/node tsx -D
```

**Initializing tsconfig** </br>
`npx tsx --init`

[Node Target Mapping](https://github.com/microsoft/TypeScript/wiki/Node-Target-Mapping).

## ORM Prisma
Prisma it's a object relation mapping or ORM open source Node.js and TypeScript with an </br>
intuitive data model, automated migrations, type-safety, and autocompletion. </br>
[Prisma ORM | Documentation](https://www.prisma.io/docs)


*installation prisma as dev dependencie*
```
    npm install -D prisma
```

**Initializing schema.prisma** </br>
`npx prisma --init`

## ZOD
Zod is a validation data library, that validate schemas from typescript with static type interface.
[Zod | Documentation](https://zod.dev/)

*installation zod as dev dependencie*
```
    npm install -D zod 
```

## Docker

This project will be use docker and docker-compose to up the database.
The file will be stay at main directory as
    - docker-compose.yml

```
    version: '3.7'

    services:
    postgres:
        image: bitnami/postgresql:latest
        ports:
        - '5432:5432'
        environment:
        - POSTGRES_USER=docker
        - POSTGRES_PASSWORD=docker
        - POSTGRES_DB=polls
        volumes:
        - polls_pg_data:/bitnami/postgresql

    redis:
        image: bitnami/redis:latest
        environment:
        - ALLOW_EMPTY_PASSWORD=yes
        ports:
        - '6379:6379'
        volumes:
        - 'polls_redis_data:/bitnami/redis/data'

    volumes:
    polls_pg_data:
    polls_redis_data:

```

