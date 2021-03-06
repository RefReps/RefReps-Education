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
  + The client wants to make creating unique course with given information to be able to create the many courses. To be able to set up a new course given a set of base information to make the course creation process user friendly for the client. This was not easy to do with their current software.
  + Owner enters course information (Title, Sport, Content, etc.) --> a standard class format is created with the information
+ UC2 - Add and edit course curriculum
  + Actor(s): Owner, Video Database
  + BR2
  + The client wants to be able to add different information to the course such as videos and quizzes for the students to access and be able to edit the curriculum that has been added. Their current platform does not allow for the type of content they want to add.
  + Owner wants to add or remove content --> find the module where the content is --> have a add/remove button for the module
+ UC3 - Upload videos from the database
  + Actor(s): Owner, Video Database
  + BR1 and BR2
  + The client has a large database of videos on their RefReps app that they want to make use of in the learning platform so they want to be able to pull from their existing database to be able to add those videos from the database to the learning platform. They are currently not able to use this database with their current platform and have to give each organization a new copy of the videos that they would have to store on their systems.
  + Owner selects video(s) they want to upload from the database --> the Owner adds them to the course --> the Owner can organize where the video(s) will go in the course
+ UC4 - Track and report video viewership
  + Actor(s): Owner, User Database, Video Database
  + BR1
  + The client wants to be able to keep track of who watches a particular video, how many students viewed a particular video, and how much time they spent watching the video for each "class", the particular instance of the course, to be able to report back to their customers for the Author to make use of the information. Teachable is bad at tracking how the viewer is interacting with the video and often does not acknowledge viewership and leads to problems with course completion for students. The best the client can do currently is providing the client with a copy of all the videos that can track stats for their organization.
  + the Owner uploads a video to a module --> students watch the video --> the students that view the video are recorded and saved --> the Owner can deliver that info to the organization
+ UC5 - Add multiple choice quizzes
  + Actor(s): Owner
  + BR2
  + The client wants to keep the quizzes that the students are able to take and allow the Owner to add quizzes to the platform. They like the quiz functionality that Teachable has but the after selecting an answer for quizzes the correct answer is displayed to the student. Teachable also allows for an immense amount of attempts from the student so the student can retake the quiz however many times they need while knowing the correct answers. The client would like to be able to allow the students to take the quiz a set number of times without immediately giving the correct answer to the questions after giving a reponse.
  + the Owner can upload quiz(zes) --> organize where the quizzes will go --> students can select choices from the quiz --> the responses are recorded --> responses checked against correct answers --> student receives score
+ UC6 - Allow Author to set release schedules
  + Actor(s): Author
  + BR2
  + The client want to be able to have set times that new content can be release. On Teachable all of the content is available all the time and when completion benchmarks are added, often time they are not cleared correctly and force the Owners to manually check completion. The client wants to be able to set content to be release on a schedule like one a week as this software is mostly used in high school classes where assignments are given through the semester and shouldn't all be available to skip through immediately
  + the Author can go to some content (module, video, quiz) --> the Author can hide the content from student view --> the Author can designate when/how often the content is release --> on scheduled release the student can view the content
+ UC7 - Be accessible from IOS, Android, and web
  + Actor(s): Owner, Author, Student
  + BR2
  + The current RefReps app is only available on IOS but they want to expand to other platforms in the near future. So they want this learning management system to be avaialble from their RefReps system and be available wherever RefReps is.
  + the user opens the RefReps app --> the user can select the learning management system from within the app --> the app will send the user to the web app for the system.

