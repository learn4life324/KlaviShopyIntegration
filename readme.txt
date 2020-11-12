This NodeJS app interact with Shopify API to reterieve Orders and Placed orders data and submit over to Klaviyo application.

Shopify API end point : https://success-engineering.myshopify.com//admin/api/2020-10/orders.json?status=any
Klaviyo endpoint: https://a.klaviyo.com/api/track?api_key=pk_85d0a1bb1bca774e057f32c4222c4bfc2f&data=<base64 encoded data>

Procedure:
1. Create a directory for your project, cd into the directory and initialize a Node project with default settings:
  $ npm init -y
  This will create a package.json file in the directory. 

2. Install node-fetch as shown below and add an fetchAPI.js file
    $ npm install node-fetch 
    node-fetch is a lightweight module that enables us to use the fetch() function in NodeJS, with very similar functionality as window.fetch() in native JavaScript.

3. Add the content from fetchAPI.js( attached with this project) to newly created empty file.
4. Run the program with command as shown below:- 
    node fetchAPI.js


Overview & Results:

1. Placed Order metrics and order placed metrics API's are called in a loop 
2. Payload for each of the metrics is built on the run with data from shopify API call.
3. The payload is then encoded with base64 and sent over to Klaviyo
4. Constants are used to handle constant data
5. Three functions are added as such:
  a. setInterval(() => { apiFunctionCall(urlForAllOrders) }, 60 * 30000); //this part to schedule this call after every 30 mins
  b. apiFunctionCall(urlForAllOrders); // api call for all orders irrespective of time date contraints
  c. apiFunctionCall(urlForLast30MinsOrders); // api call for all orders from the last 30 mins 


  

