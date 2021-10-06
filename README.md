Marketplace-style API

Features browsing products, registering users, posting new listings and editing/removing those listings. Uses Basic authentication, with passwords being encrypted with bcrypt. Data validation is used when adding users or listings. Mocha testing is present, but not completely efficient.

Postman formats: Use raw data, json POST /register :

{ "fName": "", "lName": "",
"email": "", "mobileNumber": , "username": "", "password": "" }

Use form-data with 'image' as files, required fields below POST /item/add :

name, description, price, location, category, delivery, image (format: files)

Requires you to enter all fields again. Seems like only raw data works for this, so use that PUT /item/modify/:id

{ "name": "", "description": "" , "location": "", "category": "", "delivery": "", "price": "" }


If you do the mocha tests make sure to comment out the app.server command, else it will run two at once. Then open cmd and navigate to the folder '/apiTest' and use npx mocha.

Stoplight site (should be public):
https://t8leos.stoplight.io/studio/shopping
