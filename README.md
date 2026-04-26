# UniTask — Student Freelance Platform

A full-stack freelance marketplace built for university students, powered by React + Supabase.

## 🚀 Quick Start

### Prerequisites
Install Node.js from https://nodejs.org (LTS version recommended)

### Setup

```bash
# 1. Unzip the project folder and open terminal inside it
cd unitask

# 2. Install dependencies
npm install

# 3. Start development server
npm run dev
```

Open http://localhost:5173 in your browser.

---

## 🗂️ Project Structure

```
src/
├── components/
│   └── layout/        # Navbar, Layout wrapper
├── context/
│   └── AuthContext.jsx # Auth state, login/signup/logout
├── lib/
│   └── supabase.js    # Supabase client
├── pages/
│   ├── Login.jsx
│   ├── Register.jsx
│   ├── ForgotPassword.jsx
│   ├── Feed.jsx        # Job listing with search + filter
│   ├── JobDetail.jsx   # Apply, select applicant, report
│   ├── PostJob.jsx     # Post a job (escrow deducted)
│   ├── Profile.jsx     # View & edit profile
│   ├── Chat.jsx        # Real-time messaging + dispute
│   ├── Wallet.jsx      # Balance, top-up, transactions
│   ├── Notifications.jsx
│   └── AdminPanel.jsx  # Disputes, reports, user management
└── App.jsx            # Routes
```

---

## 🔐 Supabase Project

- **Project:** UniTask
- **URL:** https://obanhuxsyjeovqvcqxew.supabase.co
- **Region:** ap-south-1 (Mumbai)

### Database Tables
| Table | Purpose |
|-------|---------|
| users | Core user accounts |
| student_profiles | Student-specific info |
| client_profiles | Client-specific info |
| wallets | One wallet per user |
| job_posts | Job listings |
| applications | Job applications |
| chat_rooms | Per-job chat |
| messages | Chat messages (real-time) |
| notifications | In-app alerts |
| transactions | Wallet history |
| ratings | Post-job ratings |
| disputes | Raised via chat |
| reports | Job post reports |

### Auto-triggers
- New signup → creates user + wallet + profile automatically
- Job posted → payment escrowed from wallet
- Job completed → payment released to worker
- Rating submitted → student avg_rating updated

---

## 👤 Roles

| Role | Can Post Jobs | Can Apply | Admin Panel |
|------|:---:|:---:|:---:|
| Student (.edu/.ac.bd email) | ✅ | ✅ | ❌ |
| Client | ✅ | ❌ | ❌ |
| Admin | ✅ | ✅ | ✅ |

To make a user admin: in Supabase dashboard → Table Editor → users → change `role` to `admin`.

---

## 📱 Features
- ✅ Email OTP verification via Supabase Auth
- ✅ .edu / .ac.bd email restriction for students
- ✅ Job feed with search + category filter
- ✅ Escrow payment system
- ✅ Real-time chat (Supabase Realtime)
- ✅ Dispute resolution system
- ✅ Rating system (triggers avg update)
- ✅ Admin panel (disputes, reports, wallet management)
- ✅ Notification system with unread indicators

---

## 🔧 Enabling Email Verification
In Supabase Dashboard → Authentication → Email → make sure "Confirm email" is enabled.
