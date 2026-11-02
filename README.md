# Leafbloom

A very slow multiplayer plant idler. Firebase handles sign-in and the shared garden.

## Files

- `index.html`: the whole game
- `firebase-config.js`: your Firebase project keys (fill this in)
- `firestore.rules`: database security rules
- `firebase.json`: hosting and rules settings for the Firebase CLI

## Setup

1. Create a new project at https://console.firebase.google.com.
2. Add a Web app (the `</>` icon). Copy the config values into `firebase-config.js`.
3. Under Authentication > Sign-in method, enable Google.
4. Under Firestore Database, create a database (production mode).

## Deploy with Firebase Hosting

```
npm install -g firebase-tools
firebase login
firebase use --add
firebase deploy
```

This uploads the game and the rules. The game runs at `https://<project-id>.web.app`.

## Deploy with GitHub Pages instead

1. Push `index.html` and `firebase-config.js` to a repository and enable Pages.
2. Paste `firestore.rules` into Firestore > Rules and publish.
3. Add `<username>.github.io` under Authentication > Settings > Authorized domains.

## Testing locally

Opening `index.html` from disk works on your device only, without the shared garden.
To test sign-in, run a local server in this folder, for example `npx serve` or
`python -m http.server`. Then add `localhost` to the authorized domains, if it isn't there already.

## Collections

All collections start with `lb_`: `lb_saves`, `lb_garden`, `lb_clans` (with `tree` and `msgs`
subcollections), `lb_drops`, `lb_bugs`, `lb_bees` and `lb_worms`.
