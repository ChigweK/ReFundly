# System Architecture for ReFundly

ReFundly is a peer-to-peer airtime exchange platform that helps users resell mistakenly purchased airtime safely. The system connects sellers and buyers, handles verification, and releases payment only when both sides confirm the transfer.

## Architecture Overview

![1000113505](https://github.com/user-attachments/assets/6633829e-602a-4bc5-bf60-61b0fb5af0cb)

### 1. Frontend
**Technology:** Flutter (mobile) or React (web)  
**Responsibilities:**
- User registration & login
- Listing airtime for sale
- Displaying marketplace offers
- Processing payments and wallet actions

### 2. Backend
**Technology:** Node.js + Express  
**Responsibilities:**
- Handle authentication & user sessions
- Verify airtime existence via telecom API
- Match buyers and sellers
- Securely hold funds before release (escrow logic)
- Manage ratings and user trust levels

### 3. Database
**Recommended:** PostgreSQL (structured data)  
**Tables:**
- `users` (profile, verification status)
- `airtime_listings` (amount, network, seller)
- `transactions` (buyer, seller, status)
- `wallets` (balance, withdrawals)
- `ratings` (user trust score)

### 4. Payment Layer
**Integration:** Paystack/Flutterwave  
Used for:
- Secure payments
- Wallet funding and withdrawals
- Escrow-style transaction holding

### 5. Telecom Verification Layer
**Integration:** Telecom Network API (MTN, Airtel, Glo, 9mobile)
Used to validate airtime before listing to prevent fraud.

## System Flow

1. User reports airtime amount and network.
2. Backend verifies airtime existence.
3. Airtime is listed for sale in the marketplace.
4. Buyer selects listing and pays through payment gateway.
5. Seller transfers airtime to buyer.
6. Once confirmed, system releases money to seller wallet.
7. Seller withdraws wallet funds to bank.
   
## Why This Is Feasible
People already sell airtime informally. ReFundly simply organizes, verifies, and secures the process. Using Flutter allows quick mobile deployment and PostgreSQL ensures safe structured data storage. Wallet + escrow prevents fraud.
