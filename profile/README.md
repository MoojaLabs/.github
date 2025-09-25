# Mooja – Protest Coordination Platform

> **TL;DR:** Mooja centralizes verified protest events and gives NGOs tools to organize effectively — solving fragmentation, mistrust, and low turnout caused by using scattered tools like Facebook, WhatsApp, and Twitter.

---

## 🚀 Quick Links

* **Live Mobile Demo:** [Open in Appetize](https://appetize.io/app/b_vneagh6iro3ck2qydt6nkmwhuy) (no install needed)
* **Main Website:** [mooja.app](https://mooja.app)
* **Tech Repos:** [Mobile](https://github.com/MoojaLabs/mooja-mobile) • [Server](https://github.com/MoojaLabs/mooja-server) • [Admin Dashboard](https://github.com/MoojaLabs/mooja-admin)

---

## 📌 What Mooja Solves

* **Fragmentation:** Protest details are scattered across multiple apps → Mooja unifies them in one feed.
* **Mistrust:** Events come only from verified organizations → protestors know what’s legit.
* **Coordination Chaos:** Organizations get a dashboard to manage events, volunteers, and logistics.

---

## 🛠️ Project Structure

| Component        | Purpose                                                                   | Tech                                  |
| ---------------- | ------------------------------------------------------------------------- | ------------------------------------- |
| **Mooja Mobile** | Flutter app for protestors & organizers. Login-free feed + org dashboard. | Flutter, Dart, BloC                   |
| **Mooja Server** | REST API + org verification + protest management.                         | NestJS, Prisma, PostgreSQL (Supabase) |
| **Mooja Admin**  | Next.js dashboard for reviewing org applications & managing data.         | Next.js, Supabase, shadcn/ui          |

---

## 🧪 Demo Setup (Local)

You can spin up Mooja locally in under 5 minutes using [Railway](https://railway.app/).

### 1. Clone & Run Server

```bash
git clone https://github.com/MoojaLabs/mooja-server.git
cd mooja-server

# Install dependencies
npm install

# Setup environment
cp .env.example .env

# Database
npx prisma generate
npx prisma migrate dev
npm run prisma:seed

# Start dev server
npm run start:dev
```

Your API will run at `http://localhost:3000/api`.

---

### 2. Run Mobile App

```bash
git clone https://github.com/MoojaLabs/mooja-mobile.git
cd mooja-mobile
flutter pub get

# Create .env in project root
API_BASE_URL=http://localhost:3000/api

flutter run
```

---

### 3. Run Admin Dashboard

```bash
git clone https://github.com/MoojaLabs/mooja-admin.git
cd mooja-admin
npm install

# Setup environment
cp .env.example .env.local
npx prisma db push

npm run dev
```

Dashboard will be available at `http://localhost:3001`.

---

## 📱 Key Features

* **Public Feed (No Login):** Country-based filtering, infinite scroll, verified-only events.
* **Org Verification Flow:** Social media handle submission + invite-code validation.
* **Org Dashboard:** Event creation, management, and analytics (in development).
* **Admin Panel:** Approve/reject orgs, manage protests, issue invite codes.

---

## 📊 Tech Highlights

* **Secure:** JWT auth, Supabase storage, role-based org access.
* **Scalable:** Modular NestJS server + Prisma ORM + PostgreSQL.
* **Cross-platform:** iOS + Android from a single Flutter codebase.
* **Dev-friendly:** `.env` based config, Railway deployment ready, Prisma studio for DB.

---

## 📜 License

Licensed under **GNU AGPL-3.0** — open-source.
