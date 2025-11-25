# Django Ecommerce Store 🛒

A full‑featured **Ecommerce web application** built with **Django**.  
This project demonstrates a complete online shopping system with product management, cart, checkout (via Stripe), and user authentication — ready to be used as a boilerplate for online stores or as a learning resource for Django-based e-commerce.


## Table of Contents

- [Features](#features)  
- [How It Works (Overview)](#how-it-works-overview)  
- [Tech Stack](#tech-stack)  
- [Prerequisites](#prerequisites)  
- [Installation & Setup (Local)](#installation--setup-local)  
- [Environment Variables](#environment-variables)  
- [Running the App](#running-the-app)  
- [Project Structure](#project-structure)  
- [Usage](#usage)  
- [Admin / Superuser](#admin--superuser)  
- [Future Improvements](#future-improvements)  
- [Contributing](#contributing)  
- [License](#license)  
- [Author](#author)

---

## Features

- **User Authentication**  
  - Register, log in, log out  
  - Secure user sessions  

- **Product Management**  
  - Add, edit, delete products (via the `demo` or admin panel)  
  - Product listing, product detail pages  

- **Shopping Cart**  
  - Add/remove products to/from cart  
  - Update quantities (if implemented)  
  - Persist cart across user sessions  

- **Checkout & Payment**  
  - Stripe integration (test mode via environment variables)  
  - Order creation and processing  

- **Admin Panel**  
  - Manage products, orders, users, categories, etc. via Django admin  
  - Superuser management  

- **Static & Media Files Handling**  
  - Static assets stored in `static_in_env/`  
  - Uploaded media (e.g. product images) stored in `media_root/`  

- **Project Organization & Structure**  
  - Modular Django apps (`core/`, `demo/`)  
  - Management commands (e.g. for custom admin setup)  
  - Clean separation of concerns  

> **Note:** Although default database is SQLite for easy setup, this project can be extended to use more production-grade databases (PostgreSQL, MySQL, etc.).

---

## How It Works (Overview)

1. **User visits the store** → Browses available products (listed from the database).  
2. **User adds items to the cart** → Items stored in session / database, depending on implementation.  
3. **User proceeds to checkout** → Stripe payment form is displayed, user enters payment details.  
4. **On successful payment** → Order is created and stored in the database; user receives confirmation.  
5. **Admin manages orders/products** → Via Django admin, admin can view orders, mark them as delivered, manage products, etc.  

This flow provides a minimal, yet complete, e-commerce experience — ideal as a starting point for more advanced features.

---

## Tech Stack

- **Backend:** Python 3, Django  
- **Database:** SQLite (default) — easy to start with  
- **Payment Processor:** Stripe (test mode by default)  
- **Frontend / Static:** HTML, CSS, JavaScript — minimal styling; ready for customization  

---

## Prerequisites

Before you begin, ensure you have the following installed:

- Python ≥ 3.8  
- pip (Python package installer)  
- (Optional but recommended) virtualenv or venv  

---

## Installation & Setup (Local)

```bash
# 1. Clone the repository
git clone https://github.com/muhammadtayabfarooq-dev/django-ecommerce-store.git
cd django-ecommerce-store

# 2. Create a virtual environment and activate it
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS / Linux:
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt
````

---

## Environment Variables

Create a `.env` file at the project root and set the following values (for development/testing):

```env
STRIPE_SECRET_KEY=your_stripe_test_secret_key
STRIPE_PUBLIC_KEY=your_stripe_test_public_key
DJANGO_SECRET_KEY=your_django_secret_key
DEBUG=True
```

> For production, you should set `DEBUG=False` and configure allowed hosts, static/media storage, SSL, etc.

---

## Running the App

```bash
# Run database migrations
python manage.py migrate

# (Optional) Create a superuser
python manage.py createsuperuser

# Start the development server
python manage.py runserver
```

Then navigate to `http://localhost:8000` in your browser to view the store.

---

## Project Structure

```
django-ecommerce-store/
│
├── bin/                    # Management CLI tools
│   ├── cli.py
│   ├── commands.py
│   └── shared.py
│
├── core/                   # Main app: business logic, models, views
│   ├── management/commands/   # Custom Django management commands
│   │   ├── makesuper.py
│   │   └── rename.py
│   ├── migrations/
│   ├── templatetags/
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── demo/                   # Example/demo app or placeholder for future features
│   ├── __init__.py
│   ├── azure.py
│   ├── urls.py
│   └── wsgi.py
│
├── media_root/             # Uploaded media (e.g. product images)
├── static_in_env/          # Static files (CSS, JS, images)
├── templates/              # HTML templates
├── .gitignore
├── db.sqlite3              # Default SQLite database (auto-generated)
├── manage.py
└── requirements.txt        # Python dependencies
```

---

## Usage

* Visit the home page → see product listings.
* As a regular user → register / login, browse products, add to cart, checkout.
* As an admin → log in to the Django admin panel (`/admin/`), manage products, view orders, manage users, etc.
* To add sample products → you can either use the admin panel or extend/demo app to import products in bulk.

---

## Future Improvements (Planned / Suggested)

* Use a production-ready database (PostgreSQL, MySQL) instead of SQLite
* Add product categories, tags, search and filtering functionality
* Improve frontend (UI/UX, responsive design, styling)
* Add order status tracking (pending → shipped → delivered)
* Implement email notifications (order confirmation, shipping updates)
* Add user profiles, order history, wishlist/favorites
* Add product reviews & ratings
* Add support for variable products (size, color, etc.)
* Deploy to a cloud server — configure static/media storage (e.g. AWS S3), HTTPS, environment-based settings
* Write tests and add CI/CD pipeline

---

## Contributing

Contributions are welcome! If you find a bug, want to add a feature or improve documentation, feel free to open an issue or submit a pull request.

Suggested workflow:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/my-feature`)
3. Make your changes (code / tests / docs)
4. Commit and push (`git commit -m "Add my feature"`, `git push`)
5. Open a PR describing your changes

Before contributing: make sure your code follows PEP 8 style, run tests (if any), and update documentation accordingly.

---

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

## Author

**Muhammad Tayab Farooq** — [muhammadtayabfarooq-dev on GitHub](https://github.com/muhammadtayabfarooq-dev)

Thanks for checking out this project! 🙌
