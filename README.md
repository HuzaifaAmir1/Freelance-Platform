# Freelance Platform

A Django-based freelance platform backend with REST API support, JWT authentication, real-time messaging, notifications, payment integration, and modular app architecture.

## Project Overview

This project is built with Django and Django REST Framework to support a freelance marketplace. It includes account management, client and seller flows, job postings, proposals, courses, payments, disputes, notifications, and messaging.

## Key Features

- Custom user model in `account`
- JWT authentication with `rest_framework_simplejwt`
- API documentation support using `drf_yasg`
- CORS support for frontend integration
- Stripe payment integration
- Real-time messaging support with Django Channels
- Email support via SMTP
- Modular application structure for client, seller, jobs, proposals, courses, payments, disputes, and notifications

## Core Applications

- `account` - authentication, user profiles, custom user model
- `Client` - client-specific functionality
- `Seller` - seller-specific functionality
- `project` - project management and listings
- `jobpost` - job posting and search
- `JobProposal` - proposals and bidding
- `Payment` - payment processing and Stripe integration
- `Course` - course management
- `message` - real-time messaging
- `notifications` - notification delivery
- `dispute` - dispute management
- `social_auth` - social authentication flows

## Requirements

This project depends on a Django environment and several third-party packages. The main dependencies include:

- Python 3.8+
- Django 4.1.x
- djangorestframework
- drf_yasg
- djangorestframework-simplejwt
- django-cors-headers
- django-countries
- channels
- python-decouple
- stripe

> A project-specific requirements file is not included here, so install dependencies manually or generate one from the environment.

## Setup

1. Clone the repository.
2. Create and activate a virtual environment.
3. Install required packages.
4. Create a `.env` file at the project root and define environment variables.

### Suggested `.env` variables

```env
ENGINE=django.db.backends.postgresql
NAME=your_db_name
USER=your_db_user
PASSWORD=your_db_password
HOST=your_db_host
PORT=your_db_port
STRIPE_API_KEY=your_stripe_api_key
```

Additionally, you should set a secure `SECRET_KEY` and adjust `DEBUG` for non-production environments.

## Running the Project

From the project root:

```bash
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Access the development server at `http://127.0.0.1:8000/`.

## Important Configuration Notes

- Django settings are loaded from `djangoauth/settings.py`.
- A custom user model is defined in `account`.
- JWT authentication is enabled via `rest_framework_simplejwt`
- Channel layers are configured for in-memory use in development.
- Static files are served under `STATIC_URL = 'static/'` and media uploads are stored in `uploads/`.
- Email backend uses SMTP and should be configured with secure credentials.

## Recommended Enhancements

- Add a `requirements.txt` or `Pipfile` for reproducible dependency installation.
- Move sensitive keys and passwords to environment variables only.
- Configure production-ready channel layers and static/media storage.
- Add API documentation routes for Swagger/OpenAPI if not already exposed.

## Project Structure

The repository is organized into Django apps and a project module:

- `account/`
- `Client/`
- `Seller/`
- `social_auth/`
- `project/`
- `jobpost/`
- `JobProposal/`
- `Payment/`
- `Course/`
- `notifications/`
- `message/`
- `dispute/`
- `djangoauth/`

## License

No license is included in the repository. Add a `LICENSE` file if you want to specify usage terms.
