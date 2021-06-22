# JsonPowerDB
#
#
## Saving user information using POST request
This project is for storing user information using Ajax with integrated JsonPowerDB database.
To create PUT request and do Ajax calls, predefined methods has been used and can be found for reference through the following link - 
http://login2explore.com/jpdb/resources/js/0.0.3/jpdb-commons.js
#
## About JsonPowerDB:
JsonPowerDB is a Real-time, High Performance, Lightweight and Simple to Use, Rest API based Multi-mode DBMS. JsonPowerDB has ready to use API for Json document DB, RDBMS, Key-value DB, GeoSpatial DB and Time Series DB functionality. JPDB supports and advocates for true serverless and pluggable API development.
#
## Benefits of JsonPowerDB
1. Easy to retrieve data in JSON.
2. Very simple to use and schema-free database.
3. Minimal development cost and processing time.
4. Provies low level (raw) form of data and is also human readable.
#
## Release History
![alt text](https://github.com/Ackermann99/ajax-form-jpdb/blob/master/screenshots/log-history.jpeg?raw=true)
#
## JsonPowerDB Dashboard
![alt text](https://github.com/Ackermann99/ajax-form-jpdb/blob/master/screenshots/dashboard.jpeg?raw=t)
#
## Database Example
![alt text](https://github.com/Ackermann99/ajax-form-jpdb/blob/master/screenshots/example-database.jpeg?raw=t)

#
## Saving User Data
```
function saveEmployee() {
    var jsonStr = validateAndGetFormData();
        if (jsonStr === "") {
            return;
        }
    var putReqStr = createPUTRequest("90935976|-31948846640467453|90934156", jsonStr, "SAMPLE", "EMP-REL");
    alert(putReqStr);
    jQuery.ajaxSetup({async: false});
    var resultObj = executeCommandAtGivenBaseUrl(putReqStr, "http://api.login2explore.com:5577", "/api/iml");
    alert(JSON.stringify(resultObj));
    jQuery.ajaxSetup({async: true});
    resetForm();
    }
```

1. Validating user information and storing it as Json String
2. Initialising PUT request using `creatPUTRequest()`, with connection token.
3. Excecuting the PUT request using `executeCommandAtGivenBaseUrl()`, also handles error if occurs.
