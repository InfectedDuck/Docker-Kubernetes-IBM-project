# RealTimeGuestBookApp

This project is a real-time, dynamic guestbook web application built using **Go** for the backend and **HTML**, **CSS**, and **JavaScript** for the frontend. The application utilizes **Redis** as a data store to handle user-submitted entries and is containerized using **Docker** for ease of deployment. The app can run both locally and in cloud environments, with a flexible architecture that scales to meet high traffic demands.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Technologies](#technologies)
- [Deployment](#deployment)

## Overview

The Guestbook Web Application allows users to submit guestbook entries, which are displayed in real time. The app is designed to be simple and fast, with a focus on efficient handling of user data. Two versions of the application are available:

1. **Version 1**: Focuses on core guestbook functionality, including the ability to add entries and view them dynamically using a polling mechanism.
2. **Version 2**: Adds enhancements such as real-time updates, improved UI/UX, and Redis integration for fast data retrieval.

## Features

* **Real-time Guestbook Entries**: Users can submit messages that are instantly visible to all other users.
* **Dynamic User Interface**: Built using **HTML**, **CSS**, and **JavaScript** with jQuery for handling asynchronous updates without page reloads.
* **Data Persistence with Redis**: Guestbook entries are stored in **Redis**, providing fast in-memory data storage.
* **Dockerized Deployment**: The application is containerized using **Docker**, ensuring ease of deployment and consistent performance across different environments.
* **Scalable Architecture**: The design allows horizontal scaling with Redis managing the guestbook data, and the backend serving requests efficiently.
* **Automated Frontend Polling**: The frontend fetches the latest guestbook entries from the backend at regular intervals.
* **Modular Go Backend**: Backend is written in Go, ensuring performance and easy management of application logic.

## Architecture

The guestbook application uses a client-server model with the following components:

1. **Frontend**: A responsive and dynamic user interface built with HTML, CSS, and JavaScript. The frontend continuously polls the backend for new guestbook entries and displays them dynamically.
   
2. **Backend**: A **Go** web server that handles incoming requests and interacts with Redis for storing and retrieving guestbook entries.
   
3. **Redis**: A high-performance in-memory key-value store used to persist guestbook entries and handle concurrent requests efficiently.

4. **Docker**: The application is containerized with Docker, allowing seamless deployment and scaling in cloud environments.

## Installation

To run this project locally or deploy it, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/InfectedDuck/RealTimeGuestBookApp.git
    cd RealTimeGuestBookApp
    ```

2. Build and run the application using Docker:
    ```bash
    docker build -t guestbook .
    docker run -p 3000:3000 guestbook
    ```

3. Access the guestbook application at `http://localhost:3000`.

4. Ensure **Redis** is running locally or use a Dockerized Redis instance:
    ```bash
    docker run --name redis -p 6379:6379 redis
    ```

## Usage

Once the application is running:

1. Open the application in your browser.
2. Add a guestbook entry using the provided form.
3. Submitted entries will appear dynamically without needing to refresh the page.

## Technologies

The following technologies and tools were used in this project:

* **Go**: Backend programming language
* **Redis**: In-memory database for fast data retrieval
* **HTML/CSS/JavaScript**: Frontend technologies for building the user interface
* **jQuery**: Used for handling asynchronous HTTP requests and DOM manipulation
* **Docker**: Used to containerize the application for ease of deployment
* **Redis Docker Image**: Used to deploy Redis within a container

## Deployment

The application can be deployed using Docker for both the Go-based backend and Redis. 

To deploy in a cloud environment:

1. Ensure your Redis instance is set up.
2. Build and push the Docker image to your container registry:
    ```bash
    docker build -t your-repo/guestbook .
    docker push your-repo/guestbook
    ```

3. Set up your cloud Kubernetes cluster or Docker environment and pull the image:
    ```bash
    docker pull your-repo/guestbook
    docker run -p 3000:3000 your-repo/guestbook
    ```

4. Configure environment variables to point to your Redis instance if running externally.



## License
This project is licensed under the Apache License 2.0. See the [LICENSE](LICENSE) file for details. <br>
This project is made as a part of IBM Course.

