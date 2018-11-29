# Open Collective Invoices

[![Circle CI](https://circleci.com/gh/opencollective/opencollective-invoices/tree/master.svg?style=shield)](https://circleci.com/gh/opencollective/opencollective-invoices/tree/master)
[![Slack Status](https://slack.opencollective.org/badge.svg)](https://slack.opencollective.org)
[![Dependency Status](https://david-dm.org/opencollective/opencollective-invoices/status.svg)](https://david-dm.org/opencollective/opencollective-invoices)
[![Greenkeeper badge](https://badges.greenkeeper.io/opencollective/opencollective-invoices.svg)](https://greenkeeper.io/)

## Foreword

If you see a step below that could be improved (or is outdated), please update the instructions. We rarely go through this process ourselves, so your fresh pair of eyes and your recent experience with it, makes you the best candidate to improve them for other users. Thank you!

## Development

### Prerequisite

1. Make sure you have Node.js version >= 10.

- We recommend using [nvm](https://github.com/creationix/nvm): `nvm use`.

2. Make sure you have [GraphicsMagick](http://www.graphicsmagick.org) installed.

- On Debian/Ubuntu: `sudo apt-get install graphicsmagick`
- On MacOS (with [Homebrew](https://brew.sh/)): `brew install graphicsmagick`

### Install

We recommend cloning the repository in a folder dedicated to `opencollective` projects.

```
git clone git@github.com:opencollective/opencollective-invoices.git opencollective/invoices
cd opencollective/invoices
npm install
```

### Environment variables

This project requires an access to the Open Collective API. You have two options:

- `cp .env-staging .env` to connect to the Open Collective staging API
- `cp .env-local .env` to connect to the API running locally

If you decide to pick the local strategy, make sure you install and run the [opencollective-api](https://github.com/opencollective/opencollective-api) project.

### Start

To start the service:

```
npm run dev
```

If you use this service through frontend, you're ready to go - frontend will pass
your authorization token directly to the app.

However if you're using the service directly you'll need to set the `Authorization`
header with your token to identify your requests.

## Contributing

Code style? Commit convention? Please check our [Contributing guidelines](CONTRIBUTING.md).

TL;DR: we use [Prettier](https://prettier.io/) and [ESLint](https://eslint.org/), we do like great commit messages and clean Git history.

## Tests

You can run the tests using `npm test`.

## Deployment

To deploy to staging or production, you need to be a core member of the Open Collective team.

### Staging (now)

```
now -e API_KEY=09u624Pc9F47zoGLlkg1TBSbOl2ydSAq -e API_URL=https://api-staging.opencollective.com -e WEBSITE_URL=https://staging.opencollective.com
now alias invoices-staging.opencollective.com
```

- URL: https://invoices-staging.opencollective.com/

### Production (now)

```
now -e API_KEY=@opencollective_api_key -e API_URL=https://api.opencollective.com -e WEBSITE_URL=https://opencollective.com
now alias invoices.opencollective.com
```

- URL: https://invoices.opencollective.com/
