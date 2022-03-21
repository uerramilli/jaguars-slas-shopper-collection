Useful SLAS Shopper API calls.
Download SLAS Jaguars Shopper API Usage.postman_collection.json collection and import into Postman workspace.

Useful Docs:

https://developer.salesforce.com/docs/commerce/commerce-api/references?meta=shopper-login:Summary

https://developer.salesforce.com/docs/commerce/commerce-api/guide/auth-z-scope-catalog.html


To make this solution work for your Commerce Cloud Sandbox, do the following:
1. Update shortCode, OrganizationID & ClientID prop per your env on the collection
2. API ClientID used for testing: 46f446f3-539c-45f6-aee4-32a8cecdd14c. Clone this API client to create new one for you
3. Create a shopper account on your SFRA storefront site. The following credentials are used to generate registered customer JWT. 
   - Username:legend@sleepyhollow.com
   - Password:!20Summer

Sequence of SLAS calls to create an order for a guest user in your sandbox:
1. Run 1a. Authorize Guest
2. Run 1c. Token - Copy Code & USID from 1a/1b response header Location field
3. Run 5a: Post Shopper Basket - Create
4. Run 6a: Post Shopper Order - Create

Note: If run into CustomerBasketsQuotaExceededException - The maximum number of baskets per customer was exceeded, then 
run 5c: Delete Shopper Basket - Delete 
