# Polling-app

Step 1: Install Dependencies

Install the project dependencies using npm:


npm install

Step 2: upload Database file in your phpmyadmin to create db and tables

file name is polling_app_db.sql


DB_HOST=localhost
DB_USER=your_mysql_username
DB_PASSWORD=your_mysql_password

Step 5: Database Migration



bash
Copy code
npx knex migrate:latest
Step 6: Start the Server

Start your Node.js server:


npm start 

Your server should now be running on port 3000, or the port you specified in your Express configuration.

Step 7: Test Setup

Ensure your tests are correctly set up. Make sure you have Mocha and Chai installed as development dependencies.

Step 8: Run Tests

Run your tests using Mocha:


npx mocha tests/authentication.test.js tests/polling.test.js 

This command will execute your authentication and polling tests. Fix any failing tests and make sure all tests pass.



Step 9: Test with Postman

You can also test your API using Postman. Import your Postman collection with API endpoints and use it to send requests to your running server.


Authentication APIs:

User Registration (POST /auth/register)

json
Copy code
{
  "username": "testuser",
  "password": "testpassword"
}


User Login (POST /auth/login)

json
Copy code
{
  "username": "testuser",
  "password": "testpassword"
}

in header write a key name {Authorization} Value is Bearer token
Create a New Poll (POST /polls/create)

json
Copy code
{
  "title": "Sample Poll",
  "description": "This is a sample poll.",
  "options": ["Option A", "Option B", "Option C"]
}

List All Polls (GET /polls/list)

No request body is required for this GET request.

Vote on a Poll (POST /polls/vote)

json
Copy code
{
  "pollId": 1,      // Replace with the actual poll ID
  "optionId": 2     // Replace with the actual option ID
}
User Management APIs:

Get User Details (GET /users/{{user_id}})

Replace {{user_id}} with the actual user ID.

Get User's Voting History (GET /users/{{user_id}}/voting-history)

Replace {{user_id}} with the actual user ID
