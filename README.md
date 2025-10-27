
# FootprinTrails — Ready-to-Deploy (Vercel)

This package contains a deployable monorepo for **FootprinTrails** (client + server).

Quick summary:
- Client: React (Vite) — pages, map, booking modal, success & cancel pages.
- Server: Express — `/api/create-checkout-session`, `/api/webhook`, `/api/subscribe`, `/api/admin/bookings`.
- Stripe Checkout + SendGrid webhook example included.
- Admin protected by `ADMIN_SECRET` env var.

## How to deploy to Vercel (recommended)
1. Push this repo to GitHub.
2. In Vercel, click "New Project" → import from GitHub.
3. For monorepo, set Root to `/` and use the provided `vercel.json` (this repo uses a build for client and serverless functions).
4. Add Environment Variables in Vercel Dashboard:
   - STRIPE_SECRET_KEY
   - STRIPE_WEBHOOK_SECRET
   - REACT_APP_STRIPE_PUBLISHABLE_KEY
   - SENDGRID_API_KEY
   - FROM_EMAIL (shreya.acharyya@gmail.com)
   - ADMIN_SECRET (SIVA1503)
   - CLIENT_URL (https://footprintrails.vercel.app)

## Local run (development)
### Server
```bash
cd server
npm install
cp .env.example .env   # fill values
node server.js
```
Server default: http://localhost:4242

### Client
```bash
cd client
npm install
npm run dev
```
Client default: http://localhost:5173

