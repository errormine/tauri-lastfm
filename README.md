# Tauri Last.fm

This is a simple JS wrapper for the Last.fm API intended for use within [Tauri](https://v2.tauri.app/) desktop applications.
It was built for Tauri 2.0 Beta.

## Features

- Easily access all of the Last.fm API
- Fetch requests are made by the Tauri bakend using the http plugin
- Node.js is not needed!

## Installation

To install simply use the command:

```bash
npm i tauri-lastfm
```

or use your preferred package manager:

```bash
pnpm add tauri-lastfm
```

## Usage

Simple example:

```js
import LastFM from 'tauri-lastfm';

const lastFm = new LastFM({
    apiKey: 'LASTFM_API_KEY',
    apiSecret: 'LASTFM_API_SECRET',
});

// Get the metadata for an artist
lastFm.artist.getInfo({ artist: 'Cher' })
    .then(data => {
        console.log(data);
    });
```

Example with authentication:

```js
import LastFM from 'tauri-lastfm';

const lastFm = new LastFM({
    apiKey: 'LASTFM_API_KEY',
    apiSecret: 'LASTFM_API_SECRET',
});

// This is a helper function so you don't have to manually create the url
// It also automatically retrieves a token and stores it until it is used
let url = await lastFm.auth.getAuthUrl();

// Have the user sign in and authorize your application
window.open(url, '_blank');

// Get the user session
// You should store this somewhere securely!
let session = await lastFm.auth.getSession();

// You can now make calls to the endpoints which require authentication
lastFm.track.updateNowPlaying({
        artist: 'Daft Punk',
        track: 'Around the World',
    }, session.key);
```

## Contributing

For suggestions and issues visit the [GitHub](https://github.com/errormine/tuari-lastfm).