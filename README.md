## MERN: Book Search Engine

## Description:

Your assignment this week is emblematic of the fact that most modern websites are driven by two things: data and user demands. This shouldn't come as a surprise, as the ability to personalize user data is the cornerstone of real-world web development today. And as user demands evolve, applications need to be more performant.

This week, you’ll take starter code with a fully functioning Google Books API search engine built with a RESTful API, and refactor it to be a GraphQL API built with Apollo Server. The app was built using the MERN stack with a React front end, MongoDB database, and Node.js/Express.js server and API. It's already set up to allow users to save book searches to the back end. 

To complete the assignment, you’ll need to do the following:

1. Set up an Apollo Server to use GraphQL queries and mutations to fetch and modify data, replacing the existing RESTful API.

2. Modify the existing authentication middleware so that it works in the context of a GraphQL API.

3. Create an Apollo Provider so that requests can communicate with an Apollo Server.

4. Deploy your application to Heroku with a MongoDB database using MongoDB Atlas. Use the [Deploy with Heroku and MongoDB Atlas](https://coding-boot-camp.github.io/full-stack/mongodb/deploy-with-heroku-and-mongodb-atlas) walkthrough for instructions.

![Screen Shot 2022-04-20 at 3 15 28 PM](https://user-images.githubusercontent.com/91545451/164325087-71e4f4b7-fd53-4185-971a-05af8df0228c.png)

## Getting Started

In order for this application to use a GraphQL API, you’ll need to refactor the API to use GraphQL on the back end and add some functionality to the front end. The following sections contain details about the files you’ll need to modify on the back end and the front end.

**Important**: Make sure to study the application before building upon it. Better yet, start by making a copy of it. It's already a working application&mdash;you're converting it from RESTful API practices to a GraphQL API.

### Back-End Specifications

You’ll need to complete the following tasks in each of these back-end files:

* `auth.js`: Update the auth middleware function to work with the GraphQL API.
* `server.js`: Implement the Apollo Server and apply it to the Express server as middleware.
* `Schemas` directory:
	* `index.js`: Export your typeDefs and resolvers.
	* `resolvers.js`: Define the query and mutation functionality to work with the Mongoose models.
		**Hint**: Use the functionality in the `user-controller.js` as a guide.
	* `typeDefs.js`: Define the necessary `Query` and `Mutation` types:
		* `Query` type:
			* `me`: Which returns a `User` type.
		* `Mutation` type:
			* `login`: Accepts an email and password as parameters; returns an `Auth` type.
			* `addUser`: Accepts a username, email, and password as parameters; returns an `Auth` type.
			* `saveBook`: Accepts a book author's array, description, title, bookId, image, and link as parameters; returns a `User` type. (Look into creating what's known as an `input` type to handle all of these parameters!)
			* `removeBook`: Accepts a book's `bookId` as a parameter; returns a `User` type.
		* `User` type:
			* `_id`
			* `username`
			* `email`
			* `bookCount`
			* `savedBooks` (This will be an array of the `Book` type.)
		* `Book` type:
			* `bookId` (Not the `_id`, but the book's `id` value returned from Google's Book API.)
			* `authors` (An array of strings, as there may be more than one author.)
			* `description`
			* `title`
			* `image`
			* `link`
		* `Auth` type:
			* `token`
			* `user` (References the `User` type.)

## Scripts: 
In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

## Contributing
David Gavino

## Deploy Link
https://googlebookssesrch.herokuapp.com/
