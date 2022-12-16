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
![enter image description here](./images/8excite-%20%E2%9C%94%EF%B8%8F%20Group%20buy%20deadline%20scheduler.drawio.png)

#### Flow Diagram
![enter image description here](./images/8excite-%E2%AC%9C%20SH%20-%20Group%20buy%20campaign.drawio.png)

#### List of APIs
- POST /campaigns
- GET /campaigns
- GET /campaigns/{campaignId} 
- PUT /campaigns/{campaignId}
- DELETE /campaigns/{campaignId}

### 3. Group Buy

## Utils