# SecureChat

A privacy-first messaging platform built with Next.js and TypeScript. This project focuses on secure account flows, encrypted messaging, UI polish, and strong privacy controls.

## Features

- Registration and login with secure password hashing using bcrypt.
- End-to-end-encrypted message payloads using `tweetnacl` before transmission.
- Message and conversation access checks that reject unauthorized access.
- User privacy settings such as message preview hiding, read receipts, and online visibility controls.
- Session tracking, account deletion-friendly model, and reporting/block flows.

## Security assumptions

- HTTPS/TLS must be enforced at the deployment layer.
- Keys live in the browser or client environment and are never stored in plaintext on the server.
- The project uses a local SQLite database for demo purposes and is not meant for a production multi-region deployment without further hardening.
- This app demonstrates the architecture patterns for encrypted messaging; additional production controls such as WebSockets, user-key recovery, and device enrollment are still recommended before real-world deployment.

## Local setup

1. Install dependencies:
   npm install
2. Copy `.env.example` to `.env.local` and add a strong `JWT_SECRET`.
3. Start the development server:
   npm run dev
4. Open http://localhost:3000

## Testing

npm run build
npx vitest run

## Deployment

- Configure environment variables in your hosting platform.
- Use TLS termination and secure session cookies or bearer tokens.
- Store database files in a secure and backed-up volume.
- Enforce access controls before exposing routes to the public internet.
