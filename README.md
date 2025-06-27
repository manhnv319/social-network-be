# 📱 Social Network System

A backend social network system built with **Hexagonal Architecture**, focusing on scalability, clean code, and modular design. The system supports essential social network features such as user authentication, friend recommendations, toxic comment filtering, and image uploading.

---

## 🚀 Features
- ✅ **RESTful API** using Spring Boot 3 and Spring Security
- ✅ **JWT**-based user authentication and authorization
- ✅ **Toxic comment filtering** using Naive Bayes algorithm
- ✅ **Friend suggestion system** based on a scoring mechanism
- ✅ **Image storage** using AWS S3
- ✅ **Redis caching** to improve performance

---

## 🛠️ Technologies
- **Backend:** Spring Boot 3, Spring Security, MySQL, Redis, AWS S3
- **Authentication:** JWT
- **AI Integration:** Naive Bayes algorithm for comment filtering
- **Architecture:** Hexagonal (Ports & Adapters)

---

## 📂 Project Structure
```text
BACKEND
├── .idea
├── .mvn
├── src
│   ├── main
│   │   ├── java/com/example/socialnetwork
│   │   │   ├── application
│   │   │   │   ├── controller
│   │   │   │   ├── request
│   │   │   │   ├── response
│   │   │   ├── common
│   │   │   │   ├── annotation
│   │   │   │   ├── constant
│   │   │   │   ├── event
│   │   │   │   ├── mapper
│   │   │   │   └── util
│   │   │   ├── config
│   │   │   ├── domain
│   │   │   │   ├── listener
│   │   │   │   ├── model
│   │   │   │   ├── port
│   │   │   │   ├── publisher
│   │   │   │   └── service
│   │   │   ├── exception
│   │   │   ├── filter
│   │   │   ├── infrastructure
│   │   │   │   ├── adapter
│   │   │   │   ├── entity
│   │   │   │   ├── repository
│   │   │   │   └── specification
│   │   │   ├── SocialNetworkApplication.java
│   │   └── resources
│   └── test
├── .env
├── .gitignore
├── docker-compose.yaml
├── Dockerfile
├── envsample
└── pom.xml
```

---

## ⚙️ Requirements
- Java 17+
- MySQL
- Redis
- AWS S3 account
- Maven 3.6+

---

## 🚀 Getting Started

### 1. Clone the project
```bash
git clone https://github.com/manhnv319/social-network-be.git
cd social-network-be
```

### 2. Configure the environment
- Update database, Redis, and S3 configurations in `application.yml`
- Add your JWT secret key

### 3. Build the project
```bash
mvn clean install
```

### 4. Run the project
```bash
mvn spring-boot:run
```

---

## 📡 API Endpoints

| Method | Endpoint                               | Description                                 |
|--------|----------------------------------------|---------------------------------------------|
| GET    | `/api/v1/close_relationship`           | Get list of close relationships              |
| GET    | `/api/v1/comment`                      | Get all comments                             |
| GET    | `/api/v1/comment/{comment_id}`         | Get a specific comment by ID                 |
| GET    | `/api/v1/comment_reaction`             | Get list of comment reactions                |
| GET    | `/api/v1/newsfeed`                     | Get user's newsfeed                          |
| GET    | `/api/v1/post`                         | Get all posts                                |
| GET    | `/api/v1/post/number_post`             | Get number of posts                          |
| GET    | `/api/v1/post_reaction`                | Get list of post reactions                   |
| GET    | `/api/v1/profile`                      | Get user's profile                           |
| GET    | `/api/v1/friend/get_list_receive_requests` | Get list of received friend requests       |
| GET    | `/api/v1/friend/get_list_send_requests`    | Get list of sent friend requests           |
| GET    | `/api/v1/friend/get_list_friends`      | Get list of friends                          |
| GET    | `/api/v1/friend/get_list_block`        | Get list of blocked users                    |
| GET    | `/api/v1/friend/view_suggest`          | View friend suggestions                      |
| GET    | `/api/v1/friend/find_friend`           | Search for friends                           |
| GET    | `/api/v1/friend/number_of_friends`     | Get number of friends                        |
| GET    | `/api/v1/tag`                          | Get all tags                                 |
| GET    | `/api/v1/search`                       | Search posts and users                       |
| POST   | `/api/v1/auth/register`                | User registration                            |
| POST   | `/api/v1/auth/register/verify`         | Verify user registration                     |
| POST   | `/api/v1/auth/forgot_pass`             | Request password reset                       |
| POST   | `/api/v1/auth/verify_forgot_pass`      | Verify password reset request                |
| POST   | `/api/v1/auth/reset_pass`              | Reset password                               |
| POST   | `/api/v1/auth/change_pass`             | Change password                              |
| POST   | `/api/v1/auth/login`                   | User login                                   |
| POST   | `/api/v1/auth/refresh`                 | Refresh JWT token                            |
| POST   | `/api/v1/auth/logout`                  | User logout                                  |
| POST   | `/api/v1/auth/logout/all`              | Logout from all devices                      |
| POST   | `/api/v1/close_relationship`           | Create a close relationship                  |
| POST   | `/api/v1/comment`                      | Create a new comment                         |
| POST   | `/api/v1/comment_reaction`             | React to a comment                           |
| POST   | `/api/v1/images/upload`                | Upload an image                              |
| POST   | `/api/v1/post`                         | Create a new post                            |
| POST   | `/api/v1/post_reaction`                | React to a post                              |
| POST   | `/api/v1/friend/send_request`          | Send a friend request                        |
| POST   | `/api/v1/friend/accept_request`        | Accept a friend request                      |
| POST   | `/api/v1/friend/refuse_request`        | Refuse a friend request                      |
| POST   | `/api/v1/friend/block`                 | Block a user                                 |
| POST   | `/api/v1/friend/unblock`               | Unblock a user                               |
| POST   | `/api/v1/tag`                          | Create a new tag                             |
| PUT    | `/api/v1/post`                         | Update a post                                |
| PUT    | `/api/v1/profile`                      | Update user profile                          |
| DELETE | `/api/v1/close_relationship`           | Delete a close relationship                  |
| DELETE | `/api/v1/comment`                      | Delete a comment                             |
| DELETE | `/api/v1/comment_reaction`             | Delete a comment reaction                    |
| DELETE | `/api/v1/post`                         | Delete a post                                |
| DELETE | `/api/v1/post_reaction`                | Delete a post reaction                       |
| DELETE | `/api/v1/profile`                      | Delete user profile                          |
| DELETE | `/api/v1/friend/delete_request`        | Cancel a sent friend request                 |
| DELETE | `/api/v1/friend/delete_friend`         | Remove a friend                              |
| DELETE | `/api/v1/tag`                          | Delete a tag                                 |

---

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to submit a pull request.

---

## 📜 License
This project is licensed under the MIT License.
