# Actors
+ Owner
  + Refreps admin, the company
+ Author
  + The instructor who is proctoring that instance of the course
+ Student
  + the user currently taking the course
+ Database 1: User Account
  + houses the User information
+ Database 2: Videos
  + houses the videos from RefReps


# Use Cases
+ UC1 - Automate the course creation process
  + Actor(s): Owner
  + BR2
  + The client wants to make creating unique course with given information to be able to create the many courses. To be able to set up a new course given a set of base information to make the course creation process user friendly for the client.
+ UC2 - Add and edit course curriculum
  + Actor(s): Owner, Video Database
  + BR2
  + The client wants to be able to add different information to the course such as videos and quizzes for the students to access and be able to edit the curriculum that has been added.
+ UC3 - Upload videos from the database
  + Actor(s): Owner, Video Database
  + BR1 and BR2
  + The client has a large database of videos on their RefReps app that they want to make use of in the learning platform so they want to be able to pull from their existing database to be able to add those videos from the database to the learning platform.
+ UC4 - Track and report video viewership without video duplication
  + Actor(s): Owner, User Database, Video Database
  + BR1
  + The client wants to be able to keep track of who watches a particular video, how many students viewed a particular video, and how much time they spent watching the video for each "class", the particular instance of the course, to be able to report back to their customers for the Author to make use of the information.
+ UC5 - Add multiple choice quizzes
  + Actor(s): Owner
  + BR2
  + The client wants to keep the quizzes that the students are able to take and allow the Owner to add quizzes to the platform.
+ UC6 - Allow Author to set release schedules
  + Actor(s): Author
  + BR2


