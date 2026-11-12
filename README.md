# Cheap UC Store — Firebase Hosting starter

This is a responsive, front-end demo storefront prepared for Firebase Hosting.

## Included
- `public/index.html` — storefront UI, UC pack selector, quantity controls, and demo order summary
- `firebase.json` — Firebase Hosting configuration
- `.firebaserc.example` — project ID template

## Important before launch
This build is **demo-only**. It does not collect payments, verify UPI transactions, persist orders, or deliver UC. Do not advertise demo orders as paid or fulfilled. Before accepting real orders, obtain/retain the supplier authorization and implement:
1. A verified payment provider checkout (never trust a client-side “paid” button or screenshot).
2. A server-side payment webhook that verifies the provider signature and amount.
3. A protected backend/database with strict access rules and minimal personal-data collection.
4. Admin authentication and role-based authorization.
5. Accurate supplier costs, stock/fulfilment rules, refund policy, privacy notice, and terms.

Do not place payment gateway secret keys, service-account JSON, or admin passwords in `index.html`.

## Deploy to Firebase Hosting
1. Install Node.js LTS from https://nodejs.org/
2. Install Firebase CLI: `npm install -g firebase-tools`
3. Sign in: `firebase login`
4. In this folder, create the hosting directory and copy the page:
   - macOS/Linux: `mkdir -p public && cp index.html public/index.html`
   - Windows PowerShell: `New-Item -ItemType Directory -Force public; Copy-Item index.html public/index.html`
5. Create a Firebase project in https://console.firebase.google.com/ and copy its Project ID.
6. Run `firebase use --add` and select that project.
7. Run `firebase deploy --only hosting`
8. Firebase will print the live `web.app` and `firebaseapp.com` URLs.

## Local preview
After installing Firebase CLI, run `firebase emulators:start --only hosting`.
