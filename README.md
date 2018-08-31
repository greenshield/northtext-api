# NorthText API

API key

  - API key is found under **"Settings"** on the sidebar menu of your dashboard
  - API key must be passed as a POST variable (form field) or query string parameter (URL variable) with each request
  - Variable name must always be **token**

### Examples
Sample API key: **abc123**

#### list groups

GET:

```
https://v1.northtext.com/api/groups/list?token=abc123
```

#### send a single message

GET:
 
```
https://v1.northtext.com/api/message/send?token=abc123&body=testing&to=+16193219876
```

POST: 

```
https://v1.northtext.com/api/message/send
```

field | value
---------- | ----------
token | abc123
body | test message
to | +16193210987

POST (alternative):

```
https://v1.northtext.com/api/message/send?token=abc123
```

field | value
---------- | ----------
body | test message
to | +16193210987

# API endpoints
##### The base URL for all endpoints is
```
https://v1.northtext.com/api
```

#### /message

``
https://v1.northtext.com/api/message
``

Send a single message to one recipient

field | o | type | format
---------- | ---------- | ---------- | ----------
body | **required** | string | 240 characters
to | **required** | string | +1234567890
type | optional | string | marketing \| alert

#### /messages
``
https://v1.northtext.com/api/message
``

Send a message to a group

field | o | type | format
---------- | ---------- | ---------- | ----------
body | **required** | string | 240 characters
groupid | **required** | string | 6D4F558F-3CC8-4A5E-B03D15ED243FAB2A

Each group has a unique ID that can be found on the "Groups" tab of your "Contacts" menu under the "API ID" field.
