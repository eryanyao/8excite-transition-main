# EXCITE-SERVICE
This document is the documentation of this service. It was the backend services of the 8excite+ application.  Includes all user interactions while performing steps in the 8excite+ app.

## Architecture Diagram
![Architecture Diagram](./images/8excite-Architecture%20Diagram.drawio.png)

---
## Modules
### 1. Product
#### Description
This module will trigger when user interact with product. It only including read feature. Will return single product detail or a list of products.

- **Product Type**:
	- **Simple product** - normal product 
	- **Variation product** - product having variations (variations field length > 0)
	- **Bundle product** - can bundled with simple product or variation product (products field length > 0 AND isBundle field = true)
	- **Free gift product** - product cannot be purchased (isFree field = true)

#### 1.1 Get Product Listing	
##### Flow Diagram
![Get Product Listing](./images/8excite-excite-service%20-%20Get%20Product%20Listing.drawio.png)

Banner filter will based on the record return by banner. It will updating the filter element provided. For example, banner filter by brand, it will update the brandIds before get the product.

##### List of APIs
- GET /products

#### 1.2 Get Product Listing	
##### Flow Diagram

![Get Product Detail](./images/8excite-excite-service%20-%20Get%20Product%20Detail.drawio.png)

##### List of APIs
- GET /products/{productId} 

### 2. Group Buy
#### Description
#### Flow Diagram
#### Detailed Flow Diagram
#### List of APIs
- GET /groupBuys
- GET /groupBuys/{groupBuyId} 

### 3. Order
Order related apis, including group buy calculator and checkout.

#### 3.1 Single Group Buy Calculator 
##### Description
This module will trigger when user checkout with group buy product. It will calculate user cart product with voucher and 8excite point. User can select the payment method they prefer. After calculated, user will get the total amount that need to pay. 

##### Flow Diagram
![enter image description here](./images/8excite-excite-service%20-%20Single%20Group%20Buy%20Calculator.drawio.png)

##### List of APIs
- POST /calculator/checkout/groupBuys/summary

#### 3.2 Single Group Buy Checkout
##### Description
This module will trigger when user checkout with group buy product after single group buy calculator. It will generate order based on the calculator result.

##### Flow Diagram
![enter image description here](./images/8excite-20221014-Createorjoingroupbuy.png)

##### List of APIs
- POST /user/orders

#### 3.3 Multi Group Buy Calculator
##### Description
This module will trigger when user checkout with multiple group buy product. It allow user add their interesting group buy product into watchlist first, then checkout. Before checkout, it will calculate the final amount based on user input (voucher, 8excite point, etc).

##### Flow Diagram
![enter image description here](./images/8excite-excite-service%20-%20Multi%20Group%20Buy%20Calculator.drawio.png)

##### List of APIs
- POST /v2/calculator/checkout/summary

#### 3.4 Multi Group Buy Checkout
##### Description
This module will trigger when user checkout with multiple group buy product after multi group buy calculator. It will generate order based on the calculator result.

##### Flow Diagram
![enter image description here](./images/8excite-excite-service%20-%20Multi%20Group%20Buy%20Checkout.drawio.png)

#### 3.5 Group Buy Top Up Calculator
##### Description
This module will trigger when user checkout with pending topup group buy orders.

##### Flow Diagram
![Group Buy Top Up Calculator](./images/8excite-excite-service%20-%20Top%20Up%20Group%20Buy%20Calculator.drawio.png)

##### List of APIs
- POST /v2/calculator/checkout/groupBuys/{groupBuyId}/topup/summary 

#### 3.6 Group Buy Top Up Checkout

##### Description
This module will trigger after group buy top up calculator.

##### Flow Diagram
![Group Buy Top Up Checkout](./images/8excite-excite-service%20-%20Top%20Up%20Group%20Buy%20Checkout.drawio.png)

##### List of APIs
- POST /v2/user/groupBuys/{groupBuyId}/topup 

### 4. Warehouse
This api will show the item that to be bundle.

#### Flow Diagram
![enter image description here](./images/8excite-excite-service%20-%20Get%20Warehouse%20Items.drawio.png)

Only show in stock warehouses related by user.

#### List of APIs
- GET /user/warehouse/items

### 5. Bundle Shipment
Only shipment method = bundle will be create. 

#### 5.1 Shipment checkout calculator
##### Flow Diagram
![Shipment Checkout Calculator](./images/8excite-excite-service%20-%20Shipment%20Checkout%20Calculator.drawio.png)

##### List of APIs
- POST /calculator/checkout/shipments/summary

#### 5.2 Shipment checkout
##### Flow Diagram
![Shipment Checkout](./images/8excite-excite-service%20-%20Shipment%20Checkout.drawio.png)

##### List of APIs
- POST /user/shipments

### 6. Inventory
##### Description
This flowchart will show the inventory changes when the group buying order is created.

##### Flow Diagram
![Inventory Group Buy Order](./images/8excite-excite-service%20-%20Inventory%20-%20Group%20Buy%20Order.drawio.png)

### 7. Reward
#### 7.1 Reward Handler Command 
##### List of Rewards
1. userReferral
2. refereeFirstPurchase
3. signUp
4. topUpGroupBuyOrderReward
5. orderReward
6. shipmentReward

##### List of Functions
1. processUserReferralReward
2. processRefereeFirstPurchaseReward
3. reprocessRefereeFirstPurchaseReward
4. processSignUpReward
5. processTopUpGroupBuyOrderReward
6. processOrderReward
7. processShipmentReward

##### Order Reward/Shipment Reward
###### Flow Diagram
![Order Reward/Shipment Reward](./images/8excite-excite-service%20-%20Reward%20Command%20Handler%20-%20Order%20Reward%20And%20Shipment%20Reward.drawio.png)



---

## Utils
### 1. Google Address
#### 1.1 Get City
##### Flow Chart
![Google Address - Get City](./images/8excite-Utils%20-%20Google%20Address%20-%20Get%20City.drawio.png)

Get the address from google map api. For the city will having different object name, this function will be based on city's object name, to return the correct city name.

#### 1.2 Unwrap Address Component
##### Flow Chart
![Google Address - Unwrap Address Component](./images/8excite-Utils%20-%20Google%20Address%20-%20Unwrap%20address%20component.drawio.png)

Unwrap the address component passed from google.

### 2. Redeem Point Calculator
#### 2.1 Calculate Summary
##### Flow Chart
![Redeem Point Calculator - Calculate Summary](./images/8excite-Utils%20-%20Redeem%20Point%20Calculator%20-%20Calculate%20Summary.drawio.png)

### 3. Order
#### 3.1 Order Comparision Sort
##### Flow Chart
![Redeem Point Calculator - Calculate Summary](./images/8excite-Utils%20-%20Order%20-%20Order%20Comparison.drawio.png)

Order comparison will compare the order within
- product
- group buy
- shipping method
- logistic
- address, all detail must be same
- is the product having same variation
- is the product having bundle, the bundle same, having same bundle item variation?