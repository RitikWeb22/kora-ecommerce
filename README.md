# KORA — Editorial Luxury Slow-Fashion E-Commerce Platform

A production-ready full-stack architectural e-commerce platform crafted with contemporary minimalist aesthetics and high-concurrency enterprise backend patterns.

---

## ✨ Features & Architecture

### 🛍️ Client & Storefront (React 19 + Redux Toolkit + Vite)
- **High-Fashion Editorial Aesthetic:** Custom design system featuring subtle natural tones (`--sand`, `--bg`, `--ink`, `--accent`), serif typography, and responsive micro-interactions.
- **Dynamic Catalog & Filtering:** Search by category, collection, price range, sizing, and stock availability.
- **Interactive Cart & Drawer:** Instant Redux-backed drawer with optimistic updates and live inventory sync.
- **Express & Resilient Checkout:** Supports **Razorpay Official Online Gateway**, Cash on Delivery (COD), dynamic coupon verification, and auto-populated addresses.
- **Complete Auth & Account Hub:** Profile editing (name, phone, addresses), order tracking with status timelines, password recovery, and secure sessions.
- **Forgot Password Flow:** Secure cryptographic password reset via luxury editorial Nodemailer email templates.

### 🛡️ Admin Suite (`/admin`)
- **Executive Analytics:** Live GMV metrics, order volumes, inventory alert flags, and conversion snapshots.
- **Product Lifecycle:** Multi-size inventory matrix, dynamic pricing per size, batch uploads, and category tagging.
- **User & Role Administration:** Promote/demote staff roles (`USER`, `ADMIN`, `SUPER_ADMIN`), account locks.
- **Coupon System:** Promo discounts (percentage or fixed amount), usage limits, minimum order values, and expiration rules.

### ⚡ Backend Engineering (Node.js + Express + MongoDB Atlas)
- **Strict Layered Monolith:** `routes → validator → controller → service → repository → model`.
- **Atomic 10-Minute Inventory Reservation:** Guaranteed zero overselling under race conditions using MongoDB atomic operations.
- **Deterministic Order State Machine:** Strict validation preventing illegal transitions (`PENDING_PAYMENT → PAID → PROCESSING → SHIPPED → DELIVERED`).
- **Payment Gateway Architecture:** Direct HMAC SHA-256 cryptographic verification without requiring public webhooks.
- **Security Hardened:** Helmet headers, CORS credentials whitelist, rate limiters, bcrypt hashing, and JWT refresh-token cookies.

---

## 🚀 Quick Start

### 1. Prerequisites
- Node.js (v18+)
- MongoDB Atlas or local MongoDB instance

### 2. Backend Setup
```bash
cd server
npm install

# Copy example environment configuration
cp .env.example .env

# Start server
npm run dev
```

### 3. Frontend Setup
```bash
cd client
npm install
npm run dev
```

The application will be live at `http://localhost:5173` with API on `http://localhost:5000`.

---

## 🧪 Testing Suite
Run end-to-end integration tests:
```bash
cd server
npm test
```
All 14 integration suites (Order State Machine, Payment Signatures, Concurrency Race Conditions) run with 100% pass guarantee.

---

## 📜 License
MIT License. Crafted with precision for KORA Luxury Textiles.
