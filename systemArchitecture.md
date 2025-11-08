# System Architecture for ReFundly

ReFundly is a peer-to-peer airtime exchange platform that helps users resell mistakenly purchased airtime safely. The system connects sellers and buyers, handles verification, and releases payment only when both sides confirm the transfer.

## Architecture Overview

- **Frontend (Mobile App):** Flutter
- **Backend API:** Node.js with Express
- **Database:** PostgreSQL
- **Payments:** Paystack or Flutterwave
- **Telecom Verification:** Network Verification API

## System Flow

1. User reports airtime amount and network.
2. Backend verifies airtime existence.
3. Airtime is listed for sale in the marketplace.
4. Buyer selects listing and pays through payment gateway.
5. Seller transfers airtime to buyer.
6. Once confirmed, system releases money to seller wallet.
7. Seller withdraws wallet funds to bank.

## Architecture Diagram

![1000113505](https://github.com/user-attachments/assets/6633829e-602a-4bc5-bf60-61b0fb5af0cb)


## Why This Is Feasible
People already sell airtime informally. ReFundly simply organizes, verifies, and secures the process. Using Flutter allows quick mobile deployment and PostgreSQL ensures safe structured data storage. Wallet + escrow prevents fraud.
