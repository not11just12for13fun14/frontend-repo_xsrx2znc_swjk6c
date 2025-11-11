School Canteen Cashier — Native PHP + MySQL + Tailwind CSS

Overview
A complete cashier and consignment management system for a school canteen. Built with native PHP (no frameworks), MySQL, and Tailwind CSS. Supports three roles: Cashier, Treasurer, and Supplier (Penitip).

Key Features
- Authentication with PHP sessions (Cashier, Treasurer, Supplier)
- CRUD: Products, Suppliers, Users (basic), Transactions
- Consignment rules:
  - Wet food (consigned):
    - Buyer is a teacher → 10% canteen fee
    - Buyer is student/non-teacher → 20% canteen fee
    - Remaining goes to supplier
  - Dry food (canteen-owned): 100% profit to canteen
- Auto-calculated profit and supplier shares per transaction item
- Receipt printing
- Daily recap (cashier)
- Treasurer dashboards and reports (daily/weekly/monthly), export CSV (print for PDF)
- Supplier dashboard: items, sales, earnings, payment history
- Record supplier payouts and track status
- Tailwind CSS UI with light/dark mode toggle
- Activity logs
- Seed data for demo

Quick Start
1) Create database and user
- Create a MySQL database (e.g., canteen_db)
- Import the SQL file: sql/schema.sql (includes seed data)

2) Configure environment
- Copy .env.example to .env and fill DB credentials

3) Run locally
- Serve with PHP built-in server:
  php -S localhost:8080 -t public
- Or place in your Apache/Nginx root and point DocumentRoot to public/

4) Login (seed users)
- Cashier: cashier@school.test / password: password123
- Treasurer: treasurer@school.test / password: password123
- Supplier: supplier1@vendors.test / password: password123

Folder Structure
- public/          Web root (index.php, assets)
- includes/        Core config, db, auth, middleware, helpers
- partials/        Header, sidebar, footer, alerts, topbar
- pages/           Feature pages (auth, dashboard, products, suppliers, transactions, reports, payments)
- sql/             Schema and seed data

Notes
- Uses Tailwind via CDN for simplicity
- For PDF, use your browser Print → Save as PDF on report or receipt pages
- Exports provided as CSV; open in Excel/Sheets
- Minimal JS; no external build tools needed
