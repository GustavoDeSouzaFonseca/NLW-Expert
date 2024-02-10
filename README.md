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

## Endpoints

You could use any app to send http requests like *Postman*, *Insomnia*, etc. </br>
Recomends to use [hoppscotch](https://hoppscotch.io/) to use the [real time tab](https://hoppscotch.io/realtime/websocket)

### Http: 
`http://localhost:3333/polls`
* `GET /polls/:pollId - Find poll by Id`
* `POST /polls - Create a poll`
* `POST /polls/:pollId/votes - Vote on Poll`

### WebSocket: 
`ws://localhost:3333/polls`


# All topics below are my documentation studies

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

## Redis

It's an open-source, in-memory data store used by millions of developers as a cache, vector database, document database, streaming engine, and message broker. </br>
[Redis documentation](https://redis.io/docs/) </br>

To use with Node.js, let's install the dependencie `npm install ioredis` a translator of redis to facilitad use in typescript [ioredis](https://github.com/redis/ioredis)

It was use only this two commands properties
 - ZINCRBY
    - `zincrby(key, increment, id of key incremented)`
 - ZRANGE
    - `zrange(key, min, max, withscores)`

## Fastify - doc in progress