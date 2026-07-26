# Diagrama de descomposición de servicios

## Booking 

``` 
├──📂 com
   ├──📂 application
   |  ├──📂 dto
   |  |  └──📄 Book
   |  └──📂 use_case
   |     └──📄 BookEvent
   ├──📂 domain
   |  ├──📂 Exceptions
   |  |  ├──📄 BookingException
   |  |  ├──📄 NotificationException
   |  |  └──📄 PaymentException
   |  ├──📂 model
   |  |  └──📄 Booking
   |  |  ├──📄 Notification
   |  |  └──📄 Payment
   |  ├──📂 port
   |  |  ├──📄 BookingConsumerPort
   |  |  ├──📄 BookingRespositoryPort
   |  |  ├──📄 NotificationProducerPort
   |  |  └──📄 PaymentRequestPort
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |  |  ├──📂 controller
      |  |  |  └──📄 BookingController
      |  |  └──📂 dto
      |  |     └──📄 BookingRequest
      |  └──📂 queue
      |     ├──📂 dto
      |     |  └──📄 BookingMessage            
      |     └──📂 listener
      |        └──📄 BookingConsumerAdapter 
      └──📂 out 
         ├──📂 db
         |  ├──📂 entity
         |  |  └──📄 BookingRecord
         |  └──📂 repository
         |     └──📄 BookingRepositoryAdapter
         ├──📂 http
         |  ├──📂 client
         |  |   └──📄 PaymentClient
         |  └──📂 dto
         |     └──📄 PaymentRequestAdapter
         └──📂 queue
            ├──📂 dto
            |  └──📄 NotificationMessage     
            └──📂 producer
               └──📄 NotificationProducer           

```

```
com
├── application
│   ├── dto
│   │   ├── EventResponse
│   │   └── SearchEventQuery
│   └── usecase
│       ├── GetEventCapacityUseCase
│       ├── SearchEventUseCase
│       ├── SearchActiveEventUseCase
│       └── UpdateEventBookingUseCase
├── domain
│   ├── exception
│   │   └── EventNotFoundException
│   ├── model
│   │   ├── Event
│   │   ├── EventId
│   │   └── SeatCapacity
│   └── port
│       ├── EventRepositoryPort
│       └── NotificationPublisherPort
└── infrastructure
    ├── in
    │   ├── http
    │   │   ├── dto
    │   │   │   └── EventRequest
    │   │   └── EventController
    │   └── queue
    │       ├── dto
    │       │   └── BookingMessage
    │       └── listener
    │           └── BookingConsumer
    └── out
        ├── db
        │   ├── entity
        │   │   └── EventEntity
        │   ├── mapper
        │   │   └── EventEntityMapper
        │   └── repository
        │       ├── SpringDataEventRepository
        │       └── EventRepositoryAdapter  <-- (Implementa EventRepositoryPort)
        └── queue
            ├── dto
            │   └── NotificationMessage
            └── publisher
                └── NotificationProducer  <-- (Implementa NotificationPublisherPort)
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

```
