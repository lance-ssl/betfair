[![Build Status](https://travis-ci.org/LiamPa/betfairlightweight.svg?branch=master)](https://travis-ci.org/LiamPa/betfairlightweight)

# betfairlightweight

Lightweight, super fast python wrapper for Betfair API-NG allowing all betting operations (including market and order streaming) and some account operations.

# setup

Add your certificates to '/certs/' and app_key to environment variables with username as key before installing.

.bash_profile
```
# betfair
export username = "appkey"
```

The library can then be used as follows:

```python
import betfairlightweight

trading = betfairlightweight.APIClient('username', 'password')

trading.login()
```


```python
event_types = trading.list_event_types()
```

event_types is a list of classes containing data.

# todo

    - Complete unit tests
    - Market and Order streaming added, need further tests
    - Fix issue with no errorCode in cancel request (details sent to bdp@betfair.com)
    - Use schematics for json -> data structure, schematics is slow as balls (0.3s+ for 300 marketBook request)
    - Enums for correct values to be sent
    - Choose where certs are located
    - Thread lock on transaction counter
