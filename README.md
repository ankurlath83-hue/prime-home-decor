# Prime Home Decor

The business app for Prime Home Decor (Anita Lath & Neha Lath): stock with photos, purchase bills split between partners, sales, customers and resellers, partner money, expenses, profit dashboard and promotion posts.

**Open it:** https://ankurlath83-hue.github.io/prime-home-decor/

On iPhone, open the link in Safari, tap Share, then **Add to Home Screen**. It opens full screen like an app.

## How it's built

- `index.html` is the whole app. The Orders tab tracks customer orders (taken → packed → dispatched → delivered → paid) on a timeline; delivering an order records the sale and reduces stock. Purchases can be marked "in transit". The Godowns tab shows stock by place (godowns, partners' homes, each reseller); stock moves are stored in the `sales` collection with `type: "move"`, and reseller stock stays ours until a sale is recorded from their place. The Dashboard lists late orders, reorder suggestions and reseller follow-ups. Orders are stored in the `sales` collection with `type: "order"`. The Catalogue tab builds a customer catalogue (rates = retail × a markup you set) from the Stock list and saves it as a PDF. Material flow follows goods from supplier order (ordered → on the way → in stock) to customer order and payment, with a per-product journey. Damaged goods are stored in `sales` with `type: "damage"`; they leave stock and their landed cost (less money recovered from supplier claims) counts against profit. Sale bills, purchases, damage claims and statements export as PDF and share to WhatsApp. Lists show as cards (Table view switch in the header).
- Data and photos are kept in Firebase project `phdapp-937d7` (Firestore, Mumbai). Sign-in uses email and password.
- `firestore.rules` allows only the owner (ankurlath83@gmail.com) and the emails the owner adds in the Partners tab. Paste it into Firebase console → Firestore → Rules → Publish after any change.
- `sw.js` and `manifest.webmanifest` make it installable and let it open without internet.

## Lath Diary

A private diary at https://ankurlath83-hue.github.io/prime-home-decor/diary/ (folder `diary/`). Anyone can create an account; each account sees only its own diary, photos and voice notes (Firestore `diaries/{uid}`). The page holds no personal data: entries live only in each person's account.
