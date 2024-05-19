
# Dmoney API Chaining & Assertion Using Jmeter

This repository provides a comprehensive guide to using JMeter for API collection chaining and assertions. Follow the steps below to set up JMeter and execute a series of API tests, including logging in, creating customer or agent , performing transactions, and verifying results.



## List Of API chaining && Assertion

### Table of Contents

1. [Prerequisites](#prerequisites)
2. [Setup Instructions](#setup-instructions)
    - [Install JMeter](#install-jmeter)
    - [Set Up HTTP Header Manager](#set-up-http-header-manager)
    - [Set User Defined Variables](#set-user-defined-variables)
3. [Test Plan](#test-plan)
    - [Login Admin With Valid Credentials](#login-admin-with-valid-credentials)
    - [Get All User List](#get-all-user-list)
    - [Create Customer With Random Data](#create-customer-with-random-data)
    - [Search Created Customer By ID](#search-created-customer-by-id)
    - [Create Agent With Random Data](#create-agent-with-random-data)
    - [Search Created Agent By ID](#search-created-agent-by-id)
    - [Deposit To Agent Account](#deposit-to-agent-account)
    - [Verify Transaction Status](#verify-transaction-status)
    - [Check System Balance After Agent Deposit](#check-system-balance-after-agent-deposit)
    - [Check Agent Balance After Agent Deposited](#check-agent-balance-after-agent-deposited)
    - [Agent Deposit To Customer](#agent-deposit-to-customer)
    - [Verify Transaction After Agent Deposit to Customer](#verify-transaction-after-agent-deposit-to-customer)
    - [Check Customer Balance After Customer Deposited](#check-customer-balance-after-customer-deposited)
    - [Money Withdraw By Customer](#money-withdraw-by-customer)
    - [Send Money By Customer to Customer](#send-money-by-customer-to-customer)
    - [Check Transaction After Send Money](#check-transaction-after-send-money)
4. [Running the Test](#running-the-test)
5. [Analyzing Results](#analyzing-results)
6. [Contributing](#contributing)
7. [License](#license)

## Prerequisites

- Java Development Kit (JDK) installed and configured on your system.
- Apache JMeter downloaded and extracted.

## Setup Instructions

### Install JMeter

1. Download the latest version of Apache JMeter from the [Apache JMeter website](https://jmeter.apache.org/download_jmeter.cgi).
2. Extract the downloaded ZIP file to a directory of your choice.

### Set Up HTTP Header Manager

1. Open JMeter and create a new Test Plan.
2. Add a Thread Group to the Test Plan.
3. Within the Thread Group, add an HTTP Header Manager:
   - Right-click on Thread Group > Add > Config Element > HTTP Header Manager.
   - Add headers such as `Content-Type` and `Authorization` as needed.

### Set User Defined Variables

1. Add User Defined Variables:
   - Right-click on Test Plan > Add > Config Element > User Defined Variables.
   - Define variables such as `baseURL`, `adminUsername`, and `adminPassword`.

## Test Plan

### Login Admin With Valid Credentials

1. Add an HTTP Request Sampler for the login API:
   - Set the method to POST.
   - Add parameters for the login credentials.
2. Add a Response Assertion:
   - Right-click on the HTTP Request Sampler > Add > Assertions > Response Assertion.
   - Configure it to assert that the response contains a successful login message or status code.
3. Extract the Authentication Token:
   - Right-click on the HTTP Request Sampler > Add > Post Processors > JSON Extractor.
   - Set the JSON Extractor to extract the token from the response, e.g., `$.token`.

### Get All User List

1. Add an HTTP Request Sampler to fetch the user list:
   - Set the method to GET.
   - Use the `baseURL` variable for the URL.
   - Add the authentication token in the HTTP Header Manager.
2. Add a Response Assertion:
   - Configure it to assert that the status code is 200 and the response contains the expected user data.
3. Extract Necessary Data:
   - Use JSON Extractor to extract specific user data if required.

### Create Customer With Random Data

1. Add an HTTP Request Sampler to create a customer:
   - Set the method to POST.
   - Generate random data using JMeter functions.
2. Add a Response Assertion:
   - Configure it to assert that the response contains a successful creation message or status code.
3. Extract the Customer ID:
   - Use a JSON Extractor to extract the customer ID from the response, e.g., `$.customerId`.

### Search Created Customer By ID

1. Add an HTTP Request Sampler to search for the created customer:
   - Set the method to GET.
   - Use a variable to replace the customer ID in the URL.
2. Add a Response Assertion:
   - Configure it to assert that the status code is 200 and the response contains the expected customer data.
3. Extract Necessary Data:
   - Use JSON Extractor to extract any required information from the response.

### Create Agent With Random Data

1. Add an HTTP Request Sampler to create an agent:
   - Set the method to POST.
   - Generate random data using JMeter functions.
2. Add a Response Assertion:
   - Configure it to assert that the response contains a successful creation message or status code.
3. Extract the Agent ID:
   - Use a JSON Extractor to extract the agent ID from the response, e.g., `$.agentId`.

### Search Created Agent By ID

1. Add an HTTP Request Sampler to search for the created agent:
   - Set the method to GET.
   - Use a variable to replace the agent ID in the URL.
2. Add a Response Assertion:
   - Configure it to assert that the status code is 200 and the response contains the expected agent data.
3. Extract Necessary Data:
   - Use JSON Extractor to extract any required information from the response.

### Deposit To Agent Account

1. Add an HTTP Request Sampler to deposit to the agent's account:
   - Set the method to POST.
   - Provide the necessary parameters for the deposit.
2. Add a Response Assertion:
   - Configure it to assert that the response contains a successful deposit message or status code.
3. Extract Transaction ID:
   - Use a JSON Extractor to extract the transaction ID from the response, e.g., `$.transactionId`.

### Verify Transaction Status

1. Add assertions to verify the transaction status in the response:
   - Use Response Assertion to check for success messages or status codes.
2. Extract Necessary Data if required for future requests:
   - Use JSON Extractor to extract additional data if needed.

### Check System Balance After Agent Deposit

1. Add an HTTP Request Sampler to check the system balance:
   - Set the method to GET.
   - Add the necessary authentication token.
2. Add a Response Assertion:
   - Configure it to assert that the balance has been updated correctly.
3. Extract Necessary Data if required:
   - Use JSON Extractor to get the updated balance.

### Check Agent Balance After Agent Deposited

1. Add an HTTP Request Sampler to check the agent's balance:
   - Set the method to GET.
   - Add the necessary authentication token.
2. Add a Response Assertion:
   - Configure it to assert that the agent's balance has been updated correctly.
3. Extract Necessary Data if required:
   - Use JSON Extractor to get the updated balance.

### Agent Deposit To Customer

1. Add an HTTP Request Sampler for the agent to deposit to a customer:
   - Set the method to POST.
   - Provide the necessary parameters for the deposit.
2. Add a Response Assertion:
   - Configure it to assert that the response contains a successful deposit message or status code.
3. Extract Transaction ID:
   - Use a JSON Extractor to extract the transaction ID from the response, e.g., `$.transactionId`.

### Verify Transaction After Agent Deposit to Customer

1. Add assertions to verify the transaction status in the response:
   - Use Response Assertion to check for success messages or status codes.
2. Extract Necessary Data if required for future requests:
   - Use JSON Extractor to extract additional data if needed.

### Check Customer Balance After Customer Deposited

1. Add an HTTP Request Sampler to check the customer's balance:
   - Set the method to GET.
   - Add the necessary authentication token.
2. Add a Response Assertion:
   - Configure it to assert that the customer's balance has been updated correctly.
3. Extract Necessary Data if required:
   - Use JSON Extractor to get the updated balance.

### Money Withdraw By Customer

1. Add an HTTP Request Sampler for the customer to withdraw money:
   - Set the method to POST.
   - Provide the necessary parameters for the withdrawal.
2. Add a Response Assertion:
   - Configure it to assert that the response contains a successful withdrawal message or status code.
3. Extract Transaction ID:
   - Use a JSON Extractor to extract the transaction ID from the response, e.g., `$.transactionId`.

### Send Money By Customer to Customer

1. Add an HTTP Request Sampler for one customer to send money to another:
   - Set the method to POST.
   - Provide the necessary parameters for the transfer.
2. Add a Response Assertion:
   - Configure it to assert that the response contains a

## Running the Test

1. Ensure all configurations and samplers are set up correctly.
2. Run the test plan by clicking the green start button in JMeter.

## Analyzing Results

1. Use Listeners such as View Results Tree, Summary Report, and Aggregate Report to analyze the test results.
2. Check for any errors and verify the assertions.

### Report Screenshot

Here is a sample screenshot of the test results:

![Report Screenshot](https://github.com/Apurbokabbo/api_chaining_assertion_using_jmeter/blob/main/src/Dashboard.png)

## YouTube Video

Watch step-by-step guide on YouTube  :

[Watch the Video on YouTube](https://www.youtube.com/watch?v=xxFxrjZTmX0&ab_channel=ApurboKabbo)

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to suggest improvements or report bugs.
