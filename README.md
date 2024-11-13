# AWS-Case_study
# Weather Service Application
This project is a Spring Boot application that fetches and saves weather data for a given city using the OpenWeatherMap API. The application is designed to run on AWS Lambda using the AWS Serverless Java Container.

## Table of Contents
- Overview
- Architecture
- Setup
- Usage
- Error Handling
- Configuration
- Dependencies

## Overview
The Weather Service Application provides weather information for a specified city. It fetches data from the OpenWeatherMap API and stores it in a DynamoDB table. The application is built using Spring Boot and is designed to run on AWS Lambda.

## Architecture
- **Controller**: Handles HTTP requests and responses.
- **Service**: Contains business logic for fetching and processing weather data.
- **Model**: Represents the weather data structure.
- **Exception Handling**: Manages exceptions and provides custom error responses.
- **AWS Lambda Handler**: Integrates the Spring Boot application with AWS Lambda.

## Setup
### Prerequisites
- Java 11 or higher
- Maven
- AWS CLI configured with appropriate permissions
- OpenWeatherMap API key

### Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/weather-service-app.git
    cd weather-service-app
    ```
2. Build the project using Maven:
    ```sh
    mvn clean install
    ```
3. Deploy the application to AWS Lambda using the AWS CLI or AWS Management Console.

## Usage
### Running Locally
1. Set the required environment variables in `application.properties`:
    ```properties
    weather.api.url=https://api.openweathermap.org/data/2.5/weather
    weather.api.key=your_api_key
    ```
2. Start the Spring Boot application:
    ```sh
    mvn spring-boot:run
    ```
3. Access the weather endpoint:
    ```sh
    curl http://localhost:8080/weather/{city}
    ```
### Running on AWS Lambda
1. Package the application for AWS Lambda:
    ```sh
    mvn package
    ```
2. Deploy the packaged application to AWS Lambda.

## Error Handling
The application includes global exception handling to manage errors gracefully:

- **404 Not Found**: Returned when the specified city is not found.
- **500 Internal Server Error**: Returned for any other errors during the request processing.

## Configuration
### AWS Configuration

Set the following properties in `application.properties`:
```properties
aws.accessKeyId=your_access_key_id
aws.secretKey=your_secret_key
aws.region=us-east-1
``
### Application Properties
Set the OpenWeatherMap API URL and key:
```properties
weather.api.url=https://api.openweathermap.org/data/2.5/weather
weather.api.key=your_api_key
```
## Dependencies
- Spring Boot
- AWS SDK for Java
- AWS Serverless Java Container
- OpenWeatherMap API
