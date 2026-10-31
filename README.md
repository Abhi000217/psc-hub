# Kerala PSC Study Hub

A responsive Next.js + TypeScript starter website for a Kerala PSC learning platform.

## Included in this starter
- Responsive homepage and navigation
- Study notes marketplace with sample free and premium listings
- Sample interactive quiz with answer explanations and score
- Admin dashboard preview for adding sample listings and setting prices
- Supabase SQL schema for profiles, notes, questions, purchases and quiz attempts
- Environment variable template

## Run locally
1. Install Node.js 20.9 or newer.
2. Extract this project and open a terminal in the project folder.
3. Run `npm install`.
4. Copy `.env.example` to `.env.local` and fill in your Supabase project values when ready.
5. Run `npm run dev` and open http://localhost:3000.

The demo UI runs without Supabase credentials. The database-backed features are not connected yet.

## Before launching publicly
This is a functional frontend starter, not a production-ready paid-content service. The admin page is deliberately marked DEMO MODE and is not protected by authentication. The sample purchase buttons are disabled. Do not accept real payments or upload paid PDFs until you implement:

1. Supabase Auth and server-side role checks for admins.
2. Private Supabase Storage bucket for paid PDFs; issue short-lived signed URLs only after checking a verified purchase.
3. Server-side Razorpay order creation using the price fetched from the database.
4. Razorpay signature verification on the server/webhook before recording a purchase as `paid`.
5. Admin-only server routes for creating/updating notes and prices.
6. Privacy policy, terms, refund policy, contact details and applicable tax/payment compliance.
7. Review of all PSC facts, answer keys and current-affairs material before publishing.

Never expose Supabase service-role keys or Razorpay secret keys in browser code. Do not use client-side payment status as proof of payment. Enable and test Row Level Security policies before adding real student data.

## Suggested next development steps
- Connect Supabase Auth for student registration/login.
- Build protected student dashboard and purchased-notes library.
- Add admin-only note upload and price management.
- Integrate Razorpay test mode, then complete verification before live mode.
- Add search/filtering, real question bank, mock-test builder and current affairs publishing.

## Install on Android as an app (PWA)
This project now includes Progressive Web App support: an app manifest, install icons, a service worker, and an offline fallback page. It can be installed from a supported mobile browser after the site is deployed over HTTPS.

1. Deploy the Next.js project to a host that serves it over HTTPS (for example, Vercel).
2. Open the deployed website in Chrome on your Android phone.
3. Open Chrome's menu (three dots) and choose **Install app** or **Add to Home screen**.
4. Confirm. The PSC Study Hub icon will appear on your home screen and open in an app-like full-screen window.

On iPhone, open the site in Safari, tap **Share**, then choose **Add to Home Screen**.

The PWA is an installable mobile web app, not a Play Store APK. A public HTTPS deployment is required for service-worker installation. The offline fallback is available, but live quizzes, account features, payments and remote PDFs still need an internet connection and their backend integrations.
