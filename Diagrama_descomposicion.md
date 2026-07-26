# Diagrama de descomposición de servicios

## Booking 

``` 
├──📂 com
   ├──📂 application
   |  ├──📂 dto
   |  |  └──📄 BookingResponse
   |  └──📂 usecase
   |     └──📄 BookEventUseCase
   ├──📂 domain
   |  ├──📂 exceptions
   |  |  └──📄 BookingException
   |  ├──📂 model
   |  |  ├──📄 Booking
   |  |  └──📄 BookingStatus
   |  ├──📂 port
   |  |  ├──📄 BookingRespositoryPort
   |  |  ├──📄 NotificationProducerPort
   |  |  └──📄 PaymentHttpClientPort
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |  |  ├──📂 controller
      |  |  |  └──📄 BookingController
      |  |  └──📂 dto
      |  |     ├──📄 BookingRequest
      |  |     └──📄 BookingResposne
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

## Payment

``` 
├──📂 com
   ├──📂 application
   |  ├──📂 dto
   |  |  └──📄 PaymentResponse
   |  └──📂 usecase
   |     └──📄 MakePaymentUseCase
   ├──📂 domain
   |  ├──📂 exception
   |  |  └──📄 PaymentException
   |  ├──📂 model
   |  |  └──📄 Payment
   |  └──📂 port
   |     ├──📄 PaymentRepositoryPort
   |     └──📄 VendorHttpClientPort
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |     ├──📂 dto
      |     |  └──📄 PaymentRequest
      |     └──📂 controrller
      |        └──📄 PaymentController
      └──📂 out 
         ├──📂 db
         |  ├──📂 entity
         |  |  └──📄 PaymentRecord
         |  └──📂 repository
         |     └──📄 PaymentRepositoryAdapter
         └──📂 http
            ├──📂 client
            |   └──📄 VendorClientAdapter
            └──📂 entity
               └──📄 VendorRequest

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
