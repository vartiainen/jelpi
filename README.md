<h1 align="center">
  <br>
  <a href="http://eka.to"><img src="https://github.com/eka-foundation/jelpi/blob/master/public/img/jelpi_logo.svg" alt="Jelpi" width="200"></a>
  <br>
</h1>

<h3 align="center">A compassion based marketplace for asking and giving help.</h3>

<p align="center">
  
  <a href="https://mirrors.creativecommons.org/presskit/buttons/88x31/png/by-sa.png">
    <img width=150px src="https://raw.githubusercontent.com/eka-foundation/home/master/images/by-sa.png" alt="License">
  </a>

</p>

<p align="center">
  <a href="#what">what?</a> •
  <a href="#how">how?</a> •
  <a href="#why">why?</a> •
  <a href="#install">Install</a> •
  <a href="https://medium.com/eka-foundation">Eka's blog</a> •
  <a href="http://eka.to">About Eka</a>
</p>
<hr>

### what?

Jelpi is a marketplace that bring together people who need help with people who want to help. For example, a person who is unable to leave their home might need groceries, whereas someone in the community who is going to grocery store anyway may want to help.

### how?

Jelpi is not a service, it is a platform that can rapidly deployed (TODO: single click AWS deployment) and customized for any purpose that involves matching of help requests with help offers.

### why?

Taking care of others is the basic principle of being a human; if we can afford helping someone in our community, by doing so, we are strengthening the community, and therefore also helping ourselves.

### Key Features

ASK:

- request help (need groceries, supplies, or medicine)
- provide contact information
- wait for notification for match
- move to communicate in facebook messenger (requires login with facebook)

GIVE:

- find suitable match from proximity sorted list of asks*
- move to communicate in facebook messenger (requires login with facebook)

*by next week we should already have GIVE preferences which allow to further refine the match list, and in two weeks from now in true matchmaking service that pops up matches as they become available and the fastest to respond gets it

GENERAL:

It must take no longer than 10-minute without computer savvy to change the look and feel, language, and logo of the application. We're not building a service, but a "kit" for those that want to provide service.

Application is based on [AdonisJS](https://adonisjs.com/)

## Quick start

### With Docker

Docker quick start will build container which contains everything required for runtime

> Requires Docker to be installed https://www.docker.com/

```bash
# Build it
docker build -t jelpi .

# Run it and expose port 3333
docker run -p 3333:3333 jelpi
```

### With Node

NodeJS quick start will build all required assets and start the server

> Requires NodeJS to be installed https://nodejs.org/

```bash
# Install dependencies
npm install

# Rename .env.example to .env and set secure APP_KEY

# Start it up
npm run start
```

To do some more configuration changes look at sections below

## Writing translations

Translation files exist in `resources/locales/LOCALE/`. It's safe to add new locales and add translations into there. New locale must have all the same translations as English one, since English is used as base.

Location files are loaded to memory when backend starts, so editing location files requires restart.

Default locale is configurable in `/config/app.js` as `locale`

Read more about localization in https://adonisjs.com/docs/4.1/internationalization

## Developing

### Backend

To start backend with automatic restart:

```bash
npx adonis serve --dev
```

### Frontend

Frontend assets are in `resources/assets` folder

CSS will be built from `resources/assets/sass/app.scss` to `public/css/app.css`

JS will be built from `resources/assets/js/app.js` to `public/js/app.js`

Webpack is used as task runner and bundler, it's configuration is in project root
`webpack.config.js`

To build frontend assets:

```bash
# In development mode
npm run build:dev
```
