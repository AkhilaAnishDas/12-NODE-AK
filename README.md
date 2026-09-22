# Node.js Authentication System

**Student:** Akhila Anish Das  
**Project:** User Authentication using Node.js, Express.js, MongoDB Atlas and JWT

## Features

- User registration
- Password hashing using bcrypt
- User login
- JWT token generation
- Protected profile route
- MongoDB Atlas database
- Authentication middleware

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/register` | Register a new user |
| POST | `/login` | Login and receive JWT |
| GET | `/profile` | Access protected profile |

## Screenshots

### 1. Successful Registration
![Registration](./SCREENSHOTS/01_Successful_Registration.png)

### 2. User Stored in MongoDB Atlas
![MongoDB User](./SCREENSHOTS/02_User_Stored_MongoDB_Atlas.png)

### 3. Hashed Password
![Hashed Password](./SCREENSHOTS/03_Hashed_Password_MongoDB_Atlas.png)

### 4. Successful Login
![Login](./SCREENSHOTS/04_Successful_Login.png)

### 5. JWT Token Received
![JWT](./SCREENSHOTS/05_JWT_Token_Received.png)

### 6. Profile Without Token
![No Token](./SCREENSHOTS/06_Profile_Without_Token.png)

### 7. Profile With Invalid Token
![Invalid Token](./SCREENSHOTS/07_Profile_Invalid_Token.png)

### 8. Profile With Valid Token
![Valid Token](./SCREENSHOTS/08_Profile_Valid_Token.png)
