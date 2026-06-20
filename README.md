# 🔐 Decentralized Cryptocurrency Wallet System

**A complete blockchain-based cryptocurrency wallet application with user authentication, wallet management, UTXO transactions, mining, zakat calculation, and admin panel.**

> **Status**: ✅ **Production Ready** | All 7 core modules + 3 bonus features fully implemented and tested

---

## 📌 Quick Links

- 🌐 **Live Frontend**: https://crypto-wallet-plum.vercel.app/
- 📖 **Documentation**: See sections below

---

## 🖼️ Screenshots

![Screenshot](assets/Screenshot%202026-06-18%20220733.png)

![Screenshot](assets/Screenshot%202026-06-18%20220919.png)

![Screenshot](assets/Screenshot%202026-06-18%20220954.png)

![Screenshot](assets/Screenshot%202026-06-18%20221030.png)


## 🎯 Project Overview

This is a full-stack **decentralized cryptocurrency wallet system** implementing:
- Complete blockchain with **Proof-of-Work mining**
- **UTXO (Unspent Transaction Output)** model (like Bitcoin)
- **Merkle root verification** for block integrity
- **Islamic finance integration** (Zakat calculation)
- **Admin dashboard** for system management
- **Google OAuth** authentication
- Modern, responsive UI with light theme

Built with **Go, React, MongoDB** and deployed on **Render + Vercel**.

---

## ✨ Features Completed

### Core Modules (7/7) ✅

| Module | Features |
|--------|----------|
| **1. User Authentication** | Signup with CNIC, OTP email verification, JWT login, profile management |
| **2. Wallet System** | Generate wallets, view balance, manage multiple wallets, export keys |
| **3. UTXO Model** | Track unspent outputs, prevent double spending, UTXO validation |
| **4. Transactions** | Send money, receive funds, transaction history, fee calculation |
| **5. Blockchain** | Mine blocks with PoW, Merkle tree, genesis block, chain validation |
| **6. Zakat Calculation** | Auto-calculate 2.5% Islamic zakat, track payable zakat |
| **7. Reports & Logs** | Activity logs, transaction history, system statistics |

### Bonus Features (3/3) ✅

1. **🔐 Google OAuth** - Sign in with Google account
2. **🌳 Merkle Root Verification** - Cryptographic block verification
3. **👨‍💼 Admin Panel** - User management, transaction viewing, blockchain explorer

### UI/UX Enhancements ✅

- ✨ Modern light theme with gradient backgrounds
- 📱 Fully responsive (mobile, tablet, desktop)
- ⚡ Smooth animations and transitions
- 🎨 Professional card-based layout
- 🔄 Real-time data updates
- ♿ Accessible design with proper contrast

---

## 🛠 Technology Stack

### Backend
- **Language**: Go 1.21+
- **Framework**: Gin (HTTP web framework)
- **Database**: MongoDB Atlas (cloud)
- **Authentication**: JWT + Google OAuth 2.0
- **Security**: bcrypt (password hashing), RSA/ECDSA keys
- **Logging**: Structured logging with debugging

### Frontend
- **Library**: React 19.2.1
- **Styling**: Tailwind CSS 3.0
- **Router**: React Router 7.10.1
- **HTTP Client**: Axios
- **OAuth**: Google Identity Services
- **Build**: Create React App with Node.js

### Deployment
- **Backend**: Render (native Go deployment)
- **Frontend**: Vercel (SPA with client-side routing)
- **Database**: MongoDB Atlas (free tier)
- **Version Control**: GitHub

---

## 📁 Project Structure

```
CryptoWallet/
├── backend/                          # Go backend (Gin + MongoDB)
│   ├── controllers/
│   │   ├── auth_controller.go        # Auth with OTP verification
│   │   ├── wallet_controller.go      # Wallet generation & management
│   │   ├── utxo_controller.go        # UTXO & transaction handling
│   │   └── admin_controller.go       # Admin operations
│   ├── models/
│   │   ├── user.go                   # User schema with OAuth
│   │   ├── wallet.go                 # Wallet structure
│   │   └── utxo.go                   # UTXO model
│   ├── routes/
│   │   ├── auth_routes.go
│   │   ├── wallet_routes.go
│   │   ├── utxo_routes.go
│   │   ├── admin_routes.go
│   │   ├── zakat_routes.go
│   │   ├── blockchain_routes.go
│   │   ├── logs_routes.go
│   │   └── reports_routes.go
│   ├── middleware/
│   │   └── auth_middleware.go        # JWT validation & admin check
│   ├── crypto/
│   │   ├── encryption.go
│   │   └── keys.go                   # RSA/ECDSA key generation
│   ├── database/
│   │   └── connection.go             # MongoDB connection with TLS
│   ├── utils/
│   │   ├── hash.go
│   │   ├── jwt.go
│   │   └── email.go                  # OTP email sending
│   ├── main.go
│   ├── go.mod
│   ├── Dockerfile
│   └── .env                          # Configuration

├── frontend/                         # React frontend (Tailwind CSS)
│   ├── src/
│   │   ├── pages/
│   │   │   ├── Login.js              # Login with Google OAuth
│   │   │   ├── Signup.js             # Signup with CNIC
│   │   │   ├── VerifyOTP.js          # Email OTP verification
│   │   │   ├── Dashboard.js          # Main dashboard
│   │   │   ├── WalletProfile.js      # Wallet details
│   │   │   ├── Beneficiaries.js      # Manage beneficiaries
│   │   │   └── Admin.js              # Admin panel with 4 tabs
│   │   ├── components/
│   │   │   └── Navbar.js             # Navigation with user menu
│   │   ├── context/
│   │   │   └── AuthContext.js        # Auth state & Google OAuth
│   │   ├── services/
│   │   │   └── api.js                # Axios instance & API methods
│   │   ├── App.js
│   │   └── index.js
│   ├── package.json
│   ├── tailwind.config.js
│   └── .env

├── render.yaml                       # Render deployment config
├── README.md                         # This file
└── .github/                          # GitHub workflows (optional)
```

---

## 🚀 Getting Started

### Prerequisites
- **Go** 1.21+
- **Node.js** 18+ with npm
- **MongoDB Atlas** account (free)
- **Google OAuth** credentials (optional)

### Local Development (5 minutes)

#### 1. Backend Setup

```bash
cd backend

# Create .env file
cat > .env << EOF
MONGO_URI=mongodb+srv://USER:PASS@cluster.mongodb.net/crypto_wallet?retryWrites=true&w=majority
JWT_SECRET=your-secret-key-min-32-chars
PORT=8080
ENVIRONMENT=development
FRONTEND_URL=http://localhost:3000
EOF

# Install & run
go mod download
go run main.go
```

Backend runs on: `http://localhost:8080`

#### 2. Frontend Setup

```bash
cd frontend

# Create .env file
cat > .env << EOF
REACT_APP_API_URL=http://localhost:8080/api
REACT_APP_GOOGLE_CLIENT_ID=YOUR_GOOGLE_CLIENT_ID
EOF

# Install & run
npm install
npm start
```

Frontend opens at: `http://localhost:3000`

---

## 📖 How to Use

### 1. Create Account

1. Go to http://localhost:3000/signup
2. Fill in:
   - Full Name: John Doe
   - Email: test@example.com
   - CNIC: 12345-1234567-1
   - Password: password123
3. Click "Sign Up"

### 2. Verify Email

1. Check backend console for OTP (6-digit code)
2. Enter OTP in verification page
3. Redirected to login

### 3. Login

1. Enter credentials
2. Access dashboard
3. Shows "Generate Wallet" button

### 4. Create Wallet

1. Click "Generate Wallet" on dashboard
2. Enter wallet name
3. Wallet address is generated from public key
4. Balance initially = 0

### 5. Get Initial Funds

**Option A: Mine Genesis Block** (First user only)
```
Click "Mine Block" → Creates genesis block → Get 50 coins
```

**Option B: Receive from Another User**
```
User A sends to User B's wallet address
```

### 6. Send Transaction

1. Go to your wallet
2. Click "Send Money"
3. Enter recipient's wallet address and amount
4. Transaction added to mempool

### 7. Mine Block

1. Click "Mine Block" button
2. Proof-of-Work mining starts (1-2 minutes)
3. Block mined with all pending transactions
4. Transactions confirmed, miner gets 50 coins reward

### 8. View Blockchain

1. Go to Dashboard → Blocks tab
2. See all mined blocks with:
   - Block height, timestamp
   - Merkle root (proves transactions)
   - Nonce (proof-of-work)
   - Transactions count

### 9. Admin Panel (If Admin)

1. Login with admin account
2. Click "Admin Panel" in navbar
3. Access:
   - **Dashboard**: System stats, user count, wallet metrics
   - **Users**: List users, toggle admin status, delete users
   - **Transactions**: View all transactions with search/filter
   - **Blocks**: Blockchain explorer with all block details

---

## 🔌 API Endpoints

### Base URL
```
http://localhost:8080/api
```

### Authentication
```bash
# Signup
POST /auth/signup
{ "fullName": "John", "email": "john@example.com", "cnic": "12345-1234567-1", "password": "pass123" }

# Verify OTP
POST /auth/verify-otp
{ "email": "john@example.com", "otp": "123456" }

# Login
POST /auth/login
{ "email": "john@example.com", "password": "pass123" }

# Google OAuth
POST /auth/google
{ "token": "google-id-token" }

# Get Profile
GET /auth/profile
Authorization: Bearer JWT_TOKEN
```

### Wallets
```bash
# Generate Wallet
POST /wallet/generate
Authorization: Bearer JWT_TOKEN

# Get My Wallet
GET /wallet/my-wallet
Authorization: Bearer JWT_TOKEN

# Get Balance
GET /utxo/my-balance
Authorization: Bearer JWT_TOKEN
```

### Transactions
```bash
# Send Transaction
POST /transaction/send
{ "senderWalletId": "...", "recipientAddress": "...", "amount": 10 }

# Get My Transactions
GET /transaction/my-transactions
Authorization: Bearer JWT_TOKEN

# Get All Blocks
GET /blockchain/blocks
```

### Mining
```bash
# Mine Block
POST /blockchain/mine
Authorization: Bearer JWT_TOKEN

# Get My Mined Blocks
GET /blockchain/my-blocks
Authorization: Bearer JWT_TOKEN
```

### Zakat
```bash
# Calculate Zakat
POST /zakat/calculate
Authorization: Bearer JWT_TOKEN

# Get Zakat Summary
GET /zakat/summary
Authorization: Bearer JWT_TOKEN
```

### Admin (Admin-only)
```bash
# System Stats
GET /admin/stats
Authorization: Bearer ADMIN_TOKEN

# Get All Users
GET /admin/users
Authorization: Bearer ADMIN_TOKEN

# Get All Transactions
GET /admin/transactions
Authorization: Bearer ADMIN_TOKEN

# Get All Blocks
GET /admin/blocks
Authorization: Bearer ADMIN_TOKEN
```

---

## 🗄️ Database Schema

### Users Collection
```javascript
{
  _id: ObjectId,
  fullName: "John Doe",
  email: "john@example.com",
  cnic: "12345-1234567-1",
  password: "bcrypt-hash",
  walletIds: ["wallet-id-1"],
  publicKey: "public-key",
  privateKey: "encrypted-private-key",
  isVerified: true,
  isAdmin: false,
  googleId: "google-oauth-id",
  authProvider: "email" | "google",
  beneficiaries: [{
    name: "Jane Doe",
    email: "jane@example.com",
    walletAddress: "wallet-address",
    relationship: "Sister"
  }],
  otp: "123456",
  otpExpiry: ISODate,
  createdAt: ISODate,
  updatedAt: ISODate
}
```

### Wallets Collection
```javascript
{
  _id: ObjectId,
  userId: ObjectId,
  walletName: "My First Wallet",
  walletAddress: "unique-address-from-public-key",
  publicKey: "public-key-string",
  balance: 100,
  createdAt: ISODate
}
```

### Transactions Collection
```javascript
{
  _id: ObjectId,
  fromWallet: "sender-address",
  toWallet: "recipient-address",
  amount: 10,
  fee: 1,
  status: "pending" | "confirmed",
  inputs: [{
    txHash: "previous-tx-hash",
    outputIndex: 0,
    amount: 10
  }],
  outputs: [{
    walletAddress: "recipient-address",
    amount: 10
  }],
  signature: "transaction-signature",
  timestamp: ISODate,
  blockHeight: 5
}
```

### Blocks Collection
```javascript
{
  _id: ObjectId,
  blockHeight: 5,
  previousHash: "previous-block-hash",
  merkleRoot: "merkle-root-of-transactions",
  timestamp: ISODate,
  nonce: 12345,
  difficulty: 4,
  transactions: ["tx-id-1", "tx-id-2"],
  minedBy: "miner-wallet-address",
  reward: 50,
  isValid: true
}
```

---

## 🔒 Security Features

- ✅ **Passwords**: bcrypt hashing with cost 14
- ✅ **Authentication**: JWT tokens (7-day expiry)
- ✅ **OAuth**: Google OAuth 2.0
- ✅ **Private Keys**: RSA/ECDSA encryption
- ✅ **API Security**: Protected endpoints with middleware
- ✅ **CORS**: Configured for frontend URL
- ✅ **MongoDB**: Encrypted at rest (Atlas)
- ✅ **Email Verification**: OTP-based (10-minute expiry)

---

## 🚀 Production Deployment

### Deploy Backend to Render

1. Push code to GitHub
2. Go to https://render.com/dashboard
3. Create new Web Service:
   - Connect GitHub repository
   - Select Go 1.21 environment
   - Build: `go build -o app`
   - Start: `./app`
   - Environment variables:
     ```
     MONGO_URI=mongodb+srv://...
     JWT_SECRET=your-secret
     PORT=8080
     ENVIRONMENT=production
     FRONTEND_URL=https://your-vercel-url.vercel.app
     ```
4. Deploy and get URL: `https://your-backend.onrender.com`

### Deploy Frontend to Vercel

1. Go to https://vercel.com/dashboard
2. Import GitHub repository
3. Configure:
   - Framework: Create React App
   - Build: `npm run build`
   - Install: `npm install`
   - Root: `frontend`
4. Environment variable:
   ```
   REACT_APP_API_URL=https://your-backend.onrender.com/api
   ```
5. Deploy and get URL: `https://your-frontend.vercel.app`

### MongoDB Atlas Setup

1. Create cluster at https://www.mongodb.com/cloud/atlas
2. Create database user with password
3. Get connection string
4. Network Access: Allow 0.0.0.0/0 (for Render)
5. Update MONGO_URI in environment

---

## ✅ Testing Checklist

- [ ] User signup with CNIC
- [ ] Email OTP verification
- [ ] Login with credentials
- [ ] Create wallet
- [ ] View wallet balance
- [ ] Send transaction
- [ ] Mine block (PoW)
- [ ] Verify Merkle root
- [ ] View blockchain
- [ ] Calculate zakat
- [ ] Google OAuth login
- [ ] Admin panel access (if admin)
- [ ] Admin user management
- [ ] Admin transaction viewing
- [ ] Admin blockchain explorer

---

## 🐛 Troubleshooting

### Backend Issues

**MongoDB Connection Failed**
```
Solution:
1. Check connection string in .env
2. Whitelist your IP in MongoDB Atlas
3. Verify username/password
4. For Render: Allow 0.0.0.0/0
```

**Port Already in Use**
```
Solution: Change PORT in .env or kill process on port 8080
```

**OTP Not Sending**
```
Solution:
- Without SMTP config: OTP prints to console
- With SMTP: Ensure credentials are valid
```

### Frontend Issues

**Blank Page After Login**
```
Solution:
1. Check browser console (F12)
2. Verify REACT_APP_API_URL
3. Ensure backend is running
```

**API Calls Failing**
```
Solution:
1. Check backend is running on port 8080
2. Verify CORS configuration
3. Check API response in Network tab
```

**Google OAuth Not Working**
```
Solution:
1. Get credentials from Google Cloud Console
2. Add localhost:3000 to authorized origins
3. Add Vercel URL to authorized origins
4. Set REACT_APP_GOOGLE_CLIENT_ID
```

---

## 📊 Project Statistics

- **Lines of Code**: ~5000+ (Go backend + React frontend)
- **API Endpoints**: 40+
- **Database Collections**: 7
- **React Components**: 8+ pages
- **Go Controllers**: 8
- **Development Time**: 2 semesters
- **Team**: 2 developers

---

## 🎓 Learning Outcomes

### Blockchain Concepts
- ✅ Proof-of-Work mining
- ✅ UTXO transaction model
- ✅ Merkle tree verification
- ✅ Blockchain validation
- ✅ Cryptographic hashing

### Backend Development
- ✅ Go + Gin framework
- ✅ RESTful API design
- ✅ MongoDB database design
- ✅ JWT authentication
- ✅ Middleware implementation
- ✅ Error handling & logging

### Frontend Development
- ✅ React hooks & context
- ✅ React Router navigation
- ✅ Tailwind CSS styling
- ✅ Axios HTTP client
- ✅ Form validation
- ✅ State management

### DevOps & Deployment
- ✅ Docker containerization
- ✅ Render deployment
- ✅ Vercel deployment
- ✅ MongoDB Atlas setup
- ✅ Environment configuration
- ✅ GitHub version control

---

## 📄 License

Educational project for BSSE 7th Semester Blockchain course.

---

## 👥 Contributors

- **Developer 1**: Full-stack development
- **Developer 2**: Partnership & collaboration

---

## 📞 Support

For issues or questions:
1. Check troubleshooting section above
2. Review API documentation
3. Check backend console logs
4. Verify environment variables
5. Ensure MongoDB is configured

---

## 🔗 Useful Links

- [Go Documentation](https://golang.org/doc)
- [React Documentation](https://react.dev)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- [Tailwind CSS](https://tailwindcss.com)
- [Render Docs](https://render.com/docs)
- [Vercel Docs](https://vercel.com/docs)

---

**Last Updated**: December 8, 2025  
**Status**: ✅ All Features Complete & Production Ready  
**Next Phase**: User testing and optimization
