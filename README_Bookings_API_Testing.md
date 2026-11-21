::: {align="center"}
# 🧪 Bookings API Testing

**API testing with Postman + Newman**

Test booking endpoints, validate responses, and generate an HTML test
report.

![Postman](https://img.shields.io/badge/Tool-Postman-orange?logo=postman)
![Newman](https://img.shields.io/badge/Runner-Newman-blue)
![API](https://img.shields.io/badge/API-REST-green)
:::

------------------------------------------------------------------------

## 📌 About the project

A hands-on API testing project using the **Restful-Booker demo API**.
The Postman collection sends booking requests and checks status codes,
response time, response size, JSON format, and booking data.

**Base URL:** `https://restful-booker.herokuapp.com`

## 🔍 What is tested?

  Request                       Method   Purpose
  ----------------------------- -------- --------------------------------------
  GetBookingIds                 GET      Retrieve booking IDs
  CreateBooking                 POST     Create a booking with generated data
  GetBookingSpecificbookingid   GET      Retrieve a booking by ID
  CreateToken                   POST     Request an authentication token
  UpdateBooking                 PUT      Update a booking
  DeleteBooking                 DELETE   Delete a booking

## 🛠️ Tools

-   **Postman** --- create requests and write test scripts
-   **Newman** --- run the collection from the command line
-   **Newman HTML Reporter** --- create a browser-viewable test report

## ▶️ Run it locally

### 1. Install Newman and the HTML reporter

``` bash
npm install -g newman
npm install -g newman-reporter-html
```

### 2. Import into Postman

Import these two files:

-   `Bookings.postman_collection.json`
-   `Test Environment.postman_environment.json`

Select the **Test Environment** before running. Its `base_url` variable
points to the Restful-Booker API.

### 3. Run from the project folder

``` bash
newman run "Bookings.postman_collection.json" -e "Test Environment.postman_environment.json" -r cli,html --reporter-html-export "Bookings_Report.html"
```

When the run completes, open `Bookings_Report.html` in your browser.

## 📸 Execution screenshots

### Newman running the API collection

![Newman execution]("C:\Users\USER\Documents\API testing\booking newman extra.png")

### HTML report file generated

![HTML report generated]("C:\Users\USER\Documents\API testing\booking newman report.png")

## 📊 Sample report snapshot

The included Newman report records this sample run:

  Metric                    Result
  ----------------------- --------
  Requests                       7
  Iterations                     1
  Assertions                    33
  Failed tests                   4
  Skipped tests                  0
  Average response time     368 ms

The report is included as `Bookings_Report.html`. Open it locally in a
browser to inspect the request-level details. Test results can change
between runs because the API and network conditions are external.

## ⚠️ Before publishing

Review the collection before making the repository public. Replace
hard-coded cookies or tokens with variables, remove any real
credentials, and avoid committing secrets.

This project uses a public demo API for learning and testing. Do not use
destructive requests on data you do not own.

------------------------------------------------------------------------

::: {align="center"}
**Built for learning API testing with Postman and Newman.**
:::
