# Feathers Microservice Demo

> A small microservice on top of Node.js

## Live version

Check a [live version](https://feathers-microservice-demo.herokuapp.com/) deployed on the [Heroku Cloud Application Platform](https://www.heroku.com/).

[https://feathers-microservice-demo.herokuapp.com/](https://feathers-microservice-demo.herokuapp.com/)

## About

This project uses [Feathers](http://feathersjs.com). An open source web framework for building modern real-time applications.

This is the backend for the [https://github.com/josepcrespo/nuxt-vuetify-pwa-demo](https://github.com/josepcrespo/nuxt-vuetify-pwa-demo) project. It exposes a single API endpoint called `favorites`.

### Feathers CRUD

Feathers service methods that provide CRUD functionality are:

- `find`: Find all data (potentially matching a query).
- `get`: Get a single data entry by its unique identifier.
- `create`: Create new data.
- `update`: Update an existing data entry by completely replacing it.
- `patch`: Update one or more data entries by merging with the new data.
- `remove`: Remove one or more existing data entries.

When used as a REST API, incoming requests get mapped automatically to their corresponding service method like this:

| Service method                                    | HTTP method | Path                     |
|:---                                               |:---         |:---                      |
| service.find({ query: {} })                       | GET         | /favorites                   |
| service.find({ query: { listName: 'title' } }) | GET         | /favorites?listName=title |
| service.get(1)                                    | GET         | /favorites/1                 |
| service.create(body)                              | POST        | /favorites                   |
| service.update(1, body)                           | PUT         | /favorites/1                 |
| service.patch(1, body)                            | PATCH       | /favorites/1                 |
| service.remove(1)                                 | DELETE      | /favorites/1                 |

This way, we have a fully functional REST API endpoint for our `/favorites` service.

## Quick start with Docker

You need [Git](https://git-scm.com) >= `v2.24.3` and, [Docker Engine](https://docker.com/) >= `v19.03.13`. Make sure you don't have any other service using the 3030 port.

```bash
$ git clone https://github.com/josepcrespo/feathers-microservice-demo.git && cd feathers-microservice-demo && docker-compose build --no-cache --force-rm && docker-compose up
```

The service will be available at [http://localhost:3030](http://localhost:3030)

## Local setup (if don't want a Docker setup)

Getting up and running is as easy as 1, 2, 3 and… 4.

1. Make sure you have [NodeJS](https://nodejs.org/) and [npm](https://www.npmjs.com/) installed.

2. Install your dependencies

    ```
    cd path/to/feathers-microservice-demo
    npm install
    ```

3. Connect your local MySQL instance to the app.

You need to set your MySQL connection string into the /config/default.json file, on the `mysql` key.

4. Start your app for development

    ```
    npm run dev
    ```

## Testing

Simply run `npm run test` and all your tests in the `test/` directory will be run.

## Scaffolding

Feathers has a powerful command line interface. Here are a few things it can do:

```
$ npm install -g @feathersjs/cli          # Install Feathers CLI

$ feathers generate service               # Generate a new Service
$ feathers generate hook                  # Generate a new Hook
$ feathers help                           # Show all commands
```

## Help

For more information on all the things you can do with Feathers visit [docs.feathersjs.com](http://docs.feathersjs.com).
