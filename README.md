# Wedding Invite Manager Database

A simple website enabling wedding organizers to send invitations to guests, who can then RSVP and update their food preferences. Utilizes mariadb.

# Requirements

- npm (v9.6.2)
- node (v18.15.0)
- mariadb (v15.1 distrib 10.5.18-MariaDB for Linux x84_64)

# Setting up the database

Ensure MariaDB has been setup with a user and database, then import the dump:

```bash
mariadb -p DATABASE_NAME < database.sql
```

# Configuring backend

After preparing the database, ensure the correct address, port, and password are set in the `.env` files in:

- `src/client/.env` 
- `src/server/.env`

Example configurations can be found in the respective directories `.env.example` files.

# Installing Dependencies

Install node dependencies by running

```bash
cd src/server/
npm install
```

```bash
cd src/client/
npm install
```

# Running in Development Mode

This application uses Node.js, using npm to run the Express.js backend and Vue.js frontend. 

To run the backend run:

```bash
cd src/server/
npm run start
```

Then to run the client frontend run:

```bash
cd src/client/
npm run dev
```

# Troubleshooting
- Client reports `ECONNREFUSED`:
    - (a) the server is not running, or 
    - (b) the environmental variables are not correctly set
- On server startup it reports `[nodemon] app crashed`:
    - MariaDB environmental variables are not set correctly, or
    - Database user does not have adequate permissions
