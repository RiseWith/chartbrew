# Chartbrew Docs

## Prerequisites

**NodeJS** v12.17.0+
  * For M1 Macs you might need the latest v14 or v15

**NPM**

**MySQL** (v5+) or **PostgreSQL** (12.5+)

## Getting Started

### Installation & Setup

::: tip
The setup doesn't work in Windows PowerShell or cmd.exe. If you're using Windows, please use a bash command line like [Git Bash](https://git-scm.com/downloads) or [cygwin](https://www.cygwin.com/install.html)
:::

#### Run your database instance and create the chartbrew database

**Important!** Make sure you have a MySQL or PostgreSQL instance running and you have created a database for Chartbrew. [Follow the instruction here >>](/database/#mysql)

#### Quickstart

```sh
npx create-chartbrew-app chartbrew
```

The CLI tool creates a `chartbrew/.env` file which you can configure at any time if you want to change the database, API & client host, etc. The file contains comments explaining what each environmental variable is for.

#### Developing and extending the application

If you plan on doing this, setup the app like so:

```sh
git clone https://github.com/chartbrew/chartbrew.git
cd chartbrew && npm run setup
```

If you submit any PRs, please [follow the guidelines here](https://github.com/chartbrew/chartbrew/blob/master/CONTRIBUTING.md).

### Set up environmental variables

All the environmental variables that need to be set are found in the `.env-template` file in the root folder of the project. If you ran the setup above, you should already have a `.env` file there as well. If not, copy the template file and rename it `.env`.

Make sure you fill out the `Production` and `Development` sections accordingly.

### Run the database migrations

Running the migrations will ensure that you have the most up-to-date database schema. Ensure that all environmental variables are set before running the following command in the `server` folder:

```sh
cd server
npm run db:migrate
```

### Run the project in Development

Open two terminals, one for front-end and the other for back-end.

```sh
# frontend
cd client/
npm run start

# backend
cd server/
npm run start-dev
```

### Changing the docs

Chartbrew uses [Vuepress](https://vuepress.vuejs.org/) and you can check their documentation to see how it works. You can start the documentation development using the command below:

```sh
cd chartbrew
npm run docs:dev
```

## Tech stack

**Backend**

* [NodeJS](https://nodejs.org/en/)
* [ExpressJS](https://expressjs.com/)
* [Sequelize ORM](https://sequelize.org/)
* [Nodemailer](https://nodemailer.com/about/)
* [Mongoose](https://mongoosejs.com/) for mongoDB data sources

**Frontend**

* [ReactJS](https://reactjs.org/)
* [Redux](https://redux.js.org/)
* [Semantic UI](https://fomantic-ui.com/) (Fomantic UI at the moment)
* [ChartJs](https://www.chartjs.org/)

**Docs**

* [Vuepress](https://vuepress.vuejs.org/)
