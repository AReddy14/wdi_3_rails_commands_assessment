# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?
 rails new BunnyApp --database=postgresql -T (I did look this up)
### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command should I type in the terminal? 
rails generate model Bunny name:string color:string age:integer
technically explicitly saying that color and name are strings is unnecessary because that is the default

### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.
The command creates a migration in the db folder, a model in the models folder under app, and a table with the attributes columns mentioned in the creation line an id column before the rest and two timestamp columns afterwards. The database is still actually non-existent unless you've already created that. 

better explanation for where the files show up and what is created:
rails g model: creates /app/models/bunny.rb which defines the Bunny as a ruby class, AND creates a migration file in /db/migrate with the columns and datatypes that were specified in the Terminal command

rails g migration: creates a migration file in /db/migrate with the columns and datatypes that were specified in the Terminal command (and if you didn't specify then it will default to string) /db/schema.rb is NOT created until you actaully run the migration

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?
rake db:create will create a blank or empty database.
rake db:migrate will ensure that the most recent version of the tables you've created are there in the database.

(if you did rails g migration then you're model files still don't exist, and you would need to create them manually)

### Question 5

I want to look at the actual database that has been created. What command should I type in the terminal?
rake db will allow you to go through the database using postgres (if you've specified that as what you are using for your database earlier). Then you just have to use SQL commands to look at the database

so close. rails db is the correct answer.

alternate option
psql BunnyApp_development

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal? 
I honestly don't remember. I don't think this is even in my notes at the moment. Something for me to look up.

answer: rake routes, *face palm*

### Question 7

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?
rails server
will cause the computer to actually run the app. In order to view it in your browser you just go to localhost:3000
