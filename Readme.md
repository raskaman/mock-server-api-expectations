### Mock-server

Mock-server running docker http://127.0.0.1:1080/

Dashboard: http://127.0.0.1:1080/mockserver/dashboard


## MockServer API
https://app.swaggerhub.com/apis/jamesdbloom/mock-server-openapi/5.15.x#/expectation

## info & samples
info https://www.mock-server.com/mock_server/getting_started.html

samples
https://github.com/mock-server/mockserver/blob/master/mockserver-examples/json_examples.md

## Create expectations

```shell
#Run command:
curl -X PUT "http://127.0.0.1:1080/expectation"  -H 'Content-Type: application/x-www-form-urlencoded'  -d  " `cat ./expectations.json`  "
```

## Test
```shell
# run
curl  -w "%{http_code}\n"  http://127.0.0.1:1080/ifnode/1

# expect
/ifnode/1
200

# run
curl  -w "%{http_code}\n"  http://127.0.0.1:1080/ifnode/2

# expect
/ifnode/2
406
```