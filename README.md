# Tauri Last.fm

This is a simple JS wrapper for the Last.fm API intended for use within [Tauri](https://v2.tauri.app/) desktop applications.
It was built for Tauri 2.0 Beta.

## Features

- Easily access all of the Last.fm API
- Fetch requests are made by the Tauri bakend using the http plugin
- Node.js is not needed!

## Installation

To install simply use the command:

```
npm i tauri-lastfm
```

or use your preferred package manager:

```
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

// Get the tags for an artist
lastFm.artist.getTags({ artist: 'Cher' })
    .then(data => {
        console.log(data);
    });

// TODO: FILL THIS OUT MORE!
```

## Contributing

If you feel that I should change something, submit a PR, or if you have any issues, open an one on [GitHub](https://github.com/errormine/tuari-lastfm).