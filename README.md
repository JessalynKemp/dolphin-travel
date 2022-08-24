# Dolphin Travels

<font size="4">[Dolphin Travels Web Application](https://dolphin-travel.netlify.app)</font>

## How to Use the App

**Dolphin Travels is a travel planner web application designed to help you plan a solo trip or a group trip with friends and family.** 

The link above will direct you to the homepage. The web application is designed to only allow a user to view their trips once they are logged in. To log in as one of the hardcoded users, click the "login" button.

Once you are logged in, you will be able to see the trips that the user has planned. This can be filtered by "current trips"  which are upcoming trips and "previous trips" which are archived/old trips.

To view a trip, click on the trip card. You can delete a trip by pressing the trash can on the trip card. Please note that only the creator of the trip can delete it.

To create a new trip, click the "create trip" button and fill out the form. Give your trip a name, budget, start date and end date; select the country you are visiting; add other users to the trip; and search for your specific accommodation.

Once a trip has been created, you will be taken to the daily itinerary. Here, you can plan a day of your trip, delete a planned day, edit the trip, and view all your planned  activities in a list or map format. The map format shows your activities relative to your accommodation.

To add an activity to a day that has already been created, click on the day card. There are a variety of suggested activities nearby your accommodation. To add a suggested activity, click on the map marker and press "add attraction". You can also delete an activity by clicking on a marker that you have already added.

There is also functionality to search for a specific activity. Type your search term into the input box and press "search". Once you have selected the activity from the dropdown list, you can add this activity to your list. When you return to your daily itinerary, any activities will be listed on the day cards.

## Backend API

### Link to the API

<font size="4">[Dolphin Travels API](https://dolphin-travel.herokuapp.com/api)</font>

### Project Summary

An API to access the Dolphin Travels application data programmatically and provide it to a frontend architecture.

To see the endpoints that are currently available to users, click on the link above.

### Cloning the Repository

If you wish to experiment and make your own changes to this project, press the 'fork' button to create a copy of the repository and clone the forked repo.

To clone the repo, click on the 'code' button at the top of the page and copy the URL you require (HTTPS, SSH, or GitHub CLI).

Navigate to the directory that you wish to clone the repo to locally and write the following command in your terminal (where url is the URL that you copied from GitHub):

```
git clone url
```

### Install the Dependencies

The following devDependencies and dependencies are required for the backend of this project to run. Please see the linked documentation for information on how to install each of these dependencies. Alternatively, run the following command in the terminal.

```
npm install
```

#### Backend  Dependencies

- [express](https://expressjs.com/en/starter/installing.html): for creating the REST API and using middleware functions
- [dotenv](https://www.npmjs.com/package/dotenv): loads the environment variables from a .env file
- [cors](https://www.npmjs.com/package/cors): allows cross-origin resource sharing
- [mongodb](https://www.mongodb.com/docs/drivers/node/current/): for seeding, connecting to, and querying the database

#### Backend devDependencies

- [husky](https://www.npmjs.com/package/husky): utilise git hooks to run a pre-commit file
- [supertest](https://www.npmjs.com/package/supertest): integration testing of endpoints
- [jest](https://jestjs.io/docs/getting-started): for testing
- [nodemon](https://www.npmjs.com/package/nodemon): restarts the node application after a file change (when testing using Insomnia)
- [eslint-dependencies](https://eslint.org/), [prettier](https://prettier.io/): for consistent formatting across collaborators on the project

These dependencies are also listed in the package.json file.

### Seeding the Database

To seed the local database, setup a MongoDB Atlas account, create a cluster, navigate to the repo in your terminal and write the following command:

```
npm run seed-prod
```

This will set up a production database seeded with some basic data.

### Environment Variables

To successfully connect to the development and test databases, you will need to create two .env files which contain the correct Mongo host, username and password for each environment. Navigate to the repo in your terminal and write the following commands:

```
touch production.env
touch test.env
```

Into each file, add:

- MONGO_HOST=<mongo_host_here>
- MONGO_USER=<mongo_username_here>
- MONGO_PW=<mongo_password_here>

(see your Mongo Atlas account for more information on how to obtain these).

Add \*.env to the gitignore to ensure that these files are not uploaded to GitHub.

### Running Tests

To seed the test database and run the tests using jest, write the following command:

```
npm test
```

This will run all of the tests stored in the \_\_tests\_\_ folder. The tests folder contains integrated tests for the application. If you wish to run a specific test file, use the following command:

```
npm test name_of_file
```

## Frontend Technologies and Frameworks

- Vue
- Vue Router
- Vue Leaflet 3
- Axios
- Vanilla CSS

## Third Party APIs

- [country-flags-api](https://countryflagsapi.com)
- [LocationIQ](https://locationiq.com/)

### Version Requirements

- node.js: ^16.15.0

### Future Improvements
- Authentication: the API relies on queries provided by the frontend to return the relevant information for the user that is logged in. In the future, it would be more appropriate to implement a proper authentication system such as Auth0 or Passport.js.
- Restructure Data: more investigation into structuring noSQL data is required. Perhaps the days and activities would have their own collections.
- Refactoring: some of the API's endpoints have repeated code which could be simplified.
- Frontend Bug Fixes: we are aware of several bugs that require fixing.
- Edit Trip: we currently have a complex PATCH endpoint set up in order to edit a trip. This has not been fully implemented on the frontend but is something we are looking towards in the future.
