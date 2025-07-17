# OAuth-JWT-Server
This is a modular and secure authentication server built with Flask, PostgreSQL, and JWT
# 🔐 Flask JWT OAuth2 Auth Server with RBAC

A secure, modular authentication server built with **Flask**, **PostgreSQL**, and **JWT**, implementing OAuth2 Password Grant and Role-Based Access Control (RBAC).

---

## 📦 Features

- ✅ User Registration & Login
- ✅ Secure Password Hashing (bcrypt)
- ✅ OAuth2 Password Grant Flow
- ✅ JWT Access Tokens
- ✅ Role-Based Access Control (RBAC)
- ✅ Protected Routes with Role Guards
- ✅ PostgreSQL + SQLAlchemy + Flask-Migrate
- ✅ Environment Configuration with `.env`

---

## 🛠 Tech Stack

| Layer         | Tech                                |
|--------------|-------------------------------------|
| Language      | Python 3.10+                        |
| Framework     | Flask                               |
| ORM           | SQLAlchemy                          |
| Auth          | JWT (Flask-JWT-Extended), OAuth2    |
| DB            | PostgreSQL                          |
| Migration     | Flask-Migrate                       |
| Hashing       | bcrypt                              |
| Config        | python-dotenv                       |

---

## 🗂 Project Structure

flask-auth-server/
├── app/
│ ├── config.py
│ ├── extensions.py
│ ├── models.py
│ ├── routes/
│ │ ├── auth.py
│ │ ├── user.py
│ ├── utils/
│ │ ├── security.py
│ └── init.py
├── migrations/
├── .env
├── manage.py
├── requirements.txt
└── README.md

yaml
Copy
Edit

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/flask-auth-server.git
cd flask-auth-server
2. Create a Virtual Environment
bash
Copy
Edit
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
3. Install Dependencies
bash
Copy
Edit
pip install -r requirements.txt
4. Create .env File
env
Copy
Edit
DATABASE_URL=postgresql://postgres:password@localhost:5432/auth_db
SECRET_KEY=your_flask_secret_key
JWT_SECRET_KEY=your_jwt_secret_key
5. Initialize Database
Make sure PostgreSQL is running and auth_db is created.

bash
Copy
Edit
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
6. Run the App
bash
Copy
Edit
python manage.py
App will start at: http://127.0.0.1:5000

🔑 API Endpoints
🔐 Auth
Method	Endpoint	Description
POST	/auth/register	Register new user
POST	/auth/login	Login and get JWT token

👤 User & Roles
Method	Endpoint	Description
GET	/user/profile	Get user profile (JWT required)
POST	/user/add-role	Assign a role to a user
GET	/user/admin-only	Admin-protected route (RBAC)

🧪 Example JWT Payload
json
Copy
Edit
{
  "sub": 1,
  "iat": 1622650000,
  "exp": 1622736400,
  "roles": ["admin"]
}
👮 Role-Based Access Control
Use the @role_required(["admin"]) decorator to protect routes based on user roles.

