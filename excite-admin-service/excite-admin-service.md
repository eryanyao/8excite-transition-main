# EXCITE-ADMIN-SERVICE
This document is the documentation of this service. It was the backend service of the admin management form. 

## Modules
### 1. Product
#### Description
This module allow user create product, update product, view product and delete product. 

### 2. Campaign
#### Description
This module allow user create campaign, update campaign, view campaign and delete campaign. When the campaign create, it will trigger batch service and create new group buy when the campaign is start.

- **Trigger Logic**
![Campaign Trigger Logic](./images/8excite-%20%E2%9C%94%EF%B8%8F%20Group%20buy%20deadline%20scheduler.drawio.png)

#### Flow Diagram
![enter image description here](./images/8excite-%E2%AC%9C%20SH%20-%20Group%20buy%20campaign.drawio.png)

#### List of APIs
- POST /campaigns
- GET /campaigns
- GET /campaigns/{campaignId} 
- PUT /campaigns/{campaignId}
- DELETE /campaigns/{campaignId}

### 3. Group Buy
#### Description
This module allow user view group buy. 

### 4. Inventory
This module will show the flow diagram related with inventory.

#### 4.1 Cancel Order
##### Flow Diagram
![Inventory - Cancel Order](./images/8excite-excite-admin-service%20-%20Inventory%20-%20Cancel%20Order.drawio.png)

The inventory reserved quantity will decrease based on order purchased quantity when order cancel.

##### List of APIs
- PUT /orders/{orderId}/status

#### 4.2 Update Shipment Status to toReceive
##### Flow Diagram
![Inventory - Update Shipment Status](./images/8excite-excite-admin-service%20-%20Inventory%20-%20Update%20Shipment%20Status%20to%20toReceive.drawio.png)

The inventory reserved quantity and physical quantity will be deduct when shipment status updated.

##### List of APIs
- PUT /shipments/{shipmentId}/status

#### 4.3 Product
##### 4.3.1 Add Product
###### Flow Diagram
![Inventory - Product - Add Product](./images/8excite-excite-admin-service%20-%20Inventory%20-%20Add%20Product.drawio.png)

###### List of APIs
- POST /products

##### 4.3.2 Update Product
###### Flow Diagram
![Inventory - Product - Update Product](./images/8excite-excite-admin-service%20-%20Inventory%20-%20Add%20Product.drawio.png)

###### List of APIs
- PUT /products/{productId}

##### 4.3.3 Delete Product
###### Flow Diagram
![Inventory - Product - Delete Product](./images/8excite-excite-admin-service%20-%20Inventory%20-%20Delete%20Product.drawio.png)


###### List of APIs
- DELETE /products/{productId}

## Utils
-