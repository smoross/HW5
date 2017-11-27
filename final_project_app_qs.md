# SI 364 - Final Project questions

## Overall

* **What's a one-two sentence description of what your app will do?**
A user will enter a location/address/POI, and will be directed to a static Google map with the location marked. They will also enter their Instagram username and see the top instagram photos with that location tagged. Information about the location will be sent in an email to the user.

## The Data

* **What data will your app use? From where will you get it? (e.g. scraping a site? what site? -- careful not to run it too much. An API? Which API?)**
My app will retrieve data from the Google maps API, and then the geographic coordinates will be used to search for and retrieve the Instagram data from the Instagram API. 

* **What data will a user need to enter into a form?**
A recognizable location name or address, Instagram handle, and email address.

* **How many fields will your form have? What's an example of some data user might enter into it**
My form will have three fields for the user to input information: an address or location name, their Instagram handle, and their email. An example of data they may enter would be 'The University of Michigan - Ann Arbor' (or an address like '816 South Forest Ave,') '@sammymoross,' and 'smoross@umich.edu.'

* **After a user enters data into the form, what happens? Does that data help a user search for more data? Does that data get saved in a database? Does that determine what already-saved data the user should see?**
If multiple geographic locations are found, they will be listed and then the user can select the correct one. The previously searched locations will be collected in a database to make it easier for a user to look up the same location again. The coordinates retrieved from the Google maps API will be used in order for the user to see the top Instagrams tagged with the same coordinates.

* **What models will you have in your application?**
Location, User, Search 

* **What fields will each model have?** 
Location: Address, Latitude/Longitude, Google static map
User: Email, Instagram handle
Search: Address, Instagram handle, Email  

* **What uniqueness constraints will there be on each table? (e.g. can't add a song with the same title as an existing song)**
The same user can't search for a previously searched location. If a user wants to access information about it, they can look for it the database it is stored in.

* **What relationships will exist between the tables? What's a 1:many relationship between? What about a many:many relationship?**
1:many relationship between user and location, and between user and search because one user can search for multiple locations.
many:many relationship between location and search because the app will search many times for many locations.

* **How many get_or_create functions will you need? In what order will you invoke them? Which one will need to invoke at least one of the others?**
I will need three get_or_create functions: 
1. get_or_create_user
2. get_or_create_location. This function is needed to invoke the get_or_create_location_info function because the search information is based on the input location. 
3. get_or_create_location_info

## The Pages

* **How many pages (routes) will your application have?**
My application will have 7 routes.

* **How many different views will a user be able to see, NOT counting errors?**
6 views not counting errors.

* **Basically, what will a user see on each page / at each route? Will it change depending on something else -- e.g. they see a form if they haven't submitted anything, but they see a list of things if they have?**
Routes:
1. Form that allows user to input address/location/POI, email, and Instagram handle.
2. If multiple locations are found, the user can select the correct one.
3. Google image and map information.
4. Top Instagram images with the location searched for.
5. Error (location not found, etc.)
6. If the same user already searched for this location, they are notified with a link to the database that houses the information. 
7. Database with previously searched locations and the users that searched for them (based on Instagram handle/email).

## Extras

* **Why might your application send email?**
To provide the user with information about the location they searched for.

* **If you plan to have user accounts, what information will be specific to a user account? What can you only see if you're logged in? What will you see if you're not logged in -- anything?**
I don't plan to have user accounts. 

* **What are your biggest concerns about the process of building this application?**
I am mostly concerned if extracting the specific data that I specified is feasbile. Additionally, I struggle with SQL database tables, so I that will be a challenge when building my unique application! 
