# Diagrama de descomposición de servicios

## Booking 

``` 
├──📂 com
   ├──📂 application
   |  └──📄 BookingService
   ├──📂 domain
   |  └──📂 use.case
   |     └──📄 BookEvent
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |  |  ├──📂 controller
      |  |  |  └──📄 BookingController
      |  |  └──📂 entity
      |  |     └──📄 BookingRequest
      |  └──📂 queue
      |     ├──📂 entity
      |     |  └──📄 BookingMessage            
      |     └──📂 sender
      |        └──📄 BookingConsumer 
      └──📂 out 
         ├──📂 db
         |  ├──📂 entity
         |  |  └──📄 BookingRecord
         |  └──📂 repository
         |     └──📄 BookingRepository
         ├──📂 http
         |  ├──📂 client
         |  |   └──📄 PaymentClient
         |  └──📂 entity
         |     └──📄 PaymentRequest
         └──📂 queue
            ├──📂 entity
            |  └──📄 NotificationMessage            
            └──📂 sender
               └──📄 NotificationProducer           

──
└──
```

## Payment

``` 
├──📂 com
   ├──📂 application
   |  └──📄 PaymentService
   ├──📂 domain
   |  └──📂 use.case
   |     └──📄 MakePayment
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |     ├──📂 controller
      |     |  └──📄 PaymentController
      |     └──📂 entity
      |        └──📄 PaymentRequest
      └──📂 out 
         ├──📂 db
         |  ├──📂 entity
         |  |  └──📄 PaymentRecord
         |  └──📂 repository
         |     └──📄 PaymentRepository
         └──📂 http
            ├──📂 client
            |   └──📄 VendorClient
            └──📂 entity
               └──📄 VendorRequest

──
└──
```

## Notification

``` 
├──📂 com
   ├──📂 application
   |  └──📄 EmailNotificationService
   ├──📂 domain
   |  └──📂 use.case
   |     └──📄 SendEmailConfirmation
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 queue
      |     ├──📂 entity
      |     |   └──📄 NotificationMessage
      |     └──📂 consumer
      |        └──📄 NotificationConsusmer
      └──📂 out 
         └──📂 queue
            ├──📂 entity
            |   └──📄 NotificationMessage
            └──📂 consumer
               └──📄 NotificationConsusmer

──
└──
```

## Events

``` 
├──📂 com
   ├──📂 application
   |  └──📄 BookingService
   ├──📂 domain
   |  └──📂 use.case
   |     ├──📄 GetEventCapaccity
   |     ├──📄 SearchEvent
   |     ├──📄 SearchActiveEvent
   |     └──📄 UpdateEventBooking
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |  |  ├──📂 controller
      |  |  |  └──📄 EventController
      |  |  └──📂 entity
      |  |     └──📄 EventRequest
      |  └──📂 queue
      |     ├──📂 entity
      |     |  └──📄 BookingMessage            
      |     └──📂 sender
      |        └──📄 BookingConsumer 
      └──📂 out 
         ├──📂 db
         |  ├──📂 entity
         |  |  └──📄 BookingRecord
         |  └──📂 repository
         |     └──📄 EventRepository
         └──📂 queue
            ├──📂 entity
            |  └──📄 NotificationMessage            
            └──📂 sender
               └──📄 NotificationProducer      
──
└──
```
