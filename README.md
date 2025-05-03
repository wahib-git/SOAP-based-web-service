# Currency Conversion SOAP Web Service

This project is a Spring Boot application that provides a SOAP-based web service for currency conversion. It demonstrates how to use Spring Web Services and JAXB for XML-based communication.

## Features

- SOAP web service for currency conversion.
- WSDL and XSD schema for defining the service contract.
- JAXB-generated classes for XML-to-Java object mapping.
- Spring Boot configuration for easy setup and deployment.

## Prerequisites

- Java 17 or higher
- Maven 3.9.9 or higher

## Getting Started

### Clone the Repository

```bash
https://github.com/wahib-git/SOAP-based-web-service.git
cd currency-conversion-service
```

### Build the Project

Use the Maven wrapper to build the project:

```bash
./mvnw clean install
```

### Run the Application

Start the application using the Maven wrapper:

```bash
./mvnw spring-boot:run
```

The application will start on `http://localhost:8080`.

### Access the WSDL

The WSDL for the SOAP service is available at:

```
http://localhost:8080/ws/currencyConverter.wsdl
```

## Usage

### Sample Request

Send a `ConvertCurrencyRequest` to the SOAP endpoint:

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:cur="http://example.com/currency">
   <soapenv:Header/>
   <soapenv:Body>
      <cur:ConvertCurrencyRequest>
         <cur:fromCurrency>USD</cur:fromCurrency>
         <cur:toCurrency>EUR</cur:toCurrency>
         <cur:amount>100</cur:amount>
      </cur:ConvertCurrencyRequest>
   </soapenv:Body>
</soapenv:Envelope>
```

### Sample Response

The service will respond with a `ConvertCurrencyResponse`:

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:cur="http://example.com/currency">
   <soapenv:Header/>
   <soapenv:Body>
      <cur:ConvertCurrencyResponse>
         <cur:convertedAmount>90.0</cur:convertedAmount>
      </cur:ConvertCurrencyResponse>
   </soapenv:Body>
</soapenv:Envelope>
```

## Project Structure

- **`src/main/java`**: Contains the Java source code.
  - `com.example.currency`: Main package for the application.
  - `com.example.currency.endpoint`: Contains the SOAP endpoint implementation.
  - `com.example.currency.config`: Contains the Spring Web Services configuration.
- **`src/main/resources`**: Contains the XSD schema and application properties.
- **`pom.xml`**: Maven configuration file.

## Technologies Used

- Spring Boot
- Spring Web Services
- JAXB (Jakarta XML Binding)
- Maven

## License

This project is licensed under the [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

## References

- [Spring Web Services Documentation](https://docs.spring.io/spring-ws/docs/current/reference/html/)
- [Spring Boot Documentation](https://docs.spring.io/spring-boot/docs/current/reference/html/)
- [Producing a SOAP Web Service](https://spring.io/guides/gs/producing-web-service/)
