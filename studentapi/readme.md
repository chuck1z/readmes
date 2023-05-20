# User API

### POST /register
Registers a new user in the application.

Request body:
```json
{
  "email": "useremail@example.com",
  "password": "userpassword",
  "phone": "081234567890"
}
```

Response:

201 Created if the user is successfully registered.

Response body:
```json
{
  "message": "User registered",
  "uid": "useruid"
}
```

400 Bad Request if there is an error in the input data.

Response body:
```json
{
  "message": "error message"
}
```
------
### POST /login
Logs a user into the application.

Request body:
```json
{
  "email": "useremail@example.com",
  "password": "userpassword"
}
```

Response:

200 OK if the login is successful.

Response body:
```json
{
  "uid": "useruid",
  "email": "useremail@example.com"
}
```

500 Internal Server Error if there is a server error.

------
### GET /user/{uid}
Retrieves user information based on the uid.

Request parameter:

uid: user uid

Response:

200 OK if the user data is found.

Response body:
```json
{
  "email": "useremail@example.com",
  "phone": "081234567890"
}
```

404 Not Found if the user is not found.

500 Internal Server Error if there is a server error.

------
### POST /logout
Logs out a user from the application.

Response:

200 OK if the logout is successful.

400 Bad Request if there is an error during the logout process.

------
### PUT /edit-profile/{uid}
Updates user profile information based on the uid.

Request parameter:

uid: user uid

Request body:
```json
{
  "email": "newuseremail@example.com",
  "password": "newuserpassword",
  "phone": "081234567891",
  "currentEmail": "olduseremail@example.com",
  "currentPassword": "olduserpassword"
}
```

Response:

200 OK if the profile is successfully updated.

403 Forbidden if the user does not have access to update the profile.

500 Internal Server Error if there is a server error.
