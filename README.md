# SkillVerse — Freelance Skill Marketplace

A full-stack Flask web application that connects freelance service providers with clients. Built with Python, Flask, PostgreSQL, and Socket.IO for real-time features.

---

## 🚀 Features

- **User Authentication** — Email/password + Google OAuth login/signup
- **Service Marketplace** — Browse, search, filter, and order freelance services
- **Real-time Chat** — Socket.IO powered messaging between buyers and sellers
- **Wallet System** — In-app wallet with recharge, payments, and transaction history
- **Booking System** — Provider availability slots + client booking flow
- **Certificate Generation** — PDF certificates for completed orders with QR verification
- **Admin Panel** — User management, service approval, analytics dashboard
- **Email Notifications** — Transactional emails for orders, bookings, and account events
- **AskVera AI** — Groq-powered AI chatbot assistant

---

## 📁 Project Structure

```
SkillVerse/
├── app.py                   # Application entry point & factory
├── config.py                # Configuration classes (Dev/Prod/Test)
├── extensions.py            # Flask extension instances
├── models.py                # SQLAlchemy database models
├── routes.py                # All route blueprints (controllers)
├── routes_chat.py           # AskVera chatbot routes
├── events.py                # Socket.IO event handlers
├── managers.py              # Business logic layer (MVC pattern)
├── data_structures.py       # Custom DS: HashMap, MaxHeap, Queue, Trie
├── payment_system.py        # Wallet & payment gateway
├── certificate_generator.py # PDF certificate generation
├── chat_manager.py          # Groq AI integration for AskVera
├── email_utils.py           # Email sending utilities
├── init_db.py               # Database initialization & seeding
├── migrate_db.py            # Schema migration scripts
├── requirements.txt         # Python dependencies
├── start.bat                # Windows quick-start script
├── .env.example             # Environment variable template
├── .gitignore               # Git ignore rules
│
├── static/                  # Static assets
│   ├── css/                 # Stylesheets
│   ├── js/                  # JavaScript files
│   ├── images/              # Static images
│   ├── fonts/               # Certificate fonts
│   ├── uploads/             # User-uploaded service images
│   ├── avatars/             # User avatar uploads
│   ├── portfolio/           # Portfolio project images
│   └── certificates/        # Generated PDF certificates
│
├── templates/               # Jinja2 HTML templates
│   ├── admin/               # Admin panel templates
│   ├── auth/                # Login & registration
│   ├── components/          # Reusable template partials
│   ├── emails/              # Email HTML templates
│   ├── errors/              # Error pages (404, 500)
│   ├── legal/               # Terms & privacy pages
│   ├── user/                # User dashboard & profile
│   └── *.html               # Main pages (index, services, etc.)
│
└── docs/                    # Documentation & diagrams
    ├── SkillVerse.final.pptx
    └── SkillVerse_ER_Diagram.png
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.10+
- PostgreSQL 14+

### Quick Start (Windows)

```bash
# 1. Clone the repository
git clone https://github.com/your-repo/skillverse.git
cd skillverse

# 2. Create virtual environment
python -m venv venv
venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Configure environment
copy .env.example .env
# Edit .env with your database credentials, API keys, etc.

# 5. Run the application
python app.py
```

Or simply run `start.bat` for automatic setup.

### Access
- **Application**: http://localhost:5000
- **Default Admin**: admin@skillverse.com / admin123

---

## 🗄️ Database

The application uses **PostgreSQL** as its primary database. Configure the connection in `.env`:

```
DATABASE_URL=postgresql://postgres:yourpassword@localhost/skillverse_pg
```

Tables are created automatically on first run via `db.create_all()` and schema migrations in `migrate_db.py`.

---

## 🛠️ Tech Stack

| Layer        | Technology                        |
|--------------|-----------------------------------|
| Backend      | Python 3, Flask                   |
| Database     | PostgreSQL, SQLAlchemy ORM        |
| Auth         | Flask-Login, Google OAuth (Authlib) |
| Real-time    | Flask-SocketIO                    |
| Email        | Flask-Mail (SMTP)                 |
| AI           | Groq API (LLaMA 3.3)             |
| Frontend     | HTML5, CSS3, JavaScript, Bootstrap |

---

## 📄 License

This project is developed for academic purposes (Semester 3 Project).
