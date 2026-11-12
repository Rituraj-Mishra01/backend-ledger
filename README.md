# backend-ledger
A Node.js + Express backend for managing user accounts, ledger balances, and monetary transactions. The service supports user registration/login, protected account access, transaction processing with idempotency checks, and email notifications for key events.

## Features

- User registration and login with JWT authentication
- Cookie-based token handling and logout flow
- Account creation and balance retrieval
- Ledger-based balance tracking using MongoDB
- Transaction processing with:
  - idempotency key validation
  - account status checks
  - insufficient funds protection
  - pending/completed transaction flow
- System-user flow for initial funding
- Email notifications for registration and transaction events

## Tech Stack

- Node.js
- Express.js
- MongoDB with Mongoose
- JWT for authentication
- bcryptjs for password hashing
- Nodemailer for email sending
- dotenv for environment configuration

## Project Structure

```bash
backend-ledger/
├── server.js
├── package.json
├── package-lock.json
├── .gitignore
└── src/
    ├── app.js
    ├── config/
    │   └── db.js
    ├── controllers/
    │   ├── account.controller.js
    │   ├── auth.controller.js
    │   └── transaction.controller.js
    ├── middleware/
    │   └── auth.middleware.js
    ├── models/
    │   ├── account.model.js
    │   ├── blackList.model.js
    │   ├── ledger.model.js
    │   ├── transaction.model.js
    │   └── user.model.js
    ├── routes/
    │   ├── account.routes.js
    │   ├── auth.routes.js
    │   └── transaction.routes.js
    └── services/
        └── email.service.js
