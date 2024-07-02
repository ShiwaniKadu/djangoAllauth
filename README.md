# djangoAllauth

djangoAllauth is a Django project that demonstrates how to integrate Django Allauth for social authentication using GitHub. This project features a custom user model and the necessary configurations to enable GitHub login for users.

## Features

- Custom user model with fields for name, email, and GitHub profile URL.
- Social authentication using GitHub.
- Django Allauth integration for handling authentication.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.7 or higher
- Django 5.0.6 or higher
- GitHub account for setting up OAuth application

## Installation

Follow these steps to set up the project locally:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/djangoAllauth.git
    cd djangoAllauth
    ```

2. **Create and activate a virtual environment:**

    ```bash
    python -m venv env
    source env/bin/activate  # On Windows, use `env\Scripts\activate`
    ```

3. **Install the dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Set up the database:**

    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

5. **Run the development server:**

    ```bash
    python manage.py runserver
    ```

6. **Access the application:**

    Open your web browser and go to `http://127.0.0.1:8000`.

## Configuration

To configure GitHub OAuth, follow these steps:

1. **Create a GitHub OAuth application:**

    - Go to your GitHub account settings.
    - Navigate to "Developer settings" -> "OAuth Apps" -> "New OAuth App".
    - Set the application name, homepage URL, and authorization callback URL (e.g., `http://127.0.0.1:8000/accounts/github/login/callback/`).
    - Register the application and note down the `Client ID` and `Client Secret`.

2. **Update the Django settings:**

    Add your GitHub OAuth credentials to the `settings.py` file:

    ```python
    SOCIALACCOUNT_PROVIDERS = {
        "github": {
            "APP": {
                "client_id": "YOUR_CLIENT_ID",
                "secret": "YOUR_CLIENT_SECRET",
            }
        }
    }
    ```
