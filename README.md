# Prime Home Decor

The business app for Prime Home Decor (Anita Lath & Neha Lath): stock with photos, purchase bills split between partners, sales, customers and resellers, partner money, expenses, profit dashboard and promotion posts.

**Open it:** https://ankurlath83-hue.github.io/prime-home-decor/

On iPhone, open the link in Safari, tap Share, then **Add to Home Screen**. It opens full screen like an app.

## How it's built

- `index.html` is the whole app.
- Data and photos are kept in Firebase project `phdapp-937d7` (Firestore, Mumbai). Sign-in uses email and password.
- `firestore.rules` allows only the owner (ankurlath83@gmail.com) and the emails the owner adds in the Partners tab. Paste it into Firebase console → Firestore → Rules → Publish after any change.
- `sw.js` and `manifest.webmanifest` make it installable and let it open without internet.

## Lath Diary

A private diary at https://ankurlath83-hue.github.io/prime-home-decor/diary/ (folder `diary/`). Anyone can create an account; each account sees only its own diary, photos and voice notes (Firestore `diaries/{uid}`). The page holds no personal data: entries live only in each person's account.
