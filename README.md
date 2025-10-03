Ecommerce Next.js + Node.js + PostgreSQL scaffold
=================================================

What is included
- backend/  -> Node.js + Express + Prisma schema and basic routes (auth, products, orders, admin)
- frontend/ -> Next.js app with pages: index, product, admin, auth
- README with setup instructions

Important env variables (fill before running):
- Backend:
  - DATABASE_URL (PostgreSQL connection string)
  - JWT_SECRET
  - CLOUDINARY_URL (optional, for image uploading)
  - STRIPE_SECRET (optional, for Stripe payments)
- Frontend:
  - NEXT_PUBLIC_API_URL (e.g. http://localhost:4000/api or live backend URL)

Quick local setup (backend):
  cd backend
  npm install
  # create .env with DATABASE_URL and JWT_SECRET
  npx prisma generate
  npx prisma migrate dev --name init
  npm run dev

Quick local setup (frontend):
  cd frontend
  npm install
  # create .env.local with NEXT_PUBLIC_API_URL=http://localhost:4000/api
  npm run dev

Notes:
- This scaffold is a starting point. For production, configure HTTPS, CORS, secure JWT secrets, refresh tokens, rate limiting, logging, etc.
- Payment integration with Stripe is referenced in package.json; implement server-side Stripe checkout endpoints when ready.
- For image uploads, use Cloudinary: set CLOUDINARY_URL in backend env and use /api/admin/upload endpoint.
