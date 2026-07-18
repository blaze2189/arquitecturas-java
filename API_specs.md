# API Endpoints

**Base path:** /api/v1

## Event

### Get Active Events
---
- **TYPE:** GET
- **PATH:** getAvailable

- __BODY RESPONSE:__ 

On success
```json
{
    "eventId":"integer",
    "eventName":"string",
    "date":"string",
    "locationId":"integer",
    "locationName":"string"
}
```

On error
```json
{
    "code":"integer",
    "error":"string",
    "message":"string"
}
```

### Get Event Capacity
---
- **TYPE:** GET
- **PATH:** event/{evetnId}/capacity
- __BODY RESPONSE:__ 

On success
```json
{
    "eventId":"integer",
    "eventName":"string",
    "actuallCapacity":"integer",
    "currentCapacity":"integer"
}
```

On error
```json
{
    "code":"integer",
    "error":"string",
    "message":"string"
}
```
## Booking

- **TYPE:** POST
- **PATH:** bookEvent
- **BODY REQUEST:** 
```json
{
    "seats":["string"],
    "event":{
        "id":"integer",
        "name":"string",
        "userId":"integer",
        "userEmail":"string",
        "status":"string"
    },
    "paymentInformation":{
        "holderName": "string",
        "cardNumber": "string",
        "cvv": "string"
    }
}
```
- __BODY RESPONSE:__ 
```json
{
    "status:":"string",
    "message":"string",
    "reason":"string",
    "code": "integer"
}
```


## Payment

- **TYPE:** POST
- **PATH:** makePayment
- **Body:** 
```json
{
    "transactionId": "string",
    "holderName": "string",
    "cardNumber": "string",
    "cvv": "string"
}
```
- __Response:__ 
```json
{
    "status:":"string",
    "reason":"string",
    "code": "integer"
}
```
