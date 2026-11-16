# 🚗 Best Cars – Car Dealership Review Portal

A full-stack web application where customers can browse car dealerships across the United States, read customer reviews for each branch, and post their own reviews.

Built as the capstone project for the **IBM Full Stack Software Developer Professional Certificate** on Coursera.

---

## 📖 About the Project

A national car dealership with branches across the US ran a market survey. Customers said they wanted **one central place to read dealership reviews from across the country**.

This portal answers that need. It brings **transparency** to the dealership network and helps build **customer trust** by letting anyone see honest reviews, and letting registered customers share their own experience.

---

## ✨ Features

### 👤 Anonymous users
- View the **About Us** and **Contact Us** pages
- View the list of all dealerships
- **Filter dealerships by state** using a dropdown
- Open a dealership's details page and read its reviews, each shown on a Bootstrap card
- See the **sentiment** of every review (positive, neutral or negative)
- Register for an account or log in

### 🔐 Authorized users
Everything above, plus:
- A **Review** button next to each dealership
- Write a review with purchase details: purchase date, car make, car model and car year
- The new review appears at the top of the dealership's review list

### 🛠️ Admin users
- Log in to the **Django admin site**
- Add and manage **car makes, car models** and their attributes

---

## 🏗️ Architecture

```
                ┌──────────────────────────┐
                │  React front end (UI)    │
                └────────────┬─────────────┘
                             │
                ┌────────────▼─────────────┐
                │  Django app              │
                │  users, auth, car makes  │
                │  and models, API proxy   │
                └──────┬───────────┬───────┘
                       │           │
       ┌───────────────▼───┐   ┌───▼──────────────────┐
       │ Node.js + Express │   │ Sentiment analyzer   │
       │ dealers & reviews │   │ (Flask microservice) │
       └─────────┬─────────┘   └──────────────────────┘
                 │
       ┌─────────▼─────────┐
       │     MongoDB       │
       └───────────────────┘
```

| Component | Role |
|---|---|
| **Django** | User management and authentication, car make and model data (SQLite), routes requests to the other services |
| **React** | Front-end pages: Login, Register, Dealers, Dealer details, Post Review |
| **Node.js + Express** | REST API for dealerships and reviews |
| **MongoDB** | Stores dealership and review data |
| **Flask sentiment analyzer** | Analyses review text and returns its sentiment; deployed on IBM Cloud Code Engine |
| **Docker / Kubernetes** | Containerizes and deploys the application |
| **GitHub Actions** | CI workflow that lints the Python and JavaScript code |

---

## 🧰 Tech Stack

**Front end:** React, HTML, CSS, Bootstrap
**Back end:** Python, Django, Node.js, Express, Flask
**Database:** MongoDB, SQLite
**DevOps and cloud:** Docker, Kubernetes, IBM Cloud Code Engine, GitHub Actions

---

## 📂 Project Structure

```
server/
├── database/      # Node.js + Express API, MongoDB data and Docker setup
├── djangoapp/     # Django app: models, views, REST API proxies
├── djangoproj/    # Django project settings and URL routes
├── frontend/      # React app and static pages (Home, About, Contact)
├── manage.py
└── requirements.txt
```

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/CaptTauhid5832/CaptTauhid5832-Car-Dealership-Project.git
cd CaptTauhid5832-Car-Dealership-Project/server
```

### 2. Set up the Python environment
```bash
pip install virtualenv
virtualenv djangoenv
source djangoenv/bin/activate
python3 -m pip install -U -r requirements.txt
```

### 3. Prepare the database and run Django
```bash
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py runserver
```

Open **http://localhost:8000** in your browser.

### 4. Create an admin user (optional)
```bash
python3 manage.py createsuperuser
```
The admin site is at **http://localhost:8000/admin**.

---

## ✅ Project Progress

- [x] Fork and clone the project template
- [x] Run the Django app on the development server
- [x] Navigation bar with Bootstrap
- [x] About Us page
- [x] Contact Us page
- [ ] User management (login, logout, sign-up)
- [ ] Back-end services (dealers, reviews, car makes and models, sentiment analysis)
- [ ] Dynamic pages (dealers list, state filter, dealer details, post review)
- [ ] CI with GitHub Actions
- [ ] Containerize and deploy

---

## 👨‍💻 Author

**Tauhidur Rahman**
Lead Full-Stack Software Developer (Capstone)
GitHub: [@CaptTauhid5832](https://github.com/CaptTauhid5832)

---

## 📄 License

This project is licensed under the terms of the [LICENSE](LICENSE) file in this repository.
