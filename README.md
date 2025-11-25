# Django Ecommerce Store

A full-featured Ecommerce web application built with **Django**. This project demonstrates a complete online shopping system with product management, cart, checkout, and user authentication.

---

## **Features**

- **User Authentication**
  - Register, login, logout
- **Product Management**
  - Manage products via the demo app
- **Shopping Cart**
  - Add/remove products (if implemented)
- **Checkout**
  - Stripe integration using environment variables
- **Admin Panel**
  - Manage core models via Django admin

---

## **Tech Stack**

- **Backend:** Python 3, Django
- **Database:** SQLite (default)
- **Payment:** Stripe (test keys via environment variables)

---

## **Installation**

1. Clone the repository:

```bash
git clone https://github.com/muhammadtayabfarooq-dev/django-ecommerce-store.git
cd django-ecommerce-store
````

2. Create a virtual environment and activate it:

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Set up environment variables:

Create a `.env` file in the project root:

```env
STRIPE_SECRET_KEY=your_stripe_test_secret_key
STRIPE_PUBLIC_KEY=your_stripe_test_public_key
DJANGO_SECRET_KEY=your_django_secret_key
DEBUG=True
```

5. Apply migrations:

```bash
python manage.py migrate
```

6. Create a superuser:

```bash
python manage.py createsuperuser
```

7. Run the server:

```bash
python manage.py runserver
```

---

## **Project Structure**

```
django-ecommerce-store/
│
├── bin/
│   ├── cli.py
│   ├── commands.py
│   └── shared.py
│
├── core/
│   ├── management/
│   │   └── commands/
│   │       ├── makesuper.py
│   │       └── rename.py
│   ├── migrations/
│   ├── templatetags/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── demo/
│   ├── __init__.py
│   ├── azure.py
│   ├── urls.py
│   └── wsgi.py
│
├── media_root/
├── static_in_env/
├── templates/
├── .gitignore
├── db.sqlite3
├── manage.py
└── requirements.txt
```

---

## **Author / Maintainer**

Muhammad Tayab Farooq
GitHub: [muhammadtayabfarooq-dev](https://github.com/muhammadtayabfarooq-dev)

---

## **License**

MIT License. See [LICENSE](LICENSE) for details.
