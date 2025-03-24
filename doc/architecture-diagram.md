doc/architecture-diagram.md

Privyt Architecture Overview
This document provides a high-level technical architecture diagram for Privyt, illustrating the interaction between onboarding, Privyt Wallet (main wallet), Exportable Wallet, External Wallets, and DApps.

System Components & Flow
a.	Onboarding System (Privyt Authentication & Account Creation)
Role: Simplifies user onboarding with a Web3-native account system.
Authentication: Users can create accounts using Privyt Email System (not traditional emails like Google).
Security: Utilizes multi-party computation (MPC) for private key generation, ensuring a non-custodial model.

User Experience:
No need for seed phrases.
One-click sign-up.
Seamless login across Dapps

b.	Privyt Core System (Main Wallet)
Role: Acts as the primary account creation & authentication layer.
Security: Private keys are generated and stored using multi-party computation (MPC), ensuring non-custodial security.
Interaction: Can send & receive transactions with Exportable Wallets but does NOT directly connect to external wallets for security reasons.

c.	Exportable Wallets
Role: A sub-wallet that can interact with external wallets & DApps.
Security: Exportable wallets generate private keys that users can export to MetaMask, Trust Wallet, etc.
Functionality: Can send/receive funds from both Privyt Main Wallet and External Wallets.

d.	External Wallets (MetaMask, Trust Wallet, etc.)
Role: Third-party wallets that can only interact with Exportable Wallets (not directly with the Privyt Main Wallet).
Security: Privyt does not store any external wallet data. Users must manually import/export private keys if they wish to connect.

e.	DApp Connections
Role: Exportable Wallets can connect to Web3 DApps for transactions & smart contract interactions.
Gas Fees: Supported by gasless transactions for Privyt users when applicable.

Architecture Diagram
(A diagram illustrating the architecture should be inserted here in the final document, showcasing interactions between components.)
+--------------------+            +----------------------+
|  Privyt Main Wallet | <---> |  Exportable Wallet  | <---> [DApps]
+--------------------+            +----------------------+
       |                                      |
       v                                      v
[Privyt Email System]                 [External Wallets (MetaMask, Trust)]
      (Authentication)                      (Manual Private Key Import)

Security Layers
Multi-Party Computation (MPC) → Protects Privyt Main Wallet's key generation.
Role-Based Access → Exportable Wallets have controlled permissions.
Anti-Phishing & Fraud Detection → Detects bots & unauthorized transactions.
Gas Sponsorship System → Optimized for gasless transactions to reduce costs for users.

Final Notes
This architecture ensures maximum security, easy onboarding, and seamless DApp interaction.
Privyt Wallet prioritizes non-custodial, user-controlled security while providing gasless transaction benefits.
