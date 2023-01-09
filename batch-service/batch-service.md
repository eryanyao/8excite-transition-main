# BATCH-SERVICE
This document is the documentation of this service. It was the automation services to support 8excite project. 

### Architecture Diagram
![Architecture Diagram](./images/batch-service-architecture.PNG)

Processors for the batch service will be triggered via RabbitMQ or scheduled by tasker-service with cron jobs. It will be processed automatically when the specified date time hit.

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

#### 5. campaignGroupBuyProcessor
##### Description
This processor will update the status of the tasker through rabbitMQ and trigger the create group buy processor.

##### Flow Diagram
![Campaign Group Buy Processor](./images/8excite-batch-service%20-%20campaignGroupBuyProcessor.drawio.png)

#### 6. cancelOrderProcessor
##### Description
This processor will cancel order when payment end at hit and order status = pending.

##### Flow Diagram
![Cancel Order Processor](./images/8excite-batch-service%20-%20cancelOrderProcessor.drawio.png)

#### 7. cancelShipmentProcessor
##### Description
This processor will cancel shipment when payment end at hit and order status = pending.

##### Flow Diagram
![Cancel Shipment Processor](./images/8excite-batch-service%20-%20cancelShipmentProcessor.drawio.png)

#### 8. createGroupBuyProcessor
##### Description
This processor will create group buy based on campaign information.

##### Flow Diagram
![Create Group Buy Processor](./images/8excite-batch-service%20-%20createGroupBuyProcessor.drawio.png)

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

#### 11. groupBuyBotProcessor
##### Description
This processor will update group buy current quantity and ops user.

##### Flow Diagram
![Group Buy Bot Processor](./images/8excite-batch-service%20-%20groupBuyBotProcessor.drawio.png)

#### 12. groupBuyClosingSoonProcessor
##### Description
This processor will send notification when group buy closing soon.

##### Flow Diagram
![Group Buy Closing Soon Processor](./images/8excite-batch-service%20-%20groupBuyClosingSoonProcessor.drawio.png)

#### 13. groupBuyExpirationProcessor
##### Description
This processor will process pending top up orders when top up end at hit based on order with related group buy id.

##### Flow Diagram
![Group Buy Expiration Processor](./images/8excite-%E2%9C%94%EF%B8%8F%2020221025%20-%20End%20group%20buy%20(topup)%20expiration%20processor.drawio.png)

#### 14. groupBuyProcessor
##### Description
This processor will process floating orders when payment end at hit based on order with related group buy id.

##### Flow Diagram
![Group Buy Processor](./images/8excite-batch-service%20-%20groupBuyProcessor.drawio.png)

#### 17. newCategoryNotificationProcessor
##### Description
This processor will trigger push notification processor when new category created.

##### Flow Diagram
![New Category Notification Processor](./images/8excite-%E2%9C%94%EF%B8%8F%2020221028%20-%20New%20category%20notification%20processor.drawio.png)

#### 19. productImportProcessor
##### Description
This processor will take the product import information to get the file and convert it into an object and store into the database. It will log error if the error come out.

##### Flow Diagram
![Product Import Processor](./images/8excite-batch-service%20-%20productImportProcessor.drawio.png)

#### 20. productKeywordProcessor
##### Description
This processor will get the available product's keywords and updating the product keyword records.

##### Flow Diagram
![Product Keyword Processor](./images/8excite-batch-service%20-%20productKeywordProcessor.drawio.png)

#### 21. refundOrderOrShipmentProcessor
##### Description
This processor will refund order or shipment.

##### Flow Diagram
![Refund Order Or Shipment Processor](./images/8excite-batch-service%20-%20refundOrderOrShipmentProcessor.drawio.png)

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
