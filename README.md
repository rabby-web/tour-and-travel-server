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

### Users

- **Create User**: `POST /api/users`
- **Get All Users**: `GET /api/users`
- **Get Single User**: `GET /api/users/:id`
- **Update User**: `PUT /api/users/:id`
- **Delete User**: `DELETE /api/users/:id`

### Tours

- **Create Tour**: `POST /api/tours`
- **Get All Tours**: `GET /api/tours`
- **Get Single Tour**: `GET /api/tours/:id`
- **Update Tour**: `PUT /api/tours/:id`
- **Delete Tour**: `DELETE /api/tours/:id`

### Reviews

- **Create Review**: `POST /api/reviews`
- **Get All Reviews**: `GET /api/reviews`
- **Get Single Review**: `GET /api/reviews/:id`
- **Update Review**: `PUT /api/reviews/:id`
- **Delete Review**: `DELETE /api/reviews/:id`

## Relationships

- A **Review** references both a **Tour** and a **User** using Mongoose `ObjectId` references, establishing a relationship where each review is linked to a specific user and a specific tour.
  
## Project Setup

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   Create a `.env` file and specify the necessary variables, like `DATABASE_URL` for MongoDB and `PORT`.

4. **Start the server**:
   ```bash
   npm start
   ```

## Technologies Used

- **Node.js**: JavaScript runtime for building the server.
- **Express.js**: Web framework for building the API.
- **MongoDB**: NoSQL database for data storage.
- **Mongoose**: ODM library for MongoDB.
- **TypeScript (optional)**: Adds type safety and enhanced developer experience.

## License

This project is licensed under the MIT License.

--- 

This README provides a detailed overview of each model, endpoint, and the relationships between the data structures in the Tour and Travel server application.