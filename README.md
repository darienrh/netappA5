# netappA5
network application assignment 5


Assignment 5 – NET4005

Description:

This assignment demonstrates how to use Docker to containerize a simple Flask web application.
The Flask application generates a webpage that displays the client’s IP address. The goal is ti show how a dynamic web server can run inside a Docker container and be accessed from both a web browser and the CLI/terminal.

Requirements
- Python 3
- Flask library
- Docker Desktop

Process Documentation:

1. Creating the Flask Application

- I created a Python file (app.py) that uses the Flask framework.
- The application reads the client’s IP address using request.remote_addr and returns it in a simple HTML response.

2. Writing the Dockerfile

A Dockerfile was created to:

- Use a Python base image
- Copy the application files
- Install Flask
- Expose the application port
- Run the Flask app automatically

3. Building the Docker Image

Inside the project directory, I built the Docker image using:

docker image build -t flask-ip-app .

4. Running the Docker Container

After building the image, I ran the container with:

docker run -p 8080:5000 flask-ip-app

5. Accessing the Web Application
The application was accessed through the web browserby using "http://localhost:8080"

and the cli by useing "curl http://localhost:8080"

Both methods display the message:
“You are connecting from <client IP address>”

Note

A separate HTML file was not needed because the Flask application generates the HTML response dynamically using:
return f"<h1>You are connecting from {ip_addr}</h1>"

Contributor

darien ramirez-hennessey