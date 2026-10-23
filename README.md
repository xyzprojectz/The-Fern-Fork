# The Fern & Fork — Restaurant + Stay Website

A responsive, single-page restaurant and boutique-stay website made with plain HTML, CSS and JavaScript. No build tools or paid hosting required.

## Run locally
1. Extract the ZIP.
2. Open `index.html` in Chrome, Edge or Firefox.
3. Click **Edit website** at the bottom-right to customise the site.
4. Use the edit buttons to update menu items, room names/prices/descriptions, offers, and photo URLs.
5. You can upload photos in the editor. Browser uploads are stored in that browser's local storage; keep photos reasonably small.

## Put it on GitHub Pages
1. Sign in to GitHub and create a **public** repository, e.g. `miniature-restaurant-website`.
2. Upload `index.html` and `README.md` from this folder to the repository root (not inside an extra nested folder).
3. Open repository **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Choose branch `main` and folder `/(root)`, then click **Save**.
6. Wait a minute or two and open the published URL shown in Settings → Pages.

## Important notes
- Currency is Philippine pesos (PHP / ₱). Menu and room prices are editable.
- The menu add buttons, booking request summary and newsletter are demo interactions only. They do not take payments, send emails, or create real reservations.
- The editor stores changes in the browser's local storage. Those changes do **not** automatically update the live GitHub website or appear on another device/browser. To publish permanent changes, edit `index.html` and commit/push the changes, or later connect a database/CMS.
- Uploaded photos are stored in local browser storage and are not included in GitHub automatically. For permanent live images, add them to the repo (e.g. an `images/` folder) and use their relative paths like `images/restaurant-entry.jpg`.
- Images currently use remote Unsplash photo URLs as placeholders. Replace with your own model photos and only use images you have permission to publish.
- For real bookings, email, availability, or payments, connect a secure backend/form service. Do not collect real customer data with this demo alone.

## New features: search, orders, feedback and live dashboard

- Menu search with suggestions for available items, categories, descriptions and PHP prices.
- Shopping basket with quantity controls and estimated total.
- Demo food-order form records items, quantities, contact details, requested date/time and submission timestamp.
- Booking requests record booking type, guest count, requested date/time and timestamp.
- Guest feedback with star ratings and recent feedback display.
- `admin.html` provides an authenticated developer dashboard for food orders, bookings and feedback. It listens for real-time updates from Firebase.
- `firebase-config.js` is a placeholder until you add your Firebase web-app config. Without Firebase, records stay in the current browser and are not shared with the developer or other visitors.
- `firestore.rules` is starter security configuration; review and strengthen it before any real use.

### Enable shared real-time data
1. Create a project at https://console.firebase.google.com/ and add a Web App.
2. Copy its web configuration into `firebase-config.js`.
3. Create a Cloud Firestore database.
4. In Firebase Authentication, enable Email/Password and create your own admin user. The site has no public admin sign-up form.
5. Paste `firestore.rules` into Firestore → Rules and publish. These rules are only a starter; add stronger validation and anti-spam protection before using with real customers.
6. Upload `index.html`, `admin.html`, `firebase-config.js`, `firestore.rules`, and `README.md` to the GitHub repository root and publish using GitHub Pages.
7. Visit `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/admin.html` and sign in. Test a sample order, booking and feedback post; the dashboard should update live.

**Important:** GitHub Pages itself cannot store shared data. Firebase provides the shared database and real-time feed. This demo does not take payment, guarantee room availability, send email, or notify a kitchen by itself. Do not store sensitive customer data until you have proper security, privacy notices, and production-ready validation.
