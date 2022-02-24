# Book-Browser


As you can see in the following animation, a user can type a search term (in this case, "star wars") in a search box and the results appear:

![](21-mern-homework-demo-01.gif)

The user can save books by clicking "Save This Book!" under each search result, as shown in the following animation:


![](21-mern-homework-demo-02.gif)

A user can view their saved books on a separate page, as shown in the following animation:


![](21-mern-homework-demo-03.gif)



## User Story
AS AN avid reader
I WANT to search for new books to read
SO THAT I can keep a list of books to purchase


## Acceptance Criteria

- []    GIVEN a book search engine
        WHEN I load the search engine
        THEN I am presented with a menu with the options Search for Books and Login/Signup and an input field to search for books and a submit button           

- []    WHEN I click on the Search for Books menu option
        THEN I am presented with an input field to search for books and a submit button

- []    WHEN I am not logged in and enter a search term in the input field and click the submit button
        THEN I am presented with several search results, each featuring a book’s title, author, description, image, and a link to that book on the Google Books site

- []    WHEN I click on the Login/Signup menu option
        THEN a modal appears on the screen with a toggle between the option to log in or sign up  

- []    WHEN the toggle is set to Signup
        THEN I am presented with three inputs for a username, an email address, and a password, and a signup button    
            
- []    WHEN the toggle is set to Login
        THEN I am presented with two inputs for an email address and a password and login button

- []    WHEN I enter a valid email address and create a password and click on the signup button
        THEN my user account is created and I am logged in to the site 

- []    WHEN I enter my account’s email address and password and click on the login button
        THEN I the modal closes and I am logged in to the site

- []    WHEN I am logged in to the site
        THEN the menu options change to Search for Books, an option to see my saved books, and Logout
            
- []    WHEN I am logged in and enter a search term in the input field and click the submit button
        THEN I am presented with several search results, each featuring a book’s title, author, description, image, and a link to that book on the Google Books site and a button to save a book to my account  

- []    WHEN I click on the Save button on a book
        THEN that book’s information is saved to my account   

- []    WHEN I click on the option to see my saved books
        THEN I am presented with all of the books I have saved to my account, each featuring the book’s title, author, description, image, and a link to that book on the Google Books site and a button to remove a book from my account  

- []    WHEN I click on the Remove button on a book
        THEN that book is deleted from my saved books list   
            
- []    WHEN I click on the Logout button
        THEN I am logged out of the site and presented with a menu with the options Search for Books and Login/Signup and an input field to search for books and a submit button   


## Getting Started:


- []    GraphQL API   

- []    auth.js update auth middleware to work with GraphQL 

- []    server.js implement apollo server and apply it to the express server as middleware   
            
- []    Run npm install apollo-server-express@2.15.0 to install apollo server 2 (Or maybe upgrade? to apollo 3)

## `Schemas` Directory:

-[]     `index.js` -- export your typeDefs and resolvers  
        
-[]     `resolvers.js` -- Define the query and mutation functionality to work with mongoose models. user-controller.js can be a guide

-[]    `typeDefs.js` -- define the necessary `Query` and `Mutation` types:
        -[] `Query` type
                - `me`: which returns a `user` type
        -[]`Mutation` type: 
                -[]`login` Accepts an email and password parameters returns an `Auth` type
                -[]`addUser`: Accepts a username, email, and password as parameters; returns an `Auth` type.
                -[]`saveBook`: Accepts a book author's array, description, title, bookId, image, and link as parameters; returns a`User` type. (Look into creating what's known as an `input` type to handle all of these parameters!)
                -[]`removeBook`Accepts a book's bookId as a parameter; returns a User type.
        -[] `User` type: 
                -[] `_id`
                -[] `username`
                -[] `email`
                -[] `bookCount`
                -[] `savedBooks` This will be an array of `Book` type
        -[] `Book` type:
                -[]`bookId` not the `_id` but the book's `id` value returned fromm Google's Book API
                -[]`authors` (An array of strings as there be more than one author)
                -[] `description`
                -[] `title`
                -[]`image`
                -[]`link`
        -[] `Auth` type:
                -[]`token`
                -[]`user` (references the` User` type)  


## Front end specs

- []    `queries.js` This will hold the query `GET_ME`, which will execute the `me` query set up using the apollo server 

- []    `mutations.js`  
                -[]`LOGIN_USER` will execute the `loginUser` mutation set up using Apollo Server
                -[] `ADD_USER`   will execute the `addUser` mutation
                -[]`SAVE_BOOK`  will execute the `saveBook` mutation
                -[]`REMOVE_BOOK` will execute the `removeBook` mutation

- []    `App.js`: create an apollo provider to make every request work with the apollo server 

- []   ` SearchBooks.js`:
                -[]Use the Apollo `useMutation()` Hook to execute the `SAVE_BOOK` mutation in the `handleSaveBook()` function instead of the `saveBook()` function imported from the `API` file.
                -[]Make sure you keep the logic for saving the book's ID to state in the `try...catch `block!

- []   ` SavedBooks.js`
                -[]Remove the `useEffect()` Hook that sets the state for `UserData`.
                -[]Instead, use the` useQuery()` Hook to execute the `GET_ME` query on load and save it to a variable named `userData`.
                -[]Use the` useMutation()` Hook to execute the `REMOVE_BOOK` mutation in the` handleDeleteBook()` function instead of the `deleteBook()` function that's imported from` API `file. (Make sure you keep the `removeBookId()` function in place!)
                -[]`SignupForm.js`: Replace the` addUser()` functionality imported from the `API` file with the `ADD_USER` mutation functionality.
                -[]`LoginForm.js`: Replace the `loginUser()` functionality imported from the `API` file with the `LOGIN_USER` mutation functionality.

   


## Grading Requirements

- [] This Challenge is graded based on the following criteria:



## Technical Acceptance Criteria: 40%
- []    Apollo Server: GraphQL replacing the RESTful API

- []    Apollo server applied to express.js as middleware

- []    Includes schema settings for resolvers and typeDefs outlined above

-[]     Modify existing authentication to work with GraphQL API

-[]     Use an apollo provider so that the application can communicate with the apollo server 

- []   Deployed to Heroku

## Deployment: 32%

- []    Application deployed at live URL

- []    Application loads with no errors

- []    Application Github URL Submitted

- []    Github Repository contains application code



## Application Quality: 15%
- []    User experience is intuitive and easy to navigate.


## Repository Quality: 13%
- []    Repository has a unique name.

- []    Repository follows best practices for file structure and naming conventions.

- []    Repository follows best practices for class/id naming conventions, indentation, quality comments, etc.

- []    Repository contains multiple descriptive commit messages.

- []    Repository contains quality README file with description, screenshot, and link to deployed application.




## How to Submit the Challenge
- []    You are required to submit BOTH of the following for review:

- []    The URL of the functional deployed application

- []    The URL of the GitHub repository. Give the repository a unique name and include a README describing the project.