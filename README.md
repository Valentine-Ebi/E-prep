# iWanPass

iWanPass helps students prepare for exams with past questions, AI-generated quizzes, and progress tracking.

## Run locally

1. Install Node.js 22.12 or newer and run `npm ci`.
2. Create `.env.local` with `VITE_SUPABASE_URL` and `VITE_SUPABASE_PUBLISHABLE_KEY` from your Supabase project.
3. Run `npm run dev`. Vite serves the app at `http://localhost:3000`.

## Auth email links

In Supabase Authentication → URL Configuration, allow `http://localhost:3000/auth` for sign-up confirmation and `http://localhost:3000/reset-password` for password recovery. Add the equivalent URLs for each deployed origin. Set the Site URL to the correct deployment origin. If you use custom email templates, ensure they honor the redirect URL passed by the app.

The selected student category is saved in Supabase Auth user metadata as `category`, alongside `full_name`. It is not a column in the current `profiles` table.

Run `npm test` for auth validation and component tests, and `npm run build` for the production bundle. A live Supabase project is needed to verify email delivery, confirmation links, and password recovery end to end.
