
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

### Get All User List

1. Add an HTTP Request Sampler to fetch the user list:
   - Set the method to GET.
   - Use the `baseURL` variable for the URL.

### Create Customer With Random Data

1. Add an HTTP Request Sampler to create a customer:
   - Set the method to POST.
   - Generate random data using JMeter functions.

### Search Created Customer By ID

1. Add an HTTP Request Sampler to search for the created customer:
   - Set the method to GET.
   - Use a variable to store the customer ID from the previous response.

### Create Agent With Random Data

1. Repeat the steps used for creating a customer to create an agent.

### Search Created Agent By ID

1. Add an HTTP Request Sampler to search for the created agent:
   - Set the method to GET.
   - Use a variable to store the agent ID from the previous response.

### Deposit To Agent Account

1. Add an HTTP Request Sampler to deposit to the agent's account:
   - Set the method to POST.
   - Provide the necessary parameters for the deposit.

### Verify Transaction Status

1. Add assertions to verify the transaction status in the response.

### Check System Balance After Agent Deposit

1. Add an HTTP Request Sampler to check the system balance:
   - Set the method to GET.
   - Verify the balance change after the deposit.

### Check Agent Balance After Agent Deposited

1. Add an HTTP Request Sampler to check the agent's balance:
   - Set the method to GET.
   - Verify the balance change.

### Agent Deposit To Customer

1. Add an HTTP Request Sampler for the agent to deposit to a customer:
   - Set the method to POST.
   - Provide necessary parameters.

### Verify Transaction After Agent Deposit to Customer

1. Add assertions to verify the transaction status in the response.

### Check Customer Balance After Customer Deposited

1. Add an HTTP Request Sampler to check the customer's balance:
   - Set the method to GET.
   - Verify the balance change.

### Money Withdraw By Customer

1. Add an HTTP Request Sampler for the customer to withdraw money:
   - Set the method to POST.
   - Provide necessary parameters.

### Send Money By Customer to Customer

1. Add an HTTP Request Sampler for one customer to send money to another:
   - Set the method to POST.
   - Provide necessary parameters.

### Check Transaction After Send Money

1. Add assertions to verify the transaction status in the response.

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


## Result Screenshot

![ Report Screenshots](https://github.com/Apurbokabbo/api_chaining_assertion_using_jmeter/blob/main/src/Dashboard.png)


## Requirements

- Java Development Kit (JDK) installed and configured on your system.
- Apache JMeter downloaded and extracted.

## Setup Instructions

### Install JMeter

    1. Download the latest version of Apache JMeter from the [Apache JMeter website](https://jmeter.apache.org/download_jmeter.cgi).
    2. Extract the downloaded ZIP file to a directory of your choice.


