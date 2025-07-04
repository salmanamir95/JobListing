# JobListing

# 💼 SaaS Job Board Platform MVP

A full-stack multi-tenant SaaS job board where employers can post job listings based on their subscription plan. Built with **React + Django REST Framework**, with **role-based access control**, **Stripe integration**, and a **DevSecOps-focused architecture**.

---

## 🌐 Live Demo

🚧 Coming Soon

---

## 🧱 Tech Stack

| Layer    | Technology                      |
| -------- | ------------------------------- |
| Frontend | React.js, TailwindCSS, Axios    |
| Backend  | Django, Django REST Framework   |
| Auth     | JWT / Django-AllAuth (optional) |
| DB       | PostgreSQL                      |
| Payments | Stripe API                      |
| DevOps   | Docker, GitHub Actions, Sentry  |
| Hosting  | Render / Railway / AWS          |

---

## 🔑 Features

### ✅ Core Platform Features

* Employer and job seeker registration/login
* Role-based access: `employers`, `pro_employers`, `premium_employers`, `users`, `admin`
* Employers can create job listings (limit based on plan)
* Stripe integration for recurring payments
* Auto-track listing limits and renewal dates
* Admin dashboard to manage users, jobs, and roles
* Users (job seekers) can browse and apply to jobs
* Email reminders for listing expiration and renewals

### 🛡 DevSecOps Highlights

* Dockerized backend and frontend
* CI/CD pipeline with GitHub Actions
* Bandit + ESLint for security linting
* Sentry for error monitoring
* Environment secrets management
* API secured with JWT auth

---



## 🚀 Getting Started

### 🔧 Prerequisites

* Node.js (v18+)
* Python 3.10+
* Docker + Docker Compose
* Stripe account

---

### 🔄 Setup Instructions

#### 1. Clone the Repo

```bash
git clone https://github.com/yourname/jobboard-saas.git
cd jobboard-saas
```

#### 2. Environment Variables

Create a `.env` file in the root and backend with:

```env
# Backend
DJANGO_SECRET_KEY=your-secret-key
DEBUG=True
POSTGRES_DB=jobboard
POSTGRES_USER=admin
POSTGRES_PASSWORD=password
STRIPE_SECRET_KEY=sk_test_...
FRONTEND_URL=http://localhost:3000

# Frontend
REACT_APP_API_URL=http://localhost:8000/api
REACT_APP_STRIPE_PUBLIC_KEY=pk_test_...
```

#### 3. Run with Docker

```bash
docker-compose up --build
```

---

## 🥪 Testing

```bash
# Inside backend container
python manage.py test

# Or locally
pytest
```

---

## 📄 API Overview

Base URL: `/api/`

| Endpoint                  | Method | Description                     |
| ------------------------- | ------ | ------------------------------- |
| `/auth/register/`         | POST   | Register new user               |
| `/auth/login/`            | POST   | JWT login                       |
| `/jobs/`                  | GET    | List all jobs                   |
| `/jobs/`                  | POST   | Create job (employer only)      |
| `/subscriptions/`         | GET    | View current plan + limits      |
| `/subscriptions/upgrade/` | POST   | Upgrade to pro/premium (Stripe) |

---

## 👮 Roles & Access

| Role              | Job Limit | Features                         |
| ----------------- | --------- | -------------------------------- |
| Employer          | 2         | Basic posting                    |
| Pro Employer      | 5         | More posts, scheduling           |
| Premium Employer  | 10        | Featured listings, auto-renewals |
| User (Job Seeker) | -         | Browse & apply to jobs           |
| Admin             | ∞         | Full management access           |

---

## ⚙️ CI/CD (GitHub Actions)

* Lint backend (`bandit`)
* Lint frontend (`eslint --security`)
* Run backend tests
* Build & deploy containers
* Auto-deploy on `main` branch

---

## 🔒 Security Best Practices

* CSRF, CORS, and XSS protections via Django
* Role-based DRF permissions
* HTTPS enforced on deployment
* Stripe webhooks for secure payment handling

---

## 📦 Future Improvements

* Resume uploads for job seekers
* Messaging between users/employers
* Analytics dashboard
* Multi-language support



