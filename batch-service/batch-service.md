# BATCH-SERVICE
This document is the documentation of this service. It was the automation services to support 8excite project. 

### Architecture Diagram
![Architecture Diagram](./images/batch-service-architecture.PNG)

Processors for the batch service will be triggered via RabbitMQ or scheduled by tasker-service with cron jobs.  It will be processed automatically when the specified date time hit.

### Processor Listing

1. applicationBroadcastProcessor
2. brithdayGiftProcessor
3. birthdayGiftreminderProcessor
4. bundleShipmentReminderProcessor
5. campaignGroupBuyProcessor
6. cancelOrderProcessor
7. cancelShipmentProcessor
8. createGroupBuyProcessor
9. createWarehouseBundleShipmentProcessor
10. createWarehouseOrderProcessor
11. groupBuyBotProcessor
12. groupBuyClosingSoonProcessor
13. groupBuyExpirationProcessor
14. groupBuyProcessor
15. newBrandNotificationProcessor
16. newBrandProductNotificationProcessor
17. newCategoryNotificationProcessor
18. orderRatingReminderProcessor
19. productImportProcessor
20. productKeywordProcessor
21. refundOrderOrShipmentProcessor
22. refundOrderProcessor
23. rewardProcessor
24. sendEmailNotificationProcessor
25. sendPushNotificationProcessor
26. takafulReminderProcessor

### Processor Details
#### 1. applicationBroadcastProcessor
##### Description
This processor will broadcast notification to related all users.

##### Flow Diagram
![Application Broadcast Processor](./images/8excite-batch-service%20-%20applicationBroadcaseProcessor.drawio.png)

#### 9. createWarehouseBundleShipmentProcessor
##### Description
This processor will send relevant information to the warehouse service to create the record and it will help update shipment status based on warehouse service response.

##### Flow Diagram
![Create Wahouse Bundle Shipment Processor](./images/8excite-batch-service%20-%20createWarehouseBundleShipmentProcessor.drawio.png)

#### 10. createWarehouseOrderProcessor
##### Description
This processor will send relevant information to the warehouse service to create the record and it will help update shipment status and warehouse status based on warehouse service response.

##### Flow Diagram
![Create Warehouse Order Processor](./images/8excite-batch-service%20-%20createWasehouseOrderProcessor.drawio.png)

#### 19. productImportProcessor
##### Description
This processor will take the product import information to get the file and convert it into an object and store into the database. It will log error if the error come out.

##### Flow Diagram
![Product Import Processor](./images/8excite-batch-service%20-%20productImportProcessor.drawio.png)

#### 23. rewardProcessor
##### Description
This processor will get the reward and forecast the reward to the user based on reward setting.

##### Flow Diagram
![Reward Processor](./images/8excite-batch-service%20-%20rewardProcessor.drawio.png)

#### 24. sendEmailNotificationProcessor
##### Description
This processor will trigger the smtp server and sent the email to the user.

##### Flow Diagram
![Send Email Notification Processor](./images/8excite-batch-service%20-%20sendEmailNotificationProcessor.drawio.png)

#### 25. sendPushNotificationProcessor
##### Description
This processor will trigger the firebase service and sent the notification to the user.

##### Flow Diagram
![Send Push Notification Processor](./images/8excite-batch-service%20-%20sendPushNotificationProcessor.drawio.png)
