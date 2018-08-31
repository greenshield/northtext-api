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
https://v1.northtext.com/groups/list?token=abc123
```

#### send a single message

POST: 

```
https://v1.northtext.com/message/send
```

field | value
---------- | ----------
token | abc123
body | test message
to | +16193210987

POST (alternative):

```
https://v1.northtext.com/message/send?token=abc123
```

field | value
---------- | ----------
body | test message
to | +16193210987

# API endpoints
##### The base URL for all endpoints is
```
https://v1.northtext.com/
```

#### /message

``
https://v1.northtext.com/message
``

Send a single message to one recipient


field |  | type | format
---------- | ---------- | ---------- | ----------
body | **required** | string | 240 characters
to | **required** | string | +1234567890
type | optional | string | marketing \| alert
schedule | optional | timestamp | 2018-12-31 16:30:00 (4:30 PM on 12/31/2018)

#### /messages
``
https://v1.northtext.com/messages
``

Send a message to a group

field |  | type | format
---------- | ---------- | ---------- | ----------
body | **required** | string | 240 characters
groupid | **required** | string | 6D4F558F-3CC8-4A5E-B03D15ED243FAB2A
schedule | optional | timestamp | 2018-12-31 16:30:00 (4:30 PM on 12/31/2018)

Each group has a unique ID that can be found on the "Groups" tab of your "Contacts" menu under the "API ID" field.

#### /group/add
``
https://v1.northtext.com/group/add
``

Add a number to a group

field |  | type | format
---------- | ---------- | ---------- | ----------
phone | **required** | string | +1234567890
groupid | **required** | string | 6D4F558F-3CC8-4A5E-B03D15ED243FAB2A

#### /group/remove
``
https://v1.northtext.com/group/remove
``

Remove a number from a group

field |  | type | format
---------- | ---------- | ---------- | ----------
phone | **required** | string | +1234567890
groupid | **required** | string | 6D4F558F-3CC8-4A5E-B03D15ED243FAB2A

#### /group/create
``
https://v1.northtext.com/group/create
``

Create a new group

field |  | type | format
---------- | ---------- | ---------- | ----------
name | **required** | string | My New Group
accountid | **required** | string | GE4F558F-4CC8-3A5E-B03D15ED243FAB3C
