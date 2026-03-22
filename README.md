<p align="center">
  <img src="https://img.shields.io/badge/Flask-3.0-000000?style=for-the-badge&logo=flask&logoColor=white" alt="Flask"/>
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/PostgreSQL-14+-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Socket.IO-5.5-010101?style=for-the-badge&logo=socketdotio&logoColor=white" alt="Socket.IO"/>
  <img src="https://img.shields.io/badge/License-Academic-orange?style=for-the-badge" alt="License"/>
</p>

<h1 align="center">🌐 SkillVerse</h1>
<h3 align="center">A Full-Stack Freelance Skill Marketplace</h3>

<p align="center">
  <i>Connecting talented service providers with clients — powered by real-time communication, AI assistance, and secure payments.</i>
</p>

<p align="center">
  <a href="#-features">Features</a> •
  <a href="#-tech-stack">Tech Stack</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-getting-started">Getting Started</a> •
  <a href="#-database-schema">Database</a> •
  <a href="#-custom-data-structures">Data Structures</a> •
  <a href="#-screenshots">Screenshots</a> •
  <a href="#-contributing">Contributing</a>
</p>

---

## ✨ Features

### Core Marketplace
| Feature | Description |
|---------|-------------|
| 🔐 **Authentication** | Email/password registration + Google OAuth 2.0 single sign-on |
| 🛒 **Service Marketplace** | Browse, search, filter, and order freelance services across multiple categories |
| 💬 **Real-time Chat** | Socket.IO powered instant messaging between buyers and sellers per order |
| 💰 **Wallet & Payments** | In-app wallet with recharge, payments, transaction history, and Stripe gateway integration |
| 📅 **Booking System** | Provider availability slots with client booking flow and status management |
| 📜 **Certificate Generation** | Premium PDF certificates with QR verification codes for completed orders |
| 🛡️ **Admin Panel** | Full user management, service approval workflow, analytics dashboard, and contact messages |
| 📧 **Email Notifications** | Transactional emails via Gmail SMTP for orders, bookings, password resets, and account events |
| 🤖 **AskVera AI** | Groq-powered (LLaMA 3.3 70B) intelligent chatbot assistant for platform guidance |
| ⭐ **Reviews & Ratings** | Star-based rating system with written reviews for completed services |
| 🖼️ **Portfolio Showcase** | Service providers can showcase past projects with images and descriptions |
| ❤️ **Favorites** | Users can bookmark services for quick access later |
| 🔔 **Notifications** | In-app notification system for order updates, messages, and account events |
| 📞 **Contact Page** | Public contact form with messages stored in database for admin review |

### Technical Highlights
- 🏗️ **Application Factory Pattern** — Clean Flask app initialization with environment-specific configs
- 📊 **Custom Data Structures** — Hand-built HashMap, MaxHeap, Queue & Trie (no external libraries)
- 🔄 **Schema Migrations** — Automatic database migration system for seamless upgrades
- 🌐 **Google OAuth** — Secure third-party authentication via Authlib
- 🕐 **IST Timezone Support** — All timestamps display in Indian Standard Time
- 🎨 **Responsive UI** — Mobile-first design with Bootstrap 5 and custom CSS

---

## 🛠️ Tech Stack

<table>
  <tr>
    <td align="center"><b>Layer</b></td>
    <td align="center"><b>Technology</b></td>
    <td align="center"><b>Purpose</b></td>
  </tr>
  <tr>
    <td>🐍 Backend</td>
    <td>Python 3.10+, Flask 3.0</td>
    <td>Application server, routing, business logic</td>
  </tr>
  <tr>
    <td>🗄️ Database</td>
    <td>PostgreSQL 14+, SQLAlchemy ORM</td>
    <td>Persistent data storage with relational modeling</td>
  </tr>
  <tr>
    <td>🔑 Auth</td>
    <td>Flask-Login, Authlib (Google OAuth)</td>
    <td>Session management, social login</td>
  </tr>
  <tr>
    <td>⚡ Real-time</td>
    <td>Flask-SocketIO, python-socketio</td>
    <td>WebSocket-based instant messaging</td>
  </tr>
  <tr>
    <td>📧 Email</td>
    <td>Flask-Mail (Gmail SMTP)</td>
    <td>Transactional email delivery</td>
  </tr>
  <tr>
    <td>🤖 AI</td>
    <td>Groq API (LLaMA 3.3 70B)</td>
    <td>Intelligent chatbot assistant (AskVera)</td>
  </tr>
  <tr>
    <td>💳 Payments</td>
    <td>Stripe API + In-app Wallet</td>
    <td>Secure payment processing & wallet management</td>
  </tr>
  <tr>
    <td>📜 Certificates</td>
    <td>Pillow, qrcode, matplotlib</td>
    <td>PDF certificate generation with QR verification</td>
  </tr>
  <tr>
    <td>🎨 Frontend</td>
    <td>HTML5, CSS3, JavaScript, Bootstrap 5</td>
    <td>Responsive user interface</td>
  </tr>
  <tr>
    <td>🔐 Security</td>
    <td>Werkzeug, bcrypt, PyJWT</td>
    <td>Password hashing, JWT tokens, CSRF protection</td>
  </tr>
</table>

---

## 🏗️ Architecture

### Project Structure

```
SkillVerse/
│
├── 📄 app.py                    # Application entry point & factory pattern
├── 📄 config.py                 # Configuration classes (Dev/Prod/Test)
├── 📄 extensions.py             # Flask extension instances (Login, OAuth, SocketIO, Mail)
├── 📄 models.py                 # SQLAlchemy ORM models (13 database tables)
├── 📄 routes.py                 # Main route blueprints (7 blueprints)
├── 📄 routes_chat.py            # AskVera AI chatbot routes
├── 📄 events.py                 # Socket.IO WebSocket event handlers
├── 📄 managers.py               # Business logic layer (MVC pattern)
├── 📄 data_structures.py        # Custom DS: HashMap, MaxHeap, Queue, Trie
├── 📄 payment_system.py         # Wallet, PaymentGateway & InvoiceGenerator
├── 📄 certificate_generator.py  # PDF certificate generation with QR codes
├── 📄 chat_manager.py           # Groq AI integration for AskVera
├── 📄 email_utils.py            # Email sending utilities (SMTP)
├── 📄 init_db.py                # Database initialization & seeding
├── 📄 migrate_db.py             # Schema migration scripts
├── 📄 requirements.txt          # Python dependencies
├── 📄 start.bat                 # Windows quick-start script
├── 📄 .env.example              # Environment variable template
│
├── 📁 static/                   # Static assets
│   ├── css/                     # Stylesheets
│   ├── js/                      # Client-side JavaScript
│   ├── images/                  # Static images
│   ├── fonts/                   # Certificate fonts (Playfair, Montserrat, etc.)
│   ├── uploads/                 # User-uploaded service images
│   ├── avatars/                 # User avatar uploads
│   ├── portfolio/               # Portfolio project images
│   └── certificates/            # Generated PDF certificates
│
├── 📁 templates/                # Jinja2 HTML templates
│   ├── admin/                   # Admin panel (user mgmt, approvals, analytics)
│   ├── auth/                    # Login, registration, password reset
│   ├── components/              # Reusable template partials (navbar, footer, etc.)
│   ├── emails/                  # HTML email templates
│   ├── errors/                  # Error pages (404, 500)
│   ├── legal/                   # Terms of Service & Privacy Policy
│   ├── user/                    # User dashboard, profile, wallet, orders
│   └── *.html                   # Main pages (index, services, about, contact)
│
└── 📁 docs/                     # Documentation
    ├── SkillVerse.final.pptx    # Project presentation
    └── SkillVerse_ER_Diagram.png # Entity-Relationship diagram
```

### Application Blueprints

| Blueprint | URL Prefix | Responsibility |
|-----------|------------|----------------|
| `main_bp` | `/` | Home, about, contact, search |
| `auth_bp` | `/auth` | Login, register, OAuth, password reset |
| `service_bp` | `/service` | CRUD operations, search, filtering |
| `user_bp` | `/user` | Dashboard, profile, wallet, orders |
| `admin_bp` | `/admin` | Admin panel, user management, analytics |
| `api_bp` | `/api` | REST API endpoints |
| `availability_bp` | `/availability` | Provider slots & client bookings |
| `chat_bp` | `/chat` | AskVera AI chatbot interface |

---

## 🗄️ Database Schema

The application uses **PostgreSQL** with **13 interrelated tables** designed following proper normalization principles.

### Entity-Relationship Diagram

<p align="center">
  <img src="docs/SkillVerse_ER_Diagram.png" alt="SkillVerse ER Diagram" width="800"/>
</p>

### Key Models

| Model | Table | Description |
|-------|-------|-------------|
| `User` | `users` | User accounts (clients, providers, admins) with wallet balance |
| `Service` | `services` | Freelance services with approval workflow |
| `Category` | `categories` | Service categories with icons and colors |
| `Order` | `orders` | Service orders with status management (pending → in_progress → completed) |
| `Review` | `reviews` | Star ratings (1–5) and written reviews |
| `Message` | `messages` | Chat messages linked to orders |
| `Transaction` | `transactions` | Wallet transaction history (debits, credits, recharges) |
| `Favorite` | `favorites` | User-service bookmarks (unique constraint) |
| `Notification` | `notifications` | In-app notification system |
| `AvailabilitySlot` | `availability_slots` | Provider time slot management |
| `Booking` | `bookings` | Client booking records |
| `Certificate` | `certificates` | Completion certificates with unique IDs |
| `ContactMessage` | `contact_messages` | Contact form submissions |

### Key Relationships
```
User ──┬── 1:N ──→ Service        (provider creates services)
       ├── 1:N ──→ Order          (buyer places / seller receives orders)
       ├── 1:N ──→ Review         (user writes reviews)
       ├── 1:N ──→ Favorite       (user bookmarks services)
       ├── 1:N ──→ Notification   (user receives notifications)
       ├── 1:N ──→ Transaction    (user's wallet history)
       ├── 1:N ──→ AvailabilitySlot (provider sets availability)
       └── 1:N ──→ Booking        (client books slots)

Service ──┬── N:1 ──→ Category    (service belongs to category)
          ├── 1:N ──→ Review      (service receives reviews)
          └── 1:N ──→ Order       (service is ordered)

Order ──┬── 1:1 ──→ Certificate   (completed order gets certificate)
        └── 1:N ──→ Message       (order has chat messages)
```

---

## 🧬 Custom Data Structures

All data structures are **built entirely from scratch** — no external libraries used for core logic.

<table>
  <tr>
    <td align="center"><b>Data Structure</b></td>
    <td align="center"><b>Implementation</b></td>
    <td align="center"><b>Use Case in SkillVerse</b></td>
    <td align="center"><b>Time Complexity</b></td>
  </tr>
  <tr>
    <td>🔗 <b>HashMap</b></td>
    <td>Hash table with separate chaining, dynamic resizing at 0.75 load factor</td>
    <td>Fast O(1) lookups for caching and session data</td>
    <td>Avg: O(1), Worst: O(n)</td>
  </tr>
  <tr>
    <td>📊 <b>MaxHeap</b></td>
    <td>Binary max-heap using a flat array with heapify-up/down</td>
    <td>Efficient top-N service selection (highest rated)</td>
    <td>Insert/Extract: O(log n)</td>
  </tr>
  <tr>
    <td>📬 <b>Queue</b></td>
    <td>Singly linked-list based FIFO queue</td>
    <td>Order processing queue management</td>
    <td>Enqueue/Dequeue: O(1)</td>
  </tr>
  <tr>
    <td>🔤 <b>Trie</b></td>
    <td>Prefix tree with case-insensitive search and frequency-based ranking</td>
    <td>Real-time autocomplete search suggestions</td>
    <td>Search: O(L), Suggest: O(L+K)</td>
  </tr>
</table>

---

## 🚀 Getting Started

### Prerequisites

| Requirement | Version | Download |
|-------------|---------|----------|
| Python | 3.10 or higher | [python.org](https://www.python.org/downloads/) |
| PostgreSQL | 14 or higher | [postgresql.org](https://www.postgresql.org/download/) |
| Git | Latest | [git-scm.com](https://git-scm.com/downloads) |

### Installation

#### Option 1: Quick Start (Windows)

```bash
# Clone the repository
git clone https://github.com/Mayur-Purohit/SkillVerse.git
cd SkillVerse

# Run the auto-setup script
start.bat
```

The script will automatically install dependencies, set up the environment, initialize the database, and start the server.

#### Option 2: Manual Setup

```bash
# 1. Clone the repository
git clone https://github.com/Mayur-Purohit/SkillVerse.git
cd SkillVerse

# 2. Create and activate virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
# source venv/bin/activate   # macOS/Linux

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment variables
copy .env.example .env       # Windows
# cp .env.example .env       # macOS/Linux
```

### Configuration

Edit the `.env` file with your credentials:

```env
# ─── Database ────────────────────────────────────────────────
DATABASE_URL=postgresql://postgres:yourpassword@localhost/skillverse_pg

# ─── Flask ───────────────────────────────────────────────────
SECRET_KEY=your-secure-secret-key
FLASK_ENV=development

# ─── Google OAuth (optional) ─────────────────────────────────
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

# ─── Email (Gmail SMTP) ─────────────────────────────────────
MAIL_USERNAME=your-email@gmail.com
MAIL_PASSWORD=your-app-password

# ─── AskVera AI (optional) ──────────────────────────────────
ENABLE_ASKVERA=True
GROQ_API_KEY=your-groq-api-key
```

### Database Setup

```bash
# Create the PostgreSQL database
psql -U postgres
CREATE DATABASE skillverse_pg;
\q

# Tables are created automatically on first run
python app.py
```

### Running the Application

```bash
python app.py
```

The server starts at **http://localhost:5000**

### Default Credentials

| Role | Email | Password |
|------|-------|----------|
| 🛡️ Admin | `admin@skillverse.com` | `admin123` |

> ⚠️ **Important:** Change the default admin password immediately after first login in a production environment.

---

## 🔧 Environment Variables Reference

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `DATABASE_URL` | ✅ | — | PostgreSQL connection URI |
| `SECRET_KEY` | ✅ | `dev-secret-key...` | Flask secret key for sessions/CSRF |
| `FLASK_ENV` | ❌ | `development` | Environment mode |
| `GOOGLE_CLIENT_ID` | ❌ | — | Google OAuth client ID |
| `GOOGLE_CLIENT_SECRET` | ❌ | — | Google OAuth client secret |
| `MAIL_USERNAME` | ❌ | — | Gmail address for sending emails |
| `MAIL_PASSWORD` | ❌ | — | Gmail app password |
| `ADMIN_EMAIL` | ❌ | `admin@skillverse.com` | Default admin email |
| `ADMIN_PASSWORD` | ❌ | `admin123` | Default admin password |
| `ENABLE_ASKVERA` | ❌ | `False` | Enable/disable AI chatbot |
| `GROQ_API_KEY` | ❌ | — | Groq API key for AskVera |

---

## 📄 API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET/POST` | `/auth/login` | User login |
| `GET/POST` | `/auth/register` | User registration |
| `GET` | `/auth/google/login` | Google OAuth login initiation |
| `GET` | `/auth/logout` | User logout |
| `POST` | `/auth/forgot-password` | Password reset request |

### Services
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/service/` | Browse all services |
| `GET` | `/service/<id>` | View service details |
| `POST` | `/service/create` | Create new service |
| `POST` | `/service/<id>/edit` | Update service |
| `POST` | `/service/<id>/review` | Submit a review |

### User Dashboard
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/user/dashboard` | User dashboard |
| `GET` | `/user/profile` | View/edit profile |
| `GET` | `/user/wallet` | Wallet management |
| `GET` | `/user/orders` | Order history |

### Admin Panel
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/admin/dashboard` | Admin analytics |
| `GET` | `/admin/users` | User management |
| `GET` | `/admin/services` | Service approval workflow |
| `GET` | `/admin/transactions` | Transaction oversight |

---

## 🧪 OOP & DBMS Concepts Demonstrated

This project was built as an academic exercise demonstrating the following concepts:

### Object-Oriented Programming (OOP)
- **Inheritance** — All models inherit from `db.Model`; config classes inherit from `Config`
- **Encapsulation** — Password hashing, private methods (`__get_user`, `__save_balance`)
- **Abstraction** — Clean interfaces hiding complex database operations
- **Polymorphism** — Different user types (client/provider/admin) with shared interfaces
- **Factory Pattern** — Application factory (`create_app()`) for flexible initialization
- **Composition** — `WalletManager` HAS-A `PaymentGateway`
- **Custom Exceptions** — `InsufficientBalanceException`, `InvalidCardException`, etc.

### Database Management System (DBMS)
- **Primary Keys** — Auto-increment integer IDs on all tables
- **Foreign Keys** — Referential integrity across 13 tables
- **Indexes** — Query optimization on frequently searched columns
- **Unique Constraints** — Preventing duplicate usernames, emails, and duplicate favorites
- **Composite Indexes** — `(service_id, user_id)` on reviews for faster lookups
- **Cascading Deletes** — Automatic cleanup of related records
- **One-to-Many** — User → Services, Service → Reviews, Order → Messages
- **Many-to-Many** — Users ↔ Services (via Favorites association table)

---

## 🗂️ Project Status

- [x] User authentication (email + Google OAuth)
- [x] Service marketplace with categories
- [x] Real-time chat system
- [x] Wallet & payment system
- [x] Booking & availability management
- [x] Certificate generation with QR codes
- [x] Admin panel with analytics
- [x] Email notification system
- [x] AskVera AI chatbot
- [x] Portfolio showcase
- [x] Review & rating system
- [x] Contact form

---

## 👥 Authors

**Mayur Purohit** — Full-Stack Development & Architecture

---

## 📄 License

This project was developed for academic purposes as a **Semester 3 Project**. It demonstrates applied knowledge of Python, Flask, PostgreSQL, Object-Oriented Programming, Data Structures, and Database Management Systems.

---

<p align="center">
  <b>Built with ❤️ using Flask & PostgreSQL</b>
  <br/>
  <sub>⭐ Star this repository if you found it helpful!</sub>
</p>
