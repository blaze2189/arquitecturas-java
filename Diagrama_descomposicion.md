# Diagrama de descomposición de servicios

## Booking 

``` 
├──📂 com
   ├──📂 application
   |  ├──📂 dto
   |  |  ├──📄 BookingCommand
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
   |  |  ├──📄 PaymentCommand
   |  |  └──📄 PaymentResponse
   |  └──📂 usecase
   |     └──📄 MakePaymentUseCase
   ├──📂 domain
   |  ├──📂 exception
   |  |  └──📄 PaymentException
   |  ├──📂 model
   |  |  ├──📄 Payment
   |  |  └──📄 PaymentStatus
   |  └──📂 port
   |     ├──📄 PaymentPubllisherPort
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
         ├──📂 http
         |  ├──📂 client
         |  |   └──📄 VendorClientAdapter
         |  └──📂 dto
         |     └──📄 VendorRequest
         └──📂 queue
            ├──📂 dto
            |  └──📄 NotificationMessage     
            └──📂 producer
               └──📄 NotificationProducer  

```

## Notification

``` 
├──📂 com
   ├──📂 application
   |  ├──📂 dto
   |  |  └──📄 SendEmailCommand
   |  └──📂 usecase
   |     └──📄 SendEmailConfirmationUseCase   
   ├──📂 domain
   |  ├──📂 exception
   |  |  └──📄 EmailException
   |  ├──📂 model
   |  |  ├──📄 Email
   |  |  └──📄 NotificationStatus
   |  └──📂 port
   |     ├──📄 EmailServerPort
   |     ├──📄 NotificationProducerPort
   |     └──📄 NotificationRepositoryPort
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 queue
      |     ├──📂 entity
      |     |   └──📄 NotificationMessage
      |     └──📂 consumer
      |        └──📄 NotificationConsusmer
      └──📂 out 
         └──📂 queue
         |  ├──📂 dto
         |  |   └──📄 NotificationMessage
         |  └──📂 produccer
         |     └──📄 BookingProducerAdapter
         └──📂 sender
            ├──📂 dto
            |   └──📄 EmailRequest
            └──📂 produccer
               └──📄 EmailSenderAdapter

```


## Events

``` 
├──📂 com
   ├──📂 application
   |  ├──📂 dto
   |  |  └──📄 EventCommand
   |  └──📂 usecase
   |     ├──📄 GetEventCapacityUseCase
   |     ├──📄 SearchEventUseCase
   |     ├──📄 SearchActiveEventUseCase
   |     └──📄 UpdateEventUseCase
   ├──📂 domain
   |  ├──📂 exception
   |  |  └──📄 EventException
   |  ├──📂 model
   |  |  └──📄 Event
   |  └──📂 port
   |     └──📄 EventRepositoryPort
   └──📂 infrastructure
      ├──📂 in
      |  └──📂 http
      |     ├──📂 controller
      |     |  └──📄 EventController
      |     └──📂 dto
      |        └──📄 EventRequest
      └──📂 out 
         └──📂 db
         |  ├──📂 entity
         |  |  └──📄 EventRecord
         |  └──📂 repository
         |     └──📄 EventRepositoryDBAdapter   
         └──📂 cache
         |  ├──📂 entity
         |  |  └──📄 EventCacheRecord
         |  └──📂 repository
         |     └──📄 EventRepositoryCacheAdapter 
         └──📂 repository
            ├──📂 entity
            |  └──📄 EventRecord
            └──📂 repository
               └──📄 EventRepositoryAdapter     

```