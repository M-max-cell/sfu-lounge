---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# SFULounge
SFU Lounge is a unique Android app tailored for Simon Fraser University students, aiming to overcome the socialization challenges in a commuter-heavy environment. The app encourages meaningful connections among students by offering features such as interest-based matching and icebreaker chats. Users can discover like-minded peers, stay updated on campus events, and initiate conversations through the in-app chat feature, fostering a sense of community within SFU.  

## Why SFU Lounge?
1. **Connections**. Encourages connections beyond academic boundaries, helping users meet others outside their major.

2. **Only for SFU**. This is a friends making app only meant for SFU students, making it easier for the audience to meet each other in real life

3. **Making SFU more alive**. Connects SFU commuter students, overcoming socialization challenges and building a sense of community on campus

## Challenges  
- designing nosql schema that is efficient
- using firestore SDKs to interact with the database
- building database index to improve querying time for specific queries
- using firestore snapshot listeners with livedata in the viewmodel to respond to changes in the database and update UI
- using email verification for new accounts. Our app will send a verification email to new users and they must click the link in the email to be able to continue/login to our app
- using firebase storage with firestore to upload images
- using library such as Glide to display images that are remote (urls) 
- used complex thread programming to enhance ui experience in explore page
- use prefetching to load users profile pictures without needing to make queries in the adapter
- adapted Swipe Cards API so that users can effortlessly navigate through users profiles by swiping left or right animations
- Implemented notification by using a foreground service to check for any new messages 
- came up with an recommendation algorithm to load of users
- Designed custom UI/UX design: custom buttons, backgrounds, gridview and much more
- Added custom backgrounds for different pages
- Psychology research to determine user’s personality in order to have better matchmaking algorithm
- Ensured that textviews stayed restricted to 1 line and included ellipsis (…) if they exceeded the 1 line.
- As firebase does not have support for cross service error handling we needed to implement our own data recovery strategies when we detect inconsistencies with the database
- created new styling pages to enforce photo dimensions and frames so that we can have round profile photos

## Design Diagrams
- [MVVM Model Document](https://docs.google.com/document/d/142Y2wBGEi41fotJXZjBQioxGrZqqjPv744CmfmjM3T8/edit?usp=sharing)
- [Threading Diagram](https://github.com/kianhk6/SFULounge/files/13471130/thread_diagram_3.4.pdf)

## Who did what
### Kian Hosseinkhani
- Management: Led the team, assigned tasks and bug fixes via GitHub issues, and designed the MVVM diagram prototype.
- Worked on matchmaking features.
- Created database tables, repository functions, and viewmodels.
- Developed user recommendation algorithms.
- Participated in the development of chatting/messaging feature.
- Provided documentation.
- Worked on threading for loading up user profiles in the explore page for my robust UI.
- Worked on sorting/filtering users based on compatibility.
- Worked on implementing ice breakers
- Fixed styling bugs in the development of chatting/messaging feature.

### Mathew Wong
- Created database tables, repository functions, and viewmodels
- Implemented email authentication for sign-up.
- Implemented login features.
- Implemented sign up back end 
- Implemented chatting/messaging feature.
- Participated in Bug fixing tasks related to the front end wiring.
- Created Settings page [changing images, depth questions, interests and basic information]
- Implemented the website.
- Provided thread diagram.
- Improved chatrooms by using firestore snapshot listeners with livedata in the viewmodel to respond to changes in the database and update UI
- Implemented Notification services
- Implemented error handling for firebase
- Used libraries such as Glide to display images that are remote (urls)

### Teeya Li
- Designed Interest and Deep Questions for the sign-up page.
- Created the Welcome page.
- Contributed to UI prototyping.
- Provided documentation.
- Participated in Bug Fixing Tasks Related to the Front End Wiring.
- Styled Status Bar and App Icon
- Created and Styled the ‘No More Recommendations Left’ Page
- Styled the Personality Quiz Page
- Designed and Styled Messages and Chat Rooms

### Nathalie Kaspar
- Designed images and basic information sign-up page and email authentication page.
- Designed explore page xml by putting custom backgrounds and other components.
- Adapted SwipeCards API so that users can effortlessly navigate through users profiles by swiping left or right
- Developed wiring between the xml components and the User information.
- Showcased a simple and user friendly user profile view by adding an "expand" button to show or hide the user's info
- Styled both Day and Night themes to ensure an aesthetically pleasing UI for all users.
- Enhanced responsiveness by using Glide to display images that are remote (urls)

### Divij Gupta
- Participated in brainstorming meeting for backend database architecture.
- Psychology research to find 15 questions to ask from the users so he can assign them a personality tag
- Implemented the quiz calculating user’s response and assigned the user’s with their tag through a pop up [These tags will be used to enhance user recommendations]

## Presentation
For the grading and inspect of 362's professor and TAs ([Click to download app APK](https://github.com/M-max-cell/sfu-lounge/releases/download/sfu-lounge-v3.0.0/sfu-lounge.apk))

- [Presentation video (includes demo)](https://youtu.be/s9mEcrVzXas)
- [Presentation slides](https://docs.google.com/presentation/d/1jn93Px_FvLQPenU4TvXCC9juKwyNrdpZk9ZVbpEzj2o/edit?pli=1#slide=id.p)

# More Details
This section includes more details on app features, future plans and past show and tells.  

## Features
### User Profile
- **User Database Fields**: ID, First Name, Last Name (hidden), Gender, SFU Email, Password, Interests, Depth Questions (3), Photos (up to 5), Online Status.
- **Swipe Mechanism**: Users can swipe left or right on other user profiles. Swipe actions are stored with user IDs.
- **Chatrooms**: Each match creates a new chatroom with IDs for users and messages.
- **Message System**: Messages in chatrooms are identified by IDs and include timestamps and sender details.

### UI Pages
- **Login/Signup Page**: Start page with options to log in or sign up.
- **Photo Page**: Users upload 2 to 4 photos.
- **Personality Page**: Select up to 4 interests and answer up to 3 depth questions.
- **Swipe Page**: Displays user profiles for swiping.
- **Chat Rooms**: List view of all DMs.
- **Settings Page**: Options to edit user information, interests, depth questions, and photos.

### ViewModel Functions
- **UserViewModel**: Handles login, signup, and settings update functionalities.
- **MatchesViewModel**: Manages the swiping mechanism and user recommendations.
- **ChatViewModel**: Queries chat rooms and messages, handles chat functionalities.

### Unit tests
- implemented unit tests with JUnit
- unit tests cover login, sign up and more basic functionality

## Implementation Details

### User Profile
- **Images**: 1 to 5 photos allowed.
- **Depth Questions**: Users answer selected questions to add depth to their profiles.
- **Interest Tags**: Users select from a list of interests.
- **Optional Fields**: Major, course list, age, pronouns, voice profiles, location, languages, zodiac sign, SFU club memberships.

### App Mechanics
- **User Recommendations**: Based on shared interests and preferences.
- **Blind Profiles**: Anonymous profiles shown during certain hours, focusing on character rather than appearance.
- **Matching Algorithm**: Matches users based on interests, values, and depth question answers.
- **Icebreaker Chat**: Facilitates easy conversation initiation.


## Show and Tell 1 (Sprint 1)
For the grading and inspect of 362's professor and TAs ([~~Click to download app APK~~](https://github.com/M-max-cell/sfu-lounge/releases/download/sfu-lounge-v1.0.0/sfu-lounge.apk))

## Mock Ups
UI mock-up for settings page  
![settings page mock-up](settings_page_ui_mockup.jpg)  

Design specifications: 
[Design Specification Document](https://docs.google.com/document/d/142Y2wBGEi41fotJXZjBQioxGrZqqjPv744CmfmjM3T8/edit#heading=h.8lr8rdf90n3b)

### The MVVM Model
You can view the document for the mvmm model here: [MVVM Model Document](https://docs.google.com/document/d/142Y2wBGEi41fotJXZjBQioxGrZqqjPv744CmfmjM3T8/edit?usp=sharing)

### Show and Tell 1 Video
Click on the thumbnail below to watch the Show and Tell video:

[![Show and Tell Video](https://img.youtube.com/vi/wpXYgcXO-2Y/0.jpg)](https://youtu.be/wpXYgcXO-2Y)

## Work Completed to Date (Over a 2 week sprint)

- **Login:** Completed
- **Sign Up:** Completed
- **Chatting Ability**
  - Backend: Model
  - Model View
  - UI Prototype
- **Explore Page** (swipes, user recommendation)
  - Backend: Model
  - Model View
  - UI Prototype
- **Settings:** Backend Prototype Completed


## Team Contributions

### Kian Hosseinkhani
- **Management**: Led the team, assigned tasks and bug fixes via GitHub issues, and designed the MVVM diagram prototype.
- Worked on matchmaking features.
- Created database tables, repository functions, and viewmodels.
- Developed user recommendation algorithms.
- Participated in the development of chatting/messaging feature.
- Provided documentation.

### Mathew Wong
- Created database tables, repository functions, and viewmodels 
- Contributed to UI prototyping.
- Implemented email authentication for sign-up.
- Implemented login features.
- Implemented sign up back end and provided a UI prototype for it. 
- Implemented chatting/messaging feature.
- Provided documentation.
- Participated in Bug fixing tasks related to the front end wiring.


### Teeya Li
- Developed/Improved Interest and Deep Questions for the sign-up page.
- Created the Welcome page.
- Contributed to UI prototyping.
- Provided documentation.
- Participated in Bug fixing tasks related to the front end wiring.
  
### Nathalie Kaspar
- Developed images and basic information sign-up page.
- Contributed to UI prototyping.
- Provided documentation.
- Participated in Bug fixing tasks related to the front end wiring.

### Divij Gupta
- Participated in brainstorming meeting for backend database architecture.


## Show and Tell 2 (Sprint 2)
For the grading and inspect of 362's professor and TAs ([~~Click to download app APK~~](https://github.com/M-max-cell/sfu-lounge/releases/download/sfu-lounge-v2.0.0/sfu-lounge2.apk))

## Mock Ups

### The Thread Diagram
[thread_diagram.pdf](https://github.com/kianhk6/SFULounge/files/13471130/thread_diagram_3.4.pdf)

### Show and Tell 2 Video
Click on the thumbnail below to watch the Show and Tell video:

[![Show and Tell Video](https://img.youtube.com/vi/Wpi2w2JjpzU/0.jpg)](https://youtu.be/Wpi2w2JjpzU)

## Work Completed to Date (Over a 1 week sprint)

- **Settings page** Completed
- **Recommendation algorithm [for recommending users to get swiped on]** Completed
- **Personality quiz page** Completed just needs to save the user's personality tag to the Database 
- **Explore Page** 
  - Styling prototype completed
  - need some tweaks + need to add animation for swipes and make the swiping more robust 
- **Chatroom lists:** Most of styling completed some minor tweaks regarding the chatroom names
- **Messages:**
  - Ice breaker questions implemented: recommended conversation starter based on common interests

## Team Contributions

### Kian Hosseinkhani
- **Management**: Led the team, assigned tasks and bug fixes via GitHub issues, and designed the scrum stories.
- Worked on threading for loading up user profiles in the explore page for my robust UI.
- Worked on sorting through users based on compatibility. (profiles with most shared interests show up first)
- Worked on removing users that have already gotten swiped on.
- Worked on implementing ice breakers: a message pops up in the chatroom, asking a question related to common interests between users so both users can initiate conversations easier.
- Fixed styling bugs in the development of chatting/messaging feature.
- Provided documentation.

### Mathew Wong
- Created Settings page [changing images, depth questions, interests and basic information]
- Implemented the website.
- Fixed complicated bugs related to sign in and sign up. 
- Provided thread diagram.
- Improved chatrooms by using firestore snapshot listeners with livedata in the viewmodel to respond to changes in the database and update UI
- Implemented error handling as firebase does not have support for cross service error handling: needed to implement our own data recovery strategies when we detect inconsistencies with the database
- Used libraries such as Glide to display images that are remote (urls)
- Implemented paging to paginate all messages in message activity. This improves load times. We used PagingDataSource, PagingAdapter, layout manager and recyclerview to accomplish this.

### Nathalie Kaspar
- Designed explore page xml by putting custom backgrounds and other components.
- Developed wiring between the xml components and the User information.
- Developed a swiping feature rather than using buttons. 

### Teeya Li
- Enhanced the Chatrooms list fragment xml
- Created new styling pages to enforce photo dimensions and frames so that we can have round profile photos
- Ensured that textviews stayed restricted to 1 line and included ellipsis (...) if they exceeded the 1 line.

### Divij Gupta
- Psychology research to find 15 questions to ask from the users so he can assign them a personality tag
- Implemented the quiz calculating user's response and assigned the user's with their tag through a pop up
[These tags will be used to enhance user recommendations]


## Challenges and Future Developments
- **Outside of course material**:
- designing nosql schema that is efficient
- using firestore SDKs to interact with the database
- building database index to improve querying time for specific queries
- using firestore snapshot listeners with livedata in the viewmodel to respond to changes in the database and update UI
- using email verification for new accounts. Our app will send a verification email to new users and they must click the link in the email to be able to continue/login to our app
- using firebase storage with firestore to upload images
- because firebase does not have support for cross service error handling we needed to implement our own data recovery strategies when we detect inconsistencies with the database
- using library such as Glide to display images that are remote (urls)
- using paging to paginate all messages in message activity. This improves load times. We used PagingDataSource, PagingAdapter, layout manager and recyclerview to accomplish this
- use prefetching to load users profile pictures without needing to make queries in the adapter
- came up with an recommendation algorithm to load of users
- used complex thread programming to enhance ui experience in explore page
- created new styling pages to enforce photo dimensions and frames so that we can have round profile photos
- Ensured that textviews stayed restricted to 1 line and included ellipsis (...) if they exceeded the 1 line.
- Created custom buttons
- Added custom backgrounds for different pages
- Psychology research to determine user's personality in order to have better match making algorithm 
- Initiated the work for notification implementations
- **Future Plans**: Post-semester deployment, advertisement through SFU clubs, and continuous app development for enhancing user experience.

## Getting Started

### Prerequisites
- Android Studio with Kotlin support.
- Firebase account for database and authentication services.

### Installation
1. Clone the repository.
2. Open the project in Android Studio.
3. Configure Firebase and other dependencies.
4. Build and run the application on an emulator or physical device.


## Support and Contact
For support, contact sfu_Lounge_support@gmail.com. Join our community and make your SFU experience unforgettable!  

Developers: Divij Gupta, Kian Hosseinkhani, Nathalie Kaspar, Teeya Li, Mathew Wong
