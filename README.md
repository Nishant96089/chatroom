# Chatroom Project

This is a simple chatroom application built with Django. Users can create chat rooms, send messages, and see messages from other users in real-time.

## Features

- Create chat rooms
- Send and receive messages in real-time
- User authentication (if implemented)
- Easy to deploy on platforms like Vercel

## Prerequisites

- Python 3.x
- Django 5.0.6
- Pipenv or virtualenv (optional but recommended)

## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/yourusername/chatroom.git
    cd chatroom
    ```

2. **Create and activate a virtual environment:**

    Using `pipenv`:

    ```sh
    pipenv shell
    ```

    Or using `virtualenv`:

    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install the dependencies:**

    ```sh
    pip install -r requirements.txt
    ```

4. **Run database migrations:**

    ```sh
    python manage.py migrate
    ```

5. **Collect static files:**

    ```sh
    python manage.py collectstatic
    ```

6. **Create a superuser (optional but recommended):**

    ```sh
    python manage.py createsuperuser
    ```

## Running the Project

1. **Start the development server:**

    ```sh
    python manage.py runserver
    ```

2. Open your web browser and go to `http://127.0.0.1:8000/`.

## Deployment

This project can be deployed on platforms like Vercel. Follow these steps to deploy:

1. **Install Vercel CLI:**

    ```sh
    npm i -g vercel
    ```

2. **Initialize a new Vercel project:**

    ```sh
    vercel init
    ```

3. **Create `vercel.json` in the root of your project:**

    ```json
    {
      "version": 2,
      "builds": [
        {
          "src": "manage.py",
          "use": "@vercel/python",
          "config": { "maxLambdaSize": "15mb" }
        }
      ],
      "routes": [
        { "src": "/static/(.*)", "dest": "/static/$1" },
        { "src": "/(.*)", "dest": "manage.py" }
      ]
    }
    ```

4. **Deploy the project:**

    ```sh
    vercel --prod
    ```

## Project Structure

```plaintext
chatroom/
│
├── chat/
│   ├── migrations/
│   ├── static/
│   ├── templates/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
│
├── chatroom/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── manage.py
└── requirements.txt
