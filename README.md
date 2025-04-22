# 🍋 Little Lemon Restaurant – Back-End API

This is a project to build a working API for the **Little Lemon** restaurant — including database integration and booking features.

---

## 🚀 What This Project Does

- Connects the app to a MySQL database  
- Sets up an API for managing restaurant bookings  
- Lets users register, log in, and manage bookings  

---

## 🌐 Project URL (Local)

You can run the project locally at:  
**`http://127.0.0.1:8000/`**

---

## 🛠️ Getting Started

### 1. Clone the Project

```bash
git clone https://github.com/MarinaSaitgareeva/META-Back-End-Capstone-Little-Lemon
cd META-Back-End-Capstone-Little-Lemon
```

### 2. Set Up a Virtual Environment

Make sure you have Python 3.11+ installed. Then run:

```bash
python3 -m venv venv
source venv/bin/activate
```

To deactivate later:

```bash
deactivate
```

---

### 3. Install Python Packages

Once you're inside the virtual environment:

```bash
pip install -r requirements.txt
```

---

### 4. Set Up the MySQL Database

Make sure MySQL is installed and running. Then update your `DATABASES` section in `littlelemon/settings.py` with your own username and password:

```python
DATABASES = {
  "default": {
    ...
    "USER": "your_mysql_username",
    "PASSWORD": "your_mysql_password",
    ...
  }
}
```

Then run:

```bash
python3 manage.py makemigrations
python3 manage.py migrate
```

---

### 5. Start the Server

```bash
python3 manage.py runserver
```

Visit: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 🧪 Running Tests

Run the following to make sure everything is working:

```bash
python3 manage.py test
```

You’ll find login credentials for testing in the `notes.txt` file.

---

## 🧩 API Overview

To use the API, you'll need to log in and get a token.

**Login Endpoint:**

```http
POST /auth/token/login/
```

Use the token in all requests:

```bash
curl -H "Authorization: Bearer <your_token_here>"
```

---

## 🔐 Main API Endpoints

### 👤 User Authentication

| Endpoint               | What It Does                        | Method |
|------------------------|--------------------------------------|--------|
| /auth/users            | Register a new user                 | POST   |
| /auth/users/me/        | View or update your account         | GET/PUT/PATCH/DELETE |
| /auth/token/login/     | Login and get token                 | POST   |
| /auth/token/logout/    | Log out                             | POST   |

---

### 📋 Menu Items (Manager Only)

| Endpoint                      | What It Does               | Method |
|-------------------------------|-----------------------------|--------|
| /restaurant/menu-items        | View or create items       | GET/POST |
| /restaurant/menu-items/{id}   | View, update, or delete    | GET/PUT/PATCH/DELETE |

---

### 📅 Bookings

| Endpoint                        | What It Does               | Method |
|---------------------------------|-----------------------------|--------|
| /restaurant/bookings            | View or make a booking     | GET/POST |
| /restaurant/bookings/{id}       | View, update, or delete    | GET/PUT/PATCH/DELETE |

---

### 🏠 Home Page

Static page available at:  
**`http://127.0.0.1:8000/restaurant/home/`**

---

## 🧑‍💻 Author

Made by **Norman Putra**.
