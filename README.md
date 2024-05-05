# Django-Compose-Lamp
Getting Started

This repository provides a Docker Compose setup that simplifies the deployment of your Django application with Django REST framework. It leverages pre-built Docker images for Python and PostgreSQL, ensuring consistency and ease of use.

Prerequisites

    Docker: Install Docker from https://www.docker.com/ according to your operating system.
    Docker Compose: Install Docker Compose by following the instructions on https://docs.docker.com/compose/install/.
    A code editor or IDE of your choice (e.g., Visual Studio Code, PyCharm).

Project Structure

This repository is expected to have the following basic structure:

your_project/
├── docker-compose.yml  # This README file you're reading
├── Dockerfile          # (Optional) If you need a custom image for your Django application
├── app/                # Your Django application code goes here (replace with your actual app name)
│   ├── __init__.py
│   ├── manage.py
│   ├── requirements.txt  # Your project's dependencies
│   └── ...              # Your application modules and files
├── ...                 # Other project files (if any)

Using Docker Compose

    Clone the repository:
    Bash

    git clone https://github.com/your-username/your-project-name.git
    cd your-project-name

    Use code with caution.

Install dependencies:

    If using a requirements.txt file:
    Bash

    docker-compose run --rm web pip install -r requirements.txt

    Use code with caution.

If managing dependencies manually:
Bash

docker-compose run --rm web pip install django djangorestframework  # Replace with your specific dependencies

Use code with caution.

Build and run the application:

To build the images and start the containers in detached mode (background):
Bash

docker-compose up -d

Use code with caution.

To build the images, start the containers, and open a bash shell in the web container:
Bash

docker-compose run --rm web bash

Use code with caution.

    Access your application:
        Your Django application will be accessible at http://localhost:8000 in your browser.
        The PostgreSQL database will be running on port 5432 within the container network.

Environment Variables

The docker-compose.yml file defines some environment variables for the database container:

    POSTGRES_DB: Set to postgres by default. You can change this to your desired database name.
    POSTGRES_USER: Set to user by default. Update this with your database username.
    POSTGRES_PASSWORD: Set to password by default. Replace this with a strong password.

You can modify these values directly in the file or set environment variables at runtime using docker-compose up -d -e POSTGRES_PASSWORD=your_strong_password.

Development Workflow

    Make changes to your Django application code in the app directory.
    Rebuild the image with docker-compose build web.
    Restart the containers with docker-compose up -d.
    The changes should be reflected in your running application.

Persistence (Optional)

If you want your database data to persist between container restarts, uncomment the volumes section for the db service in docker-compose.yml and create a directory on your host machine to mount the volume.

Contributing

Feel free to submit pull requests for bug fixes or improvements to this repository.

License

(Include your chosen license information here, e.g., MIT License)
