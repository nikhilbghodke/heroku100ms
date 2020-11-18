# 100mslive sample web app

This is an example web app to demo 100mslive's web SDK

## Prerequisites

You will need [Node.js](https://nodejs.org) version v12.13.0 or greater installed on your system

## Setup

Get the code by cloning this repo using git

```
git clone git@github.com:100mslive/sample-app-web.git
```

Once cloned, open the terminal in the project directory, and install dependencies with:

```
npm install
```

Create a new file `.env` and copy the values from `example.env`

```
cp example.env .env
```

### Token generation

You will need to send a token - generated by a combination of `access_key`, `customer_secret`, `customer_id`, `app_id`, `peer_id` and `room_id` when initiating 100ms client

#### Get your keys and secrets

Please reach out to [Aniket Behera](mailto:aniket@100ms.live) to get your -
- `access_key` - You can generate unique access_keys for multiple access points
- `secret` - This unique secret is used to sign the token. This should ideally be stored server-side
- `customer_id` - This is an identifier for your organisation
- `app_id` - You can use this to differentiate multiple apps which use 100ms

#### Host a token generation endpoint

1. Clone [this document on runkit](https://runkit.com/aniketbehera/100ms-token-generation-service)
2. Add the following environment variables in runkit - `hmsCustomerId`, `hmsSecret`, `hmsAccessKey`, `hmsAppId` (Screenshot for reference:)
![runkit screenshot](./github/screenshots/runkit-screenshot.png)
3. Publish your runkit and copy the endpoint URL (click on it and copy the URL that opens)

Update the `TOKEN_ENDPOINT` in `.env` file with your runkit endpoint (eg. `https://ms-token-generation-service-4w7npt7zb4ol.runkit.sh/`)

### Firebase config

Update the following values from your firebase project settings:

```
# Firebase config
FIREBASE_API_KEY=<firebaseConfig.apiKey>
FIREBASE_AUTH_DOMAIN=<firebaseConfig.authDomain>
FIREBASE_DATABASE_URL=<firebaseConfig.databaseURL>
FIREBASE_PROJECT_ID=<firebaseConfig.projectId>
FIREBASE_STORAGE_BUCKET=<firebaseConfig.storageBucket>
FIREBASE_MESSAGING_ID=<firebaseConfig.messagingSenderId>
FIREBASE_APP_ID=<firebaseConfig.appId>
FIREBASE_MEASUREMENT_ID=<firebaseConfig.measurementId>
```

Then start the app with:

```
npm start
```

The app should now be up and running at http://localhost:8080 🚀