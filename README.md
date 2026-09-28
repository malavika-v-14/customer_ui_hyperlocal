# Nearby — customer UI

Friendly Local customer experience in white and `#104850`, using Plus Jakarta Sans. This project contains customer screens only; no provider or admin UI.

## Run

```bash
npm install
npm run dev
```

Open the local URL shown by Vite. For a production build run `npm run build`.

## Included

Phone sign-in interface with demo OTP `123456`, home and category discovery, ranked provider search, functional filters, provider details, saved addresses, appointment booking, payment preference, booking tracking, and post-completion review with optional image selection. The illustration is bundled locally. Sample providers and prices are illustrative.

The app uses localStorage for demo persistence. A **Simulate provider completion** control appears on the booking detail page to review the customer payment and review journey without a provider backend. This control should be removed when API-driven job statuses are connected.

## Backend handoff

The UI domain objects in `src/data.ts` and `src/App.tsx` can be mapped to customer-facing endpoints: OTP request/verify, categories, nearby providers (visibility_score descending, then level, rating_avg, total_jobs), provider detail/reviews/availability, saved addresses, customer bookings, completion/payment confirmation, and review submission with images. The backend must validate OTP, booking availability, payment status, image uploads, and ranking. No real OTP is sent or money collected by this standalone frontend. Payment preference is chosen during booking; payment is recorded only after completion. The future in-app wallet is displayed as unavailable.
