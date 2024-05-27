# Shipping Microservice

This project is a shipping microservice built with Spring Boot. It provides an API to create shipments using different shipment carriers (FedEx and UPS) while hiding the complexity of integrating with multiple shipment services.

## Features

- Create shipments using FedEx and UPS carriers.
- Validates input parameters for each carrier.
- Provides appropriate error messages for invalid inputs.

## Technologies

- Java 11
- Spring Boot 2.6.4
- Lombok
- JUnit 5
- Mockito

## Setup

1. **Clone the repository**:
   ```sh
   git clone https://github.com/hadeel-ux/Shipment.git
   cd Shipment


2. Build the project:
Ensure you have Maven installed, then run:

mvn clean install
Run the application:

mvn spring-boot:run


Running the Application
The application can be run locally using Maven. Once started, the API will be available at http://localhost:8024.

API Endpoints
Create Shipment
## Endpoint: POST /api/shipments/
## Example Request for Fedex
Request Body:
{
  "carrierId": "fedex",
  "carrierServiceID": "fedexAIR",
  "packageDetails": {
    "width": 10,
    "height": 10,
    "length": 10,
    "weight": 1000
  }
}

Response:

Success:
{
  "message": "FedEx shipment created successfully"
}

Error:
{
  "message": "Invalid carrier service ID"
}

## Example Request for UPS
Request Body:
{
  "carrierId": "ups",
  "shipmentServiceID": "UPSExpress",
  "packageDetails": {
    "width": 10,
    "height": 10,
    "length": 10,
    "weight": 10
  }
}

Response:
Success:
{
  "message": "UPS shipment created successfully"
}
Error:
Copy code
{
  "message": "Invalid shipment service ID"
}


