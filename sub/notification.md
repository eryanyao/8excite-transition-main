#  NOTIFICATION TEMPLATE

||Group|Event|Notification Type|Trigger On|Target Audience|
|---|---|---|---|---|---|
|1|**Marketing**|Referee Sign Up|**signupReferralReward**|New joiner sign up through referral link + activated account|Referral|
|2||Main Campaign Shoutout|||All|
|3||Category Campaign Shoutout|||All|
|4||Referral Campaign Shoutout|||All|
|5||New Brand onboarded|**newBrand**|New brand added and at least 3 products listed to the app|All|
|6||New Category Added|**newCategory**|New category added and at least 5 products listed to the app|All|
|7||New Product Listed for Followed Brand|**newBrandProduct**|New product(s) added to a brand|Member(s) who followed the brand|
|8||Product recommendation||Product recommendation based on selected area of interest + purchase history + wishlist + recent browse history|All (Personalized)|
||
|9|**Order/Sales**|Wishlist Item Group Closing Soon|**wishlistGroupBuyClosingSoon**|"The product added to the wishlist almost hitting target (less than 5 items left) or closing soon (less than 24 hours).<br/>Targeted product has not been purchased within last 4 weeks<br/>Targeted product has not send any notification out within 48 hours" |Member(s) who added the targeted product to wishlist|
|10||Watchlist Item Group Closing Soon||The product was added to the watchlist almost hitting target (less than 5 items left) or closing soon (less than 24 hours).|Member(s) who added the targeted product to watchlist|
|11||Joined Group Closing Soon|**groupBuyClosingSoon**|"Group Thread(s) that has not trigger this notification type and is meeting minimally one of the condition below:<br/> 1. Group Thread close to hitting target (less than 5 items left)<br/>2. Group Thread is closing soon (less than 24 hours)"|Member(s) who joined the targeted group thread
|12||Joined Group Successfully Complete Mission|**groupBuyPurchaseSuccessful**|Group Thread(s) successfully meet target quantity|Member(s) who joined the targeted group thread
|13||Joined Group Fail to Complete Mission|**groupBuyPurchaseFailed**|Group Thread(s) reach end time but not able to meet target quantity|Member(s) who joined the targeted group thread
|14||Order is cancelled and refunded successfully|**orderRefund**|"1. Order that is being cancelled by member when group thread fail to complete mission, and amount is refunded<br/>2. Order that is being cancelled in the middle of active group thread, and amount has been refunded<br/>3. Order that has been cancelled and refunded manually"|Member of the targeted order
||
|15|**Shipment**|Order(s) that is in warehouse and ready to be shipped, and notification has not been sent yet|**orderStatusUpdates**|Order(s) that is in warehouse and ready to be shipped, and notification has not been sent yet|Member for the targeted order
|16||Order Status Update - Item has been delivered|**shipmentStatusUpdates**|Order(s) newly delivered to member, and notification has not been sent yet|Member for the targeted order
|17||Provide Rating for received Order|**orderRatingReminder**|Order(s) delivered more than 1 day, not receive rating, and notification has not been sent yet|Member for the targeted order
|18||You still have item(s) in warehouse. Please arrange shipment asap|**bundleShipmentReminder**|Order(s) in warehouse that's 1 week remaining for free storage|Member for the targeted order|
|19||One or more of your item(s) in warehouse will be charged for storage fee||Order(s) in warehouse that exceed free storage duration|Member for the targeted order|
|20||Shipping order is cancelled and refunded successfully|**shipmentRefund**|Shipment refund has been processed successfully.|Member of the targeted order|
||
|21|**Customer Service**|New message from customer service|**newChatMessage**|Message sent by customer service|Member receiving the message|
||
|22|**Loyalty**|Point Award upon order successfully delivered|**pointAward**|Order delivered|Member for the targeted order
|23||Congratulation on First Purchase (with voucher given)||First Group Buy success for each member|Member for the targeted order
|24||Birthday gift||Member's Birthday month|Member for Birthday Month
|25||Referree First Purchase|**refereeFirstPurchaseReward**|First Group Buy success for referee|Referral
|26||Birthday greetings||Member's Birthday|Birthday Member
|27||Group Leader success mission reward||
|28||Group Leader Leaderboard reward||
|29||Top Spender Leaderboard reward||
|30||Experience Point reward||
|31||Point Balance Summary||
||
|32|**Security**|Login at another device detected||When the app detects login at another device while the app at the current device is logged in using the same account.|Owner of the user account.|
||
|33|**Social**|Your friend has accepted you as a friend
|34||Someone woulikd like to add you as friend (friend invitation)
|35||You have received message from friend
|36||You have been invited to join a circle
|37||Someone has joined your circle
|38||Your friend has invited you to jointly purchase the product
|39||Your friend(s) joined you for group buy
|||
|40|**General**|New app version available for download||When a new app version is available for download.|All users which are still using older app versions.
|||
||**Other**
