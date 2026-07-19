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
      |     ├──📂 controller
      |     |  └──📄 BookingController
      |     └──📂 entity
      |        └──📄 BookingRequest
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
               └──📄 PaymentRequest            

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
├── 📂 com
|  ├── 📂 application
|  |    ├── 📂 
|  ├── 📂 domain
|  |    ├── 📂 
|  ├── 📂 infrastructure

──
└──
```

## Events

``` 
├── 📂 com
|  ├── 📂 application
|  |    ├── 📂 
|  ├── 📂 domain
|  |    ├── 📂 
|  ├── 📂 infrastructure

──
└──
```
