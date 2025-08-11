The project contains below APIs: 
https://dummyjson.com/auth/login
https://dummyjson.com/products?limit={{limit}}
https://dummyjson.com/carts/add
https://dummyjson.com/products/search?q={{product}}

URL: https://dummyjson.com
Objective: Test both functionality and performance of a public RESTful API simulating a
real online store.

Functional API Testing Tasks:
Login:
Endpoint: POST /auth/login
Validate successful login and token in response.


Get All Products:
Endpoint: GET /products
Validate response time, structure, and pagination.

Add Product to Cart:
Endpoint: POST /carts/add
Validate cart creation and total price.

Negative Test
Try creating a cart with a missing user ID or invalid product ID.

Search Products
Endpoint: GET /products/search?q=laptop
Validate search results and performance.



Note: Below instruction is for windows machine only.

Step 1: Install Postman
Go to the official site: https://www.postman.com/downloads/

Download and install for Windows.

Use Postman GUI to:

Create or import an API collection.

Save/export your collection (.json file).


Step 2: Install Node.js
Newman is a Node.js package, so first install Node.js:

Download from: https://nodejs.org/

Install Node.js (this will also install npm automatically).

Set nodejs path in enviroment variable

Verify installation:
node -v
npm -v

Step 3: Install Newman

npm install -g newman
Check if Newman is installed correctly:
newman -v

Step 4: Export Postman Collection

In Postman:

Open your collection.

Click the three dots (···) ➔ Export ➔ Export as Collection v2.1 (recommended) ➔ Save as API_Test.postman_collection.

Step 5: Run Collection with Newman

Suppose your collection file is saved as D:\API_Test_Postman\API_Test.postman_collection.json.

Then run command:
newman run D:\API_Test_Postman\API_Test.postman_collection.json

Step 6: Generate Reports with Newman

Generate an HTML Report
npm install -g newman-reporter-html

Go to the path where json file is stored (inside API_Test_Postman folder). open cmd and run below command.
Create a report folder inside API_Test_Postman folder to save the generated HTML report.

newman run D:\API_Test_Postman\API_Test.postman_collection.json  --reporters cli,html --reporter-html-export report/report.html
