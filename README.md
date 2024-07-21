# StaySpotter

StaySpotter is a comprehensive solution designed to streamline the process of finding accommodations for travelers by aggregating listings from various platforms such as Booking, Airbnb, and Trivago. This repository includes the mobile application, the microservices backend, and the Python web scraper.

## Table of Contents

- [Introduction](#introduction)
- [Technologies Used](#technologies-used)
- [Architecture](#architecture)
- [Mobile Application](#mobile-application)
- [Backend Services](#backend-services)
- [Web Scraper](#web-scraper)

## Introduction

StaySpotter is an application that simplifies the accommodation search process for travelers by aggregating data from multiple platforms based on user-defined filters. Users can save accommodations to a favorites list and receive daily updates on their availability and price changes. The application is designed for high traffic, leveraging a microservices architecture to ensure scalability and performance.


## Technologies Used

### Mobile Application

* Kotlin: Primary programming language for the Android app.
* Jetpack Compose: Modern toolkit for building native Android UI.

### Backend Services

* Java & Spring Boot: Framework for building microservices.
* Spring Cloud: Provides tools for service discovery, configuration, and routing.
* PostgreSQL: Database management system for handling application data.
* Docker: Containerization platform for deploying microservices.

### Web Scraper

* Python: Programming language for the web scraping service.
* BeautifulSoup: Library for parsing HTML and XML documents.
* Selenium: Tool for automating web browser interactions.
* Flask: Micro web framework for exposing the scraper service as REST endpoints.

## Architecture

The StaySpotter system is built on a robust microservices architecture, ensuring scalability, modularity, and maintainability. Each microservice communicates with others via RESTful endpoints, maintaining a loosely coupled system that allows independent updates and deployments.

![deployment-diagram](https://github.com/user-attachments/assets/fdb4bdcd-b8e1-4918-9099-9f2e5ac56ba3)

### Mobile Application

The mobile application is the user's primary interface with StaySpotter. It is developed using Kotlin and Jetpack Compose for Android devices.
#### Features

* *User Registration and Authentication*: Secure user registration and login functionality.
* *Search Accommodations*: Users can search for accommodations using various filters.
* *Favorites List*: Save preferred accommodations to a favorites list.
* *Daily Notifications*: Receive updates on the availability and price changes of saved accommodations.

### Screenshots

  **User Registration Flow**: 
  
![create-acc](https://github.com/user-attachments/assets/74fce6d7-d28d-42d7-be6c-78d908dfc28f)

  **Search Accommodations Flow**: 
  
![filters-flow](https://github.com/user-attachments/assets/a803e522-9830-4dc0-8822-e605537f49f0)
![search-and-favourite-flow](https://github.com/user-attachments/assets/01a73386-c7ea-43a3-9488-c53c5a03fb21)
  
  **Favorites List & User Stats Tab**:
  
![favourite-stats-tab](https://github.com/user-attachments/assets/f5da4f19-ec97-40f3-8208-38be2001e7e9)

### Backend Services

The backend is composed of several microservices, each with a specific role:

* Eureka Service Discovery: Used for service discovery to register and locate services.
* API Gateway: Routes requests to the appropriate service.
* Core Service: Handles the core business logic of the application.
* Web Scraping Service: Scrapes data from external platforms and returns structured information.
* Data Service: Manages user data, accommodation listings, and search statistics.
* Web Scraper: The web scraper service is responsible for fetching accommodation data from external sources. It uses Python libraries like BeautifulSoup and Selenium to parse HTML content and handle dynamic web pages that require interaction. Its workflow is the following:
  * Construct Search URL: Based on user filters.
  * Fetch and Parse Data: Use Selenium for dynamic content and BeautifulSoup for parsing.
  * Return Results: Send structured data back to the backend service.
