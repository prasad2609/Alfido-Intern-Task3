# Model Deployment Using FastAPI and Docker

## Introduction

This project demonstrates the deployment of a machine learning model using FastAPI and Docker. The trained sentiment analysis model is exposed as a REST API that accepts movie reviews and returns sentiment predictions.

The application is containerized using Docker to ensure portability and consistent execution across environments.

## Objective

The objective of this project is to:

* Deploy a trained machine learning model using FastAPI.
* Create API endpoints for inference.
* Containerize the application using Docker.
* Demonstrate local deployment and testing using CURL requests.

## Technologies Used

* Python
* FastAPI
* TensorFlow
* Docker
* Uvicorn

## API Endpoints

### GET /

Returns API status information.

Example Response:

{
"message": "Sentiment Analysis API is running"
}

### POST /predict

Accepts review text and returns sentiment prediction.

Example Request:

{
"review": "This movie was fantastic"
}

Example Response:

{
"sentiment": "Positive"
}

## Docker Containerization

A Dockerfile was created to package the application and its dependencies into a container.

Build Command:

docker build -t sentiment-api .

Run Command:

docker run -p 8000:8000 sentiment-api

## Testing the API

Example CURL Command:

curl -X POST "http://localhost:8000/predict" -H "Content-Type: application/json" -d "{"review":"This movie was fantastic"}"

Expected Output:

{
"sentiment": "Positive"
}

## Results

The API successfully receives input text and returns sentiment predictions. Docker enables the application to be deployed consistently on any system supporting containers.

## Conclusion

This project successfully demonstrates machine learning model deployment using FastAPI and Docker. The solution provides a scalable and portable method for serving machine learning predictions through REST APIs.
