# **API RESTful Tickets v0.2.0**

RESTful API with [NodeJs](https://nodejs.org/), [Express](https://expressjs.com/), [Sequelize](https://sequelize.org/) and [Mysql](https://www.mysql.com/) to create and assign tickets to users who request them.

## New Features!

- Create ticket
- Update ticket
- Delete ticket
- Get all the tickets
- Get a ticket
- Get assigned tickets
- Get unassigned tickets
- Assign ticket
- Get tickets from the logged in user

## Features!

- Log in
- Sign up
- User information
- Update user information
- Request a ticket
- Applicants users

## Installation

This API requires [NodeJs](https://nodejs.org/) to run.

Install the dependencies and devDependencies.

```sh
$ npm i -d
```

Create the database and specify the name in the environment variables. In addition sequelize uses other data to make the connection such as the username and password of the database manager, the host, the port and the dialect.

All this information is configured in the environment variables. It is also recommended to specify a configuration for development and one for production, which can be changed using NODE_ENV to specify if the app it is in development or production.

```sh
# CONFIG DEVELOPMENT
$ DEV_DB_USERNAME=
$ DEV_DB_PASSWORD=
$ DEV_DB_NAME=
$ DEV_DB_HOST=
$ DEV_DB_PORT=
$ DEV_DB_DIALECT=
```

```sh
# CONFIG PRODUCTION
$ PRO_DB_USERNAME=
$ PRO_DB_PASSWORD=
$ PRO_DB_NAME=
$ PRO_DB_HOST=
$ PRO_DB_PORT=
$ PRO_DB_DIALECT=
```

```sh
# CONFIG: production || development
$ NODE_ENV=
```

Express also needs some configuration so that the server is initialized and the port in which it will be hosted has to be specified.

```sh
# CONFIG DEVELOPMENT
$ DEV_SERVER_PORT=
```

```sh
# CONFIG PRODUCTION
$ PRO_SERVER_PORT=
```

To encrypt the tokens it must also be specified in the environment variables.

```sh
# CRYPT TOKEN
$ CRYPT_TOKEN=
```

### Run migrations

Sequelize through your cli allows the creation of migrations to have a control of the changes in the database. Currently, only two migrations are created, one for roles and the other for users.

to run the migrations run:

```sh
$ npx sequelize-cli db:migrate
```

### Running Seeds

For the correct operation of the app it is necessary to run the seeds since by default it is necessary to have the roles (admin and basic) and a user with an administrator role.

```sh
$ npx sequelize-cli db:seed:all
```

```sh
# Default admin user
$ email: admin@user.com
$ password: 1234567890
```

```sh
# Default basic user
$ email: basic@user.com
$ password: 1234567890
```

# Run server

```sh
# Development
$ npm run dev
```

```sh
# Production
$ npm run build
$ npm start
```

# Routes

```sh
# THIS ROUTE ALLOWS YOU TO SIGN UP IN THE APPLICATION
$ POST api/auth/signup
```

```sh
# THIS ROUTE ALLOWS LOGGING FROM THE APP
$ POST api/auth/login
```

```sh
# THIS ROUTE RETURN THE LOGGED USER INFORMATION
$ GET api/users/info
```

```sh
# THIS ROUTE UPDATE AND RETURN LOGGED USER DATA
$ PUT api/users/update
```

```sh
# THIS ROUTE SET THE LOGGED USER REQUEST FIELD SO THAT A TICKET CAN BE ASSIGNED AND RETURNED DATA
$ PUT api/users/request
```

```sh
# THIS ROUTE RETURN USERS WHO ARE REQUESTING A TICKET
$ GET api/users/applicants
```

```sh
# THIS ROUTE ALLOWS TO OBTAIN ALL USER TICKETS
$ GET api/users/tickets
```

```sh
# THIS ROUTE ALLOWS TO CREATE A TICKET
$ POST api/tickets/create
```

```sh
# THIS ROUTE ALLOWS TO UPDATE A TICKET IF YOU HAVE NOT ALREADY BEEN ASSIGNED TO A USER
$ PUT api/tickets/update/:id
```

```sh
# THIS ROUTE ALLOWS TO DELETE A TICKET IF YOU HAVE NOT ALREADY BEEN ASSIGNED TO A USER
$ DELETE api/tickets/delete/:id
```

```sh
# THIS ROUTE ALLOWS TO GET ALL THE TICKETS
$ GET api/tickets/all
```

```sh
# THIS ROUTE ALLOWS TO GET A TICKET
$ GET api/tickets/one/:id
```

```sh
# THIS ROUTE ALLOWS TO OBTAIN THE ASSIGNED TICKETS
$ GET api/tickets/assigned
```

```sh
# THIS ROUTE ALLOWS TO OBTAIN NOT ASSIGNED TICKETS
$ GET api/tickets/notassigned
```

```sh
# THIS ROUTE ALLOWS TO ASSIGN A TICKET
$ PUT api/tickets/toassign/:id
```
