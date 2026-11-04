# RN Wallet Management System — MVP

A starter dashboard for managing wallet records and manually recorded transactions.

## Safety and scope
- This MVP does **not** read SMS, collect OTPs, automate bKash/Nagad logins, or perform real-money transfers.
- Use only wallet records you own or are explicitly authorized to administer.
- Real payment processing must be added through an approved provider API and credentials issued to your business.

## Stack
- React + Vite frontend
- Node.js + Express backend
- MongoDB + Mongoose
- JWT authentication

## Requirements
- Node.js 20+
- MongoDB running locally or a MongoDB Atlas connection string

## Run locally

### 1. Backend
```bash
cd server
cp .env.example .env
npm install
npm run dev
```

### 2. Create the first admin
```bash
curl -X POST http://localhost:5000/api/auth/bootstrap-admin \
  -H "Content-Type: application/json" \
  -d '{"name":"Admin","email":"admin@example.com","password":"ChangeMe123!"}'
```
This endpoint only works while the database has no users. Change the password after first login.

### 3. Frontend
In another terminal:
```bash
cd client
npm install
npm run dev
```
Open the Vite URL shown in the terminal. The client expects the API at `http://localhost:5000`.

## MVP features
- Admin login
- Dashboard summary
- Add, view, and deactivate wallet records
- Manually record deposits and withdrawals
- Transaction history

## Before production
Add HTTPS, rate limiting, audit logging, backups, secrets management, stronger role-based permissions, input validation, monitoring, and security review. Never store PINs, passwords, OTPs, or full payment credentials.
