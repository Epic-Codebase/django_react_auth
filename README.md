# 🚀 django-react-auth

A sample project demonstrating Django DRF authentication using JWT and integrating it with a React frontend. This repository showcases best practices for handling authentication, including token-based authentication, API connections with Axios interceptors, and protected routes in React.

---

## ✨ Features

### 🔹 Backend (Django + DRF)
- 🔐 **Authentication**: Uses JWT authentication via `djangorestframework-simplejwt`.
- 🗄️ **Database**: PostgreSQL for robust data storage.
- 🌍 **CORS Handling**: Configured using `django-cors-headers` to allow frontend API requests.
- 📡 **REST API**: Built with Django Rest Framework (DRF) to provide secure endpoints.

### 🔹 Frontend (React + Axios)
- 🔑 **JWT Authentication**: Handles user login, logout, and token storage.
- ⚡ **Axios Interceptors**: Automatically injects the authorization token into requests.
- 🔒 **Protected Routes**: Uses a `ProtectedRoute` component to restrict access to authenticated users.
- 🔄 **Login Page Redirection**: Redirects users to the login page when accessing protected routes if not authenticated or if the token has expired.
- 🔁 **Automatic Token Refresh**: Axios interceptors attempt to refresh the token before redirecting to login if the access token has expired.
- ⚙️ **React Hooks & Context API**: Manages authentication state efficiently.

---

## 🚀 Getting Started

### 📌 Prerequisites
- 🐍 Python 3.x
- 🗄️ PostgreSQL
- 💻 Node.js & npm/yarn

### 🛠️ Backend Setup
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/django-react-auth.git
   cd django-react-auth/backend
   ```
2. Install dependencies using Poetry:
   ```sh
   poetry install
   ```
3. Configure `.env` file for database settings.
4. Apply migrations:
   ```sh
   poetry run python manage.py migrate
   ```
5. Create a superuser:
   ```sh
   poetry run python manage.py createsuperuser
   ```
6. Run the development server:
   ```sh
   poetry run python manage.py runserver
   ```

### 🎨 Frontend Setup
1. Navigate to the frontend folder:
   ```sh
   cd ../frontend
   ```
2. Install dependencies:
   ```sh
   npm install  # or yarn install
   ```
3. Start the React development server:
   ```sh
   npm start  # or yarn start
   ```

---

## 🔄 API Authentication Flow
1. 🔑 User logs in and receives an access & refresh token.
2. 📥 The access token is stored in memory for requests; the refresh token is stored securely.
3. 🔄 Axios interceptors automatically append the token to API requests.
4. ⏳ If the access token expires, Axios attempts to refresh it using the refresh token.
5. 🚪 If the token refresh fails, the user is redirected to the login page.
6. 🔒 Protected routes ensure only authenticated users can access certain pages.

---

## 📁 Folder Structure
```
├── backend
│   ├── manage.py
│   ├── pyproject.toml
│   ├── poetry.lock
│   ├── backend (Django project folder)
│   ├── api (Django app folder)
│   └── ...
├── frontend
│   ├── src
│   │   ├── components
│   │   ├── pages
│   │   ├── styles
│   │   ├── api.js (Axios instance & API calls)
│   │   ├── context (Auth context)
│   │   └── ...
│   ├── package.json
│   └── ...
└── README.md
```

---

## 📜 License
This project is licensed under the MIT License.
