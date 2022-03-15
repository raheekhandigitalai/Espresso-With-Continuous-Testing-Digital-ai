# Espresso-With-Continuous-Testing-Digital-ai

This repository will briefly go over how to trigger Espresso tests using a sample project against the Digital.ai's Continuous Testing platform.

Documentation Page References:

- [Preparing your App and Test .apk Files](https://docs.experitest.com/display/TE/Preparing+your+App+and+Test+.apk+Files)

- [Rest API for running Espresso tests](https://docs.experitest.com/display/TE/Manage+Test+Run+with+the+API#ManageTestRunwiththeAPI-RunningAsyncEspresso/XCUITest)

Sample APKs can be downloaded here:

- [app-debug.apk](https://experibankespressoapp.s3.us-east-2.amazonaws.com/app-debug.apk)

- [app-debug-androidTest.apk](https://experibankespressoapp.s3.us-east-2.amazonaws.com/app-debug-androidTest.apk)

## Triggering Espresso Unit Tests

To trigger Espresso Unit Tests, we need to rely on an API call:

```
POST - POST /api/v1/test-run/execute-test-run-async
```

There are a number of parameters accepted, find a [full list of parameters here](https://docs.experitest.com/display/TE/Manage+Test+Run+with+the+API#ManageTestRunwiththeAPI-RunningAsyncEspresso/XCUITest).

Here is an example API Request done using Postman:

![postman_api_call](images/postman_api_call.png)

## Status of the API Run

Using the following API, we can get the status of the Espresso Unit Tests:

```
GET - /api/v1/test-run/{id}/status
```

Here is an example API Request done using Postman:

![postman_api_call_get_status](images/postman_api_call_get_status.png)

## Viewing the Test Execution

We can also view the Execution Live, by following these steps:

1. Login to the SeeTest Cloud UI
2. Navigate to the Execution page:

![test_execution](images/test_execution.png)

## Viewing The Results

In the SeeTest Cloud UI, using the following steps, we can navigate to the SeeTest Reporter where the results are stored:

1. Login to the SeeTest Cloud
2. Click on your Initials > Go To Reporter:

![go_to_reporter](images/go_to_reporter.png)

3. Navigate to Tests tab:

![tests_tab](images/tests_tab.png)

If the execution was recent, it should show up in the list:

![results_list](images/results_list.png)

Otherwise also searching for the test results using the Filter option by searching with "test.run.id" followed with the Execution ID received from the API call:

![filter](images/filter.png)
