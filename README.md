# Project-2-Proposal

<h5>Jordan Mesibov's Project 2 Proposal</h5>

<h2>Project 2 Requirements</h2>
-------------------------------------------------------------------------
<br>
* `Node.js + express`
<br>
* `Sequelize w/ Object Relational Mapper (ORM)`
<br>
* `GET and POST routes`
<br>
* `Heroku Deployment`
<br>
* `1 new Library, package, or technology we haven't used in bootcamp yet`
<br>
* `Polished frontend/UI`
<br>
* `MVC Paradigm folder organization`
<br>
* `Protect/hide sensitive data (ie API keys)`
<br>
* `Adhere to good coding standards/practices (ie proper indentation/spacing)`
<br>
-----------------------------------------------------------------------------

<h1>There are two objectives/functions that the travel app could help accomplish:</h1>
<br>
  <h2>1. Help a group of people decide where to go on vacation.</h2>
<br>
  <h2>2. Help a group of people decide when to go on vacation.</h2>

<h2>It should be noted that the most important thing to me is that we create an app that will go great in our portfolios!</h2>

-----------------------------------------------------------------------------
-----------------------------------------------------------------------------
<h1>FRONT-END:</h1>

  1. Log-in/user authentication

  2. Through the frontend, a user would register a new vacation event (similar to how a facebook user creates a facebook group) to our database and that would create a table that would store the group members as data in the backend. This would generate an event key that would be used to allow only the group members to access the page. Maybe make it part of the url endpoint using categories/parameters (ie /api/:vacationId).
    -This user could be the group leader and potentially have veto ability/admin privelages in order to expedite decision making processes between group members.
        -low priority: let users set a profile picture/nickname that would default to a smiley face or some other image and their username if they don't provide one. Display these with any posts anyone makes.

  3. Make it so that users can suggest destination/vacation spots that require group-leader approval in order to be Posted. The group leader would not require anyone's approval.
  
  3. Set it up so that users can interact with a GUI that would allow them to move things around on the page. They can reorder/reorganize the placement of different vacation ideas so that the top item is their favorite and the bottom is their least favorite.
    - Let them interact with the vacation idea items so that they can trigger different boolean flags that could alter an item's appearance to indicate how they feel about the destination/idea (ie if they think going to Jamaica and going to Orlando are equally awesome, they could click a '<3 (heart/love)' button or something on both options and it would make them both glow green or whatever we want that do display as) so that other users can see how strongly they like something.

  4. Maybe set up an aggregate rating system where all users in the group can input a number out of 10 for each destination and this would populate backend table. Use that table and these numbers to calculate an average rating out of 10 for each destination. Whether we would allow null depends on how we want to approach it. Have a display in the GUI showing the choices by aggregate rating.

  5. Generate a background or a carousel based on the categories of vacation possiblities that the users are interested in (ie cruise would find an images of a cruise ship, Jamaica would show images of Jamaica, etc.). Maybe use keyframes to fade from one vacation destination to the next if it is a background. Maybe allow the group leader to just choose a list of images that the page would cycle through, based on their choice(s). (this is just a possibility. It may look more professional if we just give our app a theme/brand and stick with that.)

  6. Have a section where users can chat/post text. Maybe try to make replies to posts a thing (like how you can reply to a post/comment on facebook), or just have all of the posts appear chronologically if development time runs short.

  7. Display vacation ideas in order of projected travel cost(s). This can either be amounts of money entered by the user, or we can try to code the functions to access a tourism API that would potentially have data on this information. We would need to account for length of time spent at/in destination. It may be better/easier to either allow group leader/member input for how much the trip would cost based on their own research. Alternatively, if we struggle with figuring out the workings of a relevant tourism API, we could provide a button that would open a new google search in a new tab of travel costs associated with the destination in order to help the users with their research.

  8. Provide a GUI that allows the group leader to post when the group plans to go on vacation. Maybe they can input a range of dates/times. Use this and moment and/or sequelize to display a countdown until that time frame. Make this large and near the top of the screen (without being obnoxious) to help pressure group members to take action inside the app.
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
<h1>BACK-END:</h1>

  1. Set up/create a database/schema that would store various tables.

  2. Make it so that a table becomes created when a user registers a new vacation event as dictated by the second item in the FRONT-END section of this page. Perhaps the api vacationKey endpoint could be required in order to view the page's contents.
    - This table could be used for user authentication as well (or we could use a new table to store passwords and use foreign keys/joins to link them). Allow group members to set their own passwords to be stored in MySQL database. Once a password is set, trigger a boolean flag concerning whether the password has been created yet to flip.
    - When that user visits the app/site in the future, they would be prompted to log in and we would perform something like:

    ...get("/api/blahblahblah...(route info for the GET function and other relevant code) function() {
    
    db.sequelize.findOne({
      where: {
        user.password (or member.password or however we organize it): req.params.password
      }
    })
  
    } ...
      -(I haven't checked the syntax of this b/c it's just an idea of an approach, we would also need dotenv for private information)
      * This is obviously not the best way to handle the use of passwords, but it could work for the proof of concept of the app.   -When we learn about sessions and Passport on Monday, we will likely change our approach to authentication.

    3. Make a table of vacation destinations that the users suggest, captured via the GUI/frontend.

    4. Make a table that would store user ratings of vacation destination possibilities.

    5. Make a table that would store the order/priority that each user gives to the vacation destination (ie a user may think Orlando and Jamaica are both 10 out of 10 because they love them both so much, but maybe they think Jamaica is a better choice, so they place Jamaica higher up in their personal list).

    6. There would be plenty of backend work for figuring out how to organize the tables and how to link/join the tables in order to display different information to the user.

    7. Access an API that we would use to populate a table to provide information and/or links to information about the suggested travel ideas. (ie if the group leader approves of a member's suggestion that they want the group to consider going to China, then clicking or hovering on China would do something to provide the user with information about China).

    8. As mentioned in number 8 in the frontend section, capture dates of vacation times/ranges. Use this to display a countdown for the group members.
--------------------------------------------------------------------------------
<br>
<h2>Try to make all of this as mobile-friendly as possible. If people have to get on a computer to use the app, its a barrier to entry/hurts the ease of use of the app itself.</h2>
<h4>That being said, we have limited time to get it all up and running. We'll do what we can!</h4>

<h3>These are just some things we could try to implement that I thought of today. Plans will surely evolve and change if we go with this app for our project. I am open to any and all sugestions, critiques, concerns, etc. as I am sure there are many other potential features to include or to exclude and better ways to go about handling/coding them. Like I said earlier in class, my priority is to help create a great project that will shine in my portfolio and in your portfolios. This app idea is just one possible way to approach that goal!</h3>