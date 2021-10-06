Marketplace-style API

Features browsing products, registering users, posting new listings and editing/removing those listings. Uses Basic authentication, with passwords being encrypted with bcrypt. Data validation is used when adding users or listings. Mocha testing is present, but not completely efficient.

All commands (* = require login):
GET /all
GET /search/category/{category}
GET /search/id/{itemID}
GET /search/location/{location}
POST /register
POST /item/add *
PUT /item/modify/{itemID} *
DELETE /item/delete/{itemID} *

Postman formats: Use raw data, json. Note that mobileNumber is a number, the rest are strings. 
POST /register :
{ 
"fName": "", 
"lName": "",
"email": "", 
"mobileNumber": , 
"username": "", 
"password": "" 
}


Here, use form-data with 'image' as files and the rest as text
POST /item/add
name, description, price, location, category, delivery, image (format: files)

Requires you to enter all fields again. Seems like only raw data works for this, so use that 
Item ID can be found on /all or /search, but please note there's are user ID there.
PUT /item/modify/:id
{ 
  "name": "", 
  "description": "" , 
  "location": "", 
  "category": "", 
  "delivery": "", 
  "price": "" 
}


If you do the mocha tests make sure to comment out the app.server command, else it will run two at once. Then open cmd and navigate to the folder '/apiTest' and use npx mocha.
Branch 'localserver' should make doing these tests easier.

Stoplight site (should be public):
https://t8leos.stoplight.io/studio/shopping

Heroku site:
https://heroku-shopping-app.herokuapp.com/

Swagger generated client API can be found in GeneratedAPIClient folder.
