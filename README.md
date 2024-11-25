Here's an expanded README file for your **Tour and Travel Server** project.

---

# Tour and Travel Server

This project provides a backend server for a Tour and Travel application using Node.js and MongoDB. It includes models and CRUD operations for **Users**, **Tours**, and **Reviews** with relationships between them, allowing users to view, create, and manage tours and reviews. Mongoose is used for MongoDB data modeling.

## Models

### User Model

The `User` model represents the users in the application. Users can have different roles and statuses.

| Field   | Type    | Description                     |
| ------- | ------- | ------------------------------- |
| `name`  | String  | The name of the user            |
| `email` | String  | The email address of the user   |
| `age`   | Number  | The age of the user             |
| `photo` | String  | URL of the user's profile photo |
| `role`  | String  | Role of the user (e.g., `user`, `admin`) |
| `status`| String  | Account status (`active`, `inactive`) |

### Tour Model

The `Tour` model represents the tours available for users to book.

| Field        | Type    | Description                          |
| ------------ | ------- | ------------------------------------ |
| `name`       | String  | Name of the tour                    |
| `duration`   | Number  | Duration of the tour (in days)      |
| `rating`     | Number  | Average rating of the tour          |
| `price`      | Number  | Price of the tour                   |
| `coverImage` | String  | URL for the tour's cover image      |
| `image`      | Array   | Array of URLs for tour images       |
| `startDate`  | Date    | Start date of the tour              |
| `tourLocation`| String | Location of the tour               |

### Review Model

The `Review` model allows users to review and rate specific tours.

| Field     | Type   | Description                                   |
| --------- | ------ | --------------------------------------------- |
| `review`  | String | Text review written by the user               |
| `rating`  | Number | Rating given to the tour (e.g., from 1 to 5)  |
| `tour`    | ObjectId | Reference to the associated `Tour` model   |
| `user`    | ObjectId | Reference to the `User` who wrote the review|

## API Endpoints

The application includes endpoints for performing CRUD operations on `User`, `Tour`, and `Review` resources.

