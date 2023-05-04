# Rest Countries API #

This is a collection of test scenarios for the Rest Countries API. The Rest Countries API provides information about countries, including their names, currencies, languages, and more.

## Getting Started ##
To get started with this test suite, you will need to have Postman installed on your machine.

    Clone this repository to your local machine.
    Open Postman and import the Rest-Countries-API.postman_collection.json file.
    Set up the global environment variables as described in the Global Environment Variables section.
    Run the requests and verify the results.

## Global Environment Variables ##

The following global environment variables are used in this test suite:
| Variable | Initial value |
| -------- | ----- |
| baseURL | https://restcountries.com/v3.1/ | 
| name | deutschland | 
| lang | spa |
| currency | cop |

## Test scripts ##
The following test scripts are used in this test suite:
```
// Test to ensure the response contains valid JSON
pm.test("Response is valid JSON", function() {
    pm.response.to.have.jsonBody();
});

// Test to ensure the response status code is 200 OK
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```


## Test Scenarios ##

### NAME Endpoint ###

#### Test Scenario 1 - Get country by name ####
```
Given a valid country name
When a GET request is sent to /name/{name} with the name parameter set to the country name
Then a response with a status code of 200 is returned, and the response body contains information about the requested country.
```

#### Test Scenario 2 - Get country by invalid name ####
```
Given an invalid country name
When a GET request is sent to /name/{name} with the name parameter set to the invalid country name
Then a response with a status code of 404 is returned, and the response body contains an error message indicating that the requested resource was not found.
```

### CURRENCY Endpoint ###

#### Test Scenario 1 - Get countries by currency ####
```
Given a valid currency code
When a GET request is sent to /currency/{currency} with the currency parameter set to the currency code
Then a response with a status code of 200 is returned, and the response body contains information about all countries that use the requested currency.
```

#### Test Scenario 2 - Get countries by invalid currency ####
```
Given an invalid currency code
When a GET request is sent to /currency/{currency} with the currency parameter set to the invalid currency code
Then a response with a status code of 404 is returned, and the response body contains an error message indicating that the requested resource was not found.
```

### LANGUAGE Endpoint ###
#### Test Scenario 1 - Get countries by language ####
```
Given a valid language code
When a GET request is sent to /lang/{language} with the language parameter set to the language code
Then a response with a status code of 200 is returned, and the response body contains information about all countries that use the requested language.
```

#### Test Scenario 2 - Get countries by invalid language ####
```
Given an invalid language code
When a GET request is sent to /lang/{language} with the language parameter set to the invalid language code
Then a response with a status code of 404 is returned, and the response body contains an error message indicating that the requested resource was not found.
```
Contact

For questions or issues related to this project, please contact the repository owner.
