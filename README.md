# LightBnB

This is a simple application that allows users to search for properties, view property details and make bookings. Users can also add new properties to the database and leave reviews for properties they have stayed at. The application uses PostgreSQL as the database management system and Node.js for the backend.

## Database
 The lightbnb database stores all the data for the application, including information about users, properties, bookings and reviews.

## Tables
The lightbnb database has the following tables:

**Users:** This table stores information about registered users, such as their name, email, and password.

**Properties:** This table stores information about the properties listed on the application, such as the title, description, cost per night, and location details like the country, street, city, province, and post code. It also contains information about the owner of each property.

**Reservations:** This table stores information about reservations made by guests, including the start and end dates of the reservation, the ID of the guest who made the reservation, and the ID of the property being reserved.

**Property_Reviews:** This table stores information about reviews left by guests for properties they have stayed in. It includes details like the rating given by the guest, the ID of the guest who left the review, the ID of the property being reviewed, and the ID of the reservation associated with the review.


## Project Structure

```
.
├── db
│   ├── json
│   └── database.js
├── public
│   ├── javascript
│   │   ├── components 
│   │   │   ├── header.js
│   │   │   ├── login_form.js
│   │   │   ├── new_property_form.js
│   │   │   ├── property_listing.js
│   │   │   ├── property_listings.js
│   │   │   ├── search_form.js
│   │   │   └── signup_form.js
│   │   ├── libraries
│   │   ├── index.js
│   │   ├── network.js
│   │   └── views_manager.js
│   ├── styles
│   │   ├── main.css
│   │   └── main.css.map
│   └── index.html
├── routes
│   ├── apiRoutes.js
│   └── userRoutes.js
├── styles  
│   ├── _forms.scss
│   ├── _header.scss
│   ├── _property-listings.scss
│   └── main.scss
├── .gitignore
├── package-lock.json
├── package.json
├── README.md
└── server.js
```

* `db` contains all the database interaction code.
  * `json` is a directory that contains a bunch of dummy data in `.json` files.
  * `database.js` is responsible for all queries to the database. It doesn't currently connect to any database, all it does is return data from `.json` files.
* `public` contains all of the HTML, CSS, and client side JavaScript. 
  * `index.html` is the entry point to the application. It's the only html page because this is a single page application.
  * `javascript` contains all of the client side javascript files.
    * `index.js` starts up the application by rendering the listings.
    * `network.js` manages all ajax requests to the server.
    * `views_manager.js` manages which components appear on screen.
    * `components` contains all of the individual html components. They are all created using jQuery.
* `routes` contains the router files which are responsible for any HTTP requests to `/users/something` or `/api/something`. 
* `styles` contains all of the sass files. 
* `server.js` is the entry point to the application. This connects the routes to the database.

