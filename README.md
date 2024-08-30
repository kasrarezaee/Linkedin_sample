# A linkedin like app using java and javafx

## Description

this is a simple linkedin like app built using java for the backend and javafx for the client side. this app interacts with 
a mysql database and RESTful API endpoints. it uses MVC(model-view-control) architecture.

## Contents

* Installation
* Features
* Endpoints
* Technologies used
* License
* Contribution

## Installation

1. clone this repo to your local machine.
2. configure the database connection. open the `DataBaseConnector.java` file located at `Linkedin_server/src/main/java/com/Ap_project/server/dataAccess/`

```java
public class DataBaseConnecter {
    private static final String url = "jdbc:mysql://localhost:3306/Linkedin";
    private static final String userName = "Your_User_Name";
    private static final String password = "Your_Password";
    private static Connection connection;
    private static Statement statement;
    public static Connection connecter(){
        try{
            if(connection == null || connection.isClosed()){
                connection = DriverManager.getConnection(url , userName , password);
            }
        }
        catch (SQLException e){
            e.printStackTrace();
        }
        return connection;
    }
}
```
3. modify the `Your_User_name` and `Your_Password` with your username and password based on your mysql database  configuration
4. build and run the server app and then the client app.

## Features

1. User Management
    * Create, retrieve, update, and delete users.
    * Manage user bios and profile images.
    * Follow/unfollow other users.
    * Block/unblock other users.
    * Making connection with other users.
2. Post Management
    * Create posts
    * Repost
    * Like and comment
3. User Profile
    * View users profile
    * Edit profile
    * Add educational background and skills.
4. Messaging and Notification
   * View and send messages
   * View connection , follow and message notification
5. Searching
   * Search among the posts based on their caption
   * Search among the users.

## Endpoints

```
user endpoints:
---------------
GET /users
GET /users/userID
GET /users/search/name
GET /userMedia/user_id/type
POST /userMedia/user_id/mediaType/Type
POST /users/userID
POST /users
DELETE /userMedia/user_id/type
DELETE /users
DELETE /users/userID

skills endpoints:
---------------
GET /skills/userID
POST /skills/userID
DELETE /skills/userID/skillTitle

educations endpoints:
---------------
GET /educations/userID
POST /educations/userID
DELETE /educations/userID/educationID

locations endpoints:
---------------
GET /locations/userID
POST /locations/userID
DELETE /locations/userID

contactInfos endpoints:
---------------
GET /contactInfos/userID
POST /contactInfos/userID
DELETE /contactInfos/userID

posts endpoints:
---------------
GET /posts
GET /posts/userID
GET /posts/search/target
GET /postMedia/userID/postID
POST /posts/userID
POST /postMedia/userID/postID/mediaType
DELETE /posts
DELETE /posts/userID/postID
DELETE /postMedia/userID/postID

comments endpoints:
---------------
GET /comments/postID
POST /comments/userID/postID
DELETE /comments/userID/postID/commentID

notifications endpoints:
---------------
GET /notifications/userID
POST /notifications/src/target/description
DELETE /notifications/id

messages endpoints:
---------------
GET /messages/sender/receiver
GET /messages/notification/receiver/sender
GET /messages/chatRooms/userID
POST /messages/sender/receiver
DELETE /messages/userID/messageID

login endpoints:
---------------
GET /login/webToken
POST /login

likes endpoints:
---------------
GET /likes/userID/postID
GET /likes/check/userID/postID
POST /likes/userID/postID
DELETE /likes/userID/postID

follow endpoints:
---------------
GET /follows/followers/user_id
GET /follows/followings/user_id
GET /follows/check/user_1/user_2
POST /follows/follower/followed
DELETE /follows/follower/followed

connections endpoints:
---------------
GET /connects/connections/userID
GET /connects/check/user1/user2
POST /connects/user_1/user_2
DELETE /connects/user_1/user_2

block endpoints:
---------------
GET /blocks/userID
GET /blocks/check/user_1/user_2
POST /blocks/user_1/user_2
DELETE /blocks/blocker/blocked
```

## Technologies Used

* Java
* JavaFX
* MySQL
* HTTP Server
* JWT authentication
* MVC architecture
* JSON

## License

This project is licensed under the MIT License. You are free to modify and distribute the project according to the terms of the license.

## Contribution

If you want to contribute  , please follow these steps:
   1. Fork the repository.
   2. Create a new branch for your feature or bug fix.
   3. Make your changes and ensure that the codebase passes all tests.
   4. Submit a pull request describing your changes.