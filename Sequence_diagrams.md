# Sequence diagrams

## Login

When a user access to the system, it need to authenticate, so the system can identify and authorize user access.

There are two scenarios identified.
1. The user enter his data (user and password), the user is found and have access to the system.
1. The user enter invalid data, either because the user doesn't exisit nor the user and password don't match, then te user can't login into the system.

### 1. On success

1. The user type his user and password.
1. The gateway receives the data and send to keycloak.
1. Keycloak validates and found the user, it returns a hashcoded token, which will work as credential.
1. The gateway send the cookie to the UI.
1. The UI stores the code in a secure cookie (_HttpOnly_).
1. For any other request, the UI will attach the cookie to the gateway.
1. Gateway will keep the token between request in order to continue the authorization process.

_Note: The TLS and mTLS are configured at infrastructure layer_

![image](./diagrams/sequence_diagram/login-sequence.png)

### On fail

1. The user type his user and password.
1. The gateway receives the data and send to keycloak.
1. Keycloak validates but don't found date (either user doesn't exists or user and password didn't match).
1. The gateway send message to the UI _Invalid User or Password_ or _User not found_ depending on the scenario.
1. UI show message to the user.

![image](./diagrams/sequence_diagram/login-fail-sequence.png)

## Booking

Assuming that:
 - The user is already logged (authenticated and authorized).
 - The user has already searched the event.
 - The user is already at the seat selection screen.


### On success

1. The user cchooses his seats and add his payment data.
1. Send payment information via gateway.
2. Booking microservice 

![image](./diagrams/sequence_diagram/sucess-booking-sequence.png)

### On fail

#### Payment fail