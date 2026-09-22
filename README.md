**# User Registration, Login & JWT Authentication Using Express.js**

**# 🔐 Secure User Authentication API**

**### Node.js • Express.js • MongoDB Atlas • Mongoose • bcrypt • JWT**

**\*\*A complete authentication system implementing user registration, secure password hashing, login authentication, JWT generation, authentication middleware, and a protected private profile endpoint.\*\***

\---

**## 👩‍💻 Student Details**

**\*\*Name\*\*** | Akhila Anish Das \<br>

**\*\*Roll No.\*\*** | 150096725016 \<br>

**\*\*Assignment\*\*** | User Registration, Login & JWT Authentication Using Express.js \<br>

**\*\*Project Folder\*\*** | \`12-NODE-AK\` 

\---

**## 📌 Project Overview**

This project implements a secure user authentication system using **\*\*Node.js, Express.js, MongoDB Atlas, Mongoose, bcrypt, JSON Web Token (JWT), and dotenv\*\***.

The application provides a complete authentication flow:

\`\`\`text

USER

 │

 ├── Register

 │      │

 │      ▼

 │   POST /register

 │      │

 │      ▼

 │   Validate User

 │      │

 │      ▼

 │   bcrypt.hash()

 │      │

 │      ▼

 │   MongoDB Atlas

 │      │

 │      ▼

 │   User Stored

 │

 ├── Login

 │      │

 │      ▼

 │   POST /login

 │      │

 │      ▼

 │   Find User

 │      │

 │      ▼

 │   bcrypt.compare()

 │      │

 │      ▼

 │   Generate JWT

 │      │

 │      ▼

 │   Return Token

 │

 └── Private Profile

        │

        ▼

     GET /profile

        │

        ▼

   Authentication Middleware

        │

        ▼

     Read Bearer Token

        │

        ▼

      jwt.verify()

        │

      ┌─┴─┐

      │   │

    VALID INVALID

      │   │

      ▼   ▼

   Profile 401

   Response Unauthorized

\`\`\`\`

The project follows the required authentication flow of registration, password hashing, login, JWT generation, JWT verification, and protected API access.

\---

\# 🎯 Objectives

The main objectives of this project are:

\* Create a user registration endpoint.

\* Accept user name, email, and password.

\* Check whether an email already exists.

\* Hash passwords using \`bcrypt\`.

\* Store only hashed passwords in MongoDB Atlas.

\* Never store plaintext passwords.

\* Create a login endpoint.

\* Verify passwords using \`bcrypt.compare()\`.

\* Generate a JWT after successful login.

\* Create authentication middleware.

\* Read JWT tokens using the \`Authorization: Bearer TOKEN\` format.

\* Verify JWT tokens using the JWT secret.

\* Protect the \`/profile\` endpoint.

\* Reject requests without a token.

\* Reject requests with invalid tokens.

\* Allow requests with valid JWT tokens.

\* Test the complete authentication flow using Postman.

\---

\# 🛠️ Technologies Used

\| Technology             | Purpose                           |

\| ---------------------- | --------------------------------- |

\| \*\*Node.js\*\*            | JavaScript runtime environment    |

\| \*\*Express.js\*\*         | Backend web framework             |

\| \*\*MongoDB Atlas\*\*      | Cloud database                    |

\| \*\*Mongoose\*\*           | MongoDB object modeling           |

\| \*\*bcrypt / bcryptjs\*\*  | Password hashing and verification |

\| \*\*jsonwebtoken\*\*       | JWT generation and verification   |

\| \*\*dotenv\*\*             | Environment variable management   |

\| \*\*Postman\*\*            | API testing                       |

\| \*\*Visual Studio Code\*\* | Development environment           |

\---

\# ✨ Key Features

\## 1. User Registration

Users can register using:

\* Name

\* Email

\* Password

The password is hashed before being stored.

\`\`\`text

Plain Password

      ↓

bcrypt.hash()

      ↓

Hashed Password

      ↓

MongoDB Atlas

\`\`\`

\---

**## 2. Secure Password Storage**

Plaintext passwords are never stored in MongoDB.

Example stored password:

\`\`\`text

$2b$10$........................................

\`\`\`

instead of:

\`\`\`text

Rahul\@123

\`\`\`

This ensures that the original password is not directly stored in the database.

\---

**## 3. User Login**

Registered users can log in using:

\`\`\`json

{

*"email"*: "rahul\@example.com",

*"password"*: "Rahul\@123"

}

\`\`\`

The server:

1\. Finds the user using the email.

2\. Compares the entered password with the stored bcrypt hash.

3\. Generates a JWT when the credentials are correct.

4\. Returns the JWT token.

\---

**## 4. JWT Authentication**

After successful login, the API returns a JWT token.

Example:

\`\`\`json

{

*"message"*: "Login successful",

*"token"*: "JWT_TOKEN_HERE"

}

\`\`\`

The token is then used to access protected endpoints.

\---

**## 5. Authentication Middleware**

The authentication middleware:

\`\`\`text

Authorization Header

        ↓

Bearer Token

        ↓

Extract JWT

        ↓

jwt.verify()

        ↓

Valid Token?

     /       \\

   YES       NO

   ↓          ↓

Continue     401

\`\`\`

\---

**## 6. Protected Profile Endpoint**

The private endpoint is:

\`\`\`text

GET /profile

\`\`\`

It can only be accessed using a valid JWT.

**### Without token**

\`\`\`text

401 Unauthorized

\`\`\`

**### Invalid token**

\`\`\`text

401 Unauthorized

\`\`\`

**### Valid token**

\`\`\`text

200 OK

\`\`\`

\---

**# 📁 Project Structure**

\`\`\`text

12-NODE-AK/

│

├── middleware/

│   └── authMiddleware.js

│

├── models/

│   └── User.js

│

├── node_modules/

│

├── SCREENSHOTS/

│   ├── 01_Successful_Registration.png

│   ├── 02_User_Stored_MongoDB_Atlas.png

│   ├── 03_Hashed_Password_MongoDB_Atlas.png

│   ├── 04_Successful_Login.png

│   ├── 05_JWT_Token_Received.png

│   ├── 06_Profile_Without_Token.png

│   ├── 07_Profile_Invalid_Token.png

│   └── 08_Profile_Valid_Token.png

│

├── .env

├── .env.example

├── .gitignore

├── package.json

├── package-lock.json

├── README.md

└── server.js

\`\`\`

**### Folder Responsibilities**

\| File / Folder                  | Purpose                                                   |

\| ------------------------------ | --------------------------------------------------------- |

\| \`server.js\`                    | Main Express server and API endpoints                     |

\| \`models/User.js\`               | Mongoose User schema/model                                |

\| \`middleware/authMiddleware.js\` | JWT authentication middleware                             |

\| \`.env\`                         | Private environment variables                             |

\| \`.env.example\`                 | Safe environment variable template                        |

\| \`.gitignore\`                   | Prevents sensitive/unnecessary files from being committed |

\| \`package.json\`                 | Project configuration and dependencies                    |

\| \`package-lock.json\`            | Locks installed dependency versions                       |

\| \`SCREENSHOTS/\`                 | Assignment demonstration screenshots                      |

\| \`README.md\`                    | Project documentation                                     |

\---

**# 🧩 API Endpoints**

**## 1. Register User**

**### Endpoint**

\`\`\`http

POST /register

\`\`\`

**### URL**

\`\`\`text

http\://localhost:3000/register

\`\`\`

**### Request Body**

\`\`\`json

{

*"name"*: "Rahul",

*"email"*: "rahul\@example.com",

*"password"*: "Rahul\@123"

}

\`\`\`

**### Successful Response**

\`\`\`json

{

*"message"*: "User registered successfully"

}

\`\`\`

**### Expected Status**

\`\`\`text

201 Created

\`\`\`

\---

**# 2. Login User**

**### Endpoint**

\`\`\`http

POST /login

\`\`\`

**### URL**

\`\`\`text

http\://localhost:3000/login

\`\`\`

**### Request Body**

\`\`\`json

{

*"email"*: "rahul\@example.com",

*"password"*: "Rahul\@123"

}

\`\`\`

**### Successful Response**

\`\`\`json

{

*"message"*: "Login successful",

*"token"*: "JWT_TOKEN_HERE"

}

\`\`\`

**### Expected Status**

\`\`\`text

200 OK

\`\`\`

\---

**# 3. Private Profile Without Token**

**### Endpoint**

\`\`\`http

GET /profile

\`\`\`

**### URL**

\`\`\`text

http\://localhost:3000/profile

\`\`\`

No Authorization header is provided.

**### Expected Response**

\`\`\`json

{

*"message"*: "Access denied. No token provided."

}

\`\`\`

**### Expected Status**

\`\`\`text

401 Unauthorized

\`\`\`

\---

**# 4. Private Profile With Invalid Token**

**### Endpoint**

\`\`\`http

GET /profile

\`\`\`

**### Authorization**

\`\`\`text

Bearer abc123invalid

\`\`\`

**### Expected Response**

\`\`\`json

{

*"message"*: "Invalid or expired token"

}

\`\`\`

**### Expected Status**

\`\`\`text

401 Unauthorized

\`\`\`

\---

**# 5. Private Profile With Valid Token**

**### Endpoint**

\`\`\`http

GET /profile

\`\`\`

**### Authorization**

\`\`\`text

Bearer JWT_TOKEN

\`\`\`

**### Successful Response**

\`\`\`json

{

*"message"*: "Welcome to your private profile",

*"user"*: {

*"id"*: "USER_ID",

*"email"*: "rahul\@example.com"

  }

}

\`\`\`

**### Expected Status**

\`\`\`text

200 OK

\`\`\`

\---

**# 🔐 Authentication Flow**

**## Registration Flow**

\`\`\`text

POST /register

      ↓

Receive name, email, password

      ↓

Check existing email

      ↓

bcrypt.hash(password, 10)

      ↓

Create User

      ↓

MongoDB Atlas

      ↓

Registration Successful

\`\`\`

\---

**## Login Flow**

\`\`\`text

POST /login

      ↓

Receive email + password

      ↓

Find User by Email

      ↓

bcrypt.compare()

      ↓

Password Correct?

    /       \\

  NO         YES

  ↓           ↓

401       Generate JWT

              ↓

          Return Token

\`\`\`

\---

**## Protected API Flow**

\`\`\`text

GET /profile

      ↓

Authorization Header

      ↓

Bearer JWT

      ↓

Authentication Middleware

      ↓

jwt.verify()

      ↓

Token Valid?

    /       \\

  NO         YES

  ↓           ↓

401       Continue

              ↓

        Private Profile

              ↓

           200 OK

\`\`\`

\---

**# 🌐 MongoDB Atlas**

The application uses **\*\*MongoDB Atlas\*\*** as the cloud database.

The database contains a \`users\` collection.

Example document:

\`\`\`json

{

*"\_id"*: "USER_ID",

*"name"*: "Rahul",

*"email"*: "rahul\@example.com",

*"password"*: "$2b$10$HASHED_PASSWORD",

*"createdAt"*: "DATE",

*"updatedAt"*: "DATE"

}

\`\`\`

The important security requirement is that the password stored in MongoDB is a bcrypt hash rather than the original plaintext password.

\---

**# 🔒 Environment Variables**

The project uses \`.env\` to store sensitive configuration.

Example:

\`\`\`env

MONGO_URI=mongodb+srv://USERNAME\:PASSWORD\@cluster0.xxxxx.mongodb.net/authentication_db?retryWrites=true&w=majority

JWT_SECRET=your_jwt_secret_here

PORT=3000

\`\`\`

**### Important**

The actual \`.env\` file must remain private.

The repository should contain:

\`\`\`text

.env.example

\`\`\`

instead of exposing the actual MongoDB credentials or JWT secret.

\---

**# 🛡️ Security Measures**

This project implements the following security practices:

\* Passwords are hashed using bcrypt.

\* Plaintext passwords are not stored in MongoDB.

\* JWT is used for authenticated API access.

\* JWT is verified using the configured secret.

\* Protected routes require authentication.

\* Requests without tokens are rejected.

\* Invalid tokens are rejected.

\* MongoDB credentials are stored in environment variables.

\* JWT secrets are stored in environment variables.

\* \`.env\` is excluded using \`.gitignore\`.

\---

**# 🚀 Installation & Setup**

**## Prerequisites**

Install:

\* Node.js

\* npm

\* MongoDB Atlas account

\* Postman

\---

**## 1. Clone the Repository**

\`\`\`bash

git clone YOUR_GITHUB_REPOSITORY_URL

\`\`\`

Move into the project:

\`\`\`bash

cd 12-NODE-AK

\`\`\`

\---

**## 2. Install Dependencies**

\`\`\`bash

npm install

\`\`\`

\---

**## 3. Create** \`.env\`

Create a file named:

\`\`\`text

.env

\`\`\`

Add:

\`\`\`env

MONGO_URI=YOUR_MONGODB_ATLAS_CONNECTION_STRING

JWT_SECRET=YOUR_JWT_SECRET

PORT=3000

\`\`\`

\---

**## 4. Start the Server**

\`\`\`bash

npm start

\`\`\`

Expected output:

\`\`\`text

Server running on http\://localhost:3000

MongoDB Atlas connected successfully

\`\`\`

\---

**# 🧪 Postman Testing**

The complete API was tested using Postman.

\| Test                       | Method | Endpoint    | Expected Result    |

\| -------------------------- | ------ | ----------- | ------------------ |

\| Register                   | \`POST\` | \`/register\` | \`201 Created\`      |

\| Login                      | \`POST\` | \`/login\`    | \`200 OK\` + JWT     |

\| Profile without token      | \`GET\`  | \`/profile\`  | \`401 Unauthorized\` |

\| Profile with invalid token | \`GET\`  | \`/profile\`  | \`401 Unauthorized\` |

\| Profile with valid token   | \`GET\`  | \`/profile\`  | \`200 OK\`           |

\---

**# 📸 Assignment Screenshots**

The following eight screenshots document the required authentication tests and MongoDB Atlas verification.

**## 01 — Successful Registration**

The `POST /register` request is sent through Postman and returns `201 Created` with the message **"User registered successfully"**.

![Successful registration](./SCREENSHOTS/01_Successful_Registration.png)

\---

**## 02 — User Stored in MongoDB Atlas**

The registered user is visible in the MongoDB Atlas `authentication_db.users` collection.

![User stored in MongoDB Atlas](./SCREENSHOTS/02_User_Stored_MongoDB_Atlas.png)

\---

**## 03 — Hashed Password in MongoDB Atlas**

The MongoDB Atlas document shows the password stored as a bcrypt hash beginning with `$2b$10$`, rather than the original plaintext password.

![Hashed password in MongoDB Atlas](./SCREENSHOTS/03_Hashed_Password_MongoDB_Atlas.png)

\---

**## 04 — Successful Login**

The `POST /login` request successfully authenticates the registered user and returns `200 OK` with the **"Login successful"** message.

![Successful login](./SCREENSHOTS/04_Successful_Login.png)

\---

**## 05 — JWT Token Received**

The successful login response contains the generated JWT token, which is required to access the protected `/profile` endpoint.

![JWT token received](./SCREENSHOTS/05_JWT_Token_Received.png)

\---

**## 06 — Profile Without Token**

The protected `GET /profile` endpoint is accessed without an Authorization token and returns `401 Unauthorized` with **"Access denied. No token provided."**

![Profile without token](./SCREENSHOTS/06_Profile_Without_Token.png)

\---

**## 07 — Profile With Invalid Token**

The protected `GET /profile` endpoint is tested with an invalid Bearer token and returns `401 Unauthorized` with **"Invalid or expired token"**.

![Profile with invalid token](./SCREENSHOTS/07_Profile_Invalid_Token.png)

\---

**## 08 — Profile With Valid Token**

The protected `GET /profile` endpoint is accessed using the valid JWT received after login and returns `200 OK` with the private profile response.

![Profile with valid token](./SCREENSHOTS/08_Profile_Valid_Token.png)

\---

**# ✅ Assignment Requirement Checklist**

\| Requirement                  | Status |

\| ---------------------------- | ------ |

\| Node.js                      | ✅      |

\| Express.js                   | ✅      |

\| MongoDB Atlas                | ✅      |

\| Mongoose                     | ✅      |

\| bcrypt password hashing      | ✅      |

\| jsonwebtoken                 | ✅      |

\| dotenv                       | ✅      |

\| User Schema / Model          | ✅      |

\| \`POST /register\`             | ✅      |

\| \`POST /login\`                | ✅      |

\| JWT generation               | ✅      |

\| Authentication middleware    | ✅      |

\| \`GET /profile\`               | ✅      |

\| Protected private endpoint   | ✅      |

\| Postman testing              | ✅      |

\| \`.env.example\`               | ✅      |

\| \`.gitignore\`                 | ✅      |

\| MongoDB Atlas user storage   | ✅      |

\| Hashed password verification | ✅      |

\| Successful registration test | ✅      |

\| Successful login test        | ✅      |

\| No-token test                | ✅      |

\| Invalid-token test           | ✅      |

\| Valid-token test             | ✅      |

\---

**# 📊 Authentication Demonstration**

The project demonstrates the complete secure authentication lifecycle:

\`\`\`text

                 USER

                  │

        ┌─────────┴─────────┐

        │                   │

     REGISTER              LOGIN

        │                   │

        ▼                   ▼

  POST /register       POST /login

        │                   │

        ▼                   ▼

  Password Input       Find User

        │                   │

        ▼                   ▼

  bcrypt.hash()       bcrypt.compare()

        │                   │

        ▼                   ▼

  MongoDB Atlas       Correct Password

                            │

                            ▼

                       Generate JWT

                            │

                            ▼

                       Return Token

                            │

                            ▼

                     GET /profile

                            │

                            ▼

                  Authentication Middleware

                            │

                            ▼

                       jwt.verify()

                            │

                     ┌──────┴──────┐

                     │             │

                   INVALID        VALID

                     │             │

                     ▼             ▼

                  401 Error    Private Data

                                   │

                                   ▼

                                200 OK

\`\`\`

\---

**# 🎓 Learning Outcomes**

Through this project, the following backend and authentication concepts were implemented:

\* Express.js server setup

\* REST API endpoints

\* MongoDB Atlas integration

\* Mongoose schemas and models

\* Secure password hashing

\* Password comparison

\* Environment variables

\* JWT authentication

\* Bearer token authentication

\* Express middleware

\* Protected routes

\* HTTP status codes

\* API testing using Postman

\* Secure configuration management

\---

**# 🔍 HTTP Status Codes Demonstrated**

\| Status Code        | Meaning                          | Used In               |

\| ------------------ | -------------------------------- | --------------------- |

\| \`200 OK\`           | Request completed successfully   | Login / Valid Profile |

\| \`201 Created\`      | User successfully created        | Registration          |

\| \`401 Unauthorized\` | Authentication failed or missing | Protected Profile     |

\---

**# 📂 Important Files**

**###** \`server.js\`

The main application file responsible for:

\* Starting the Express server

\* Connecting to MongoDB Atlas

\* Handling registration

\* Handling login

\* Generating JWT tokens

\* Providing the private \`/profile\` endpoint

**###** \`models/User.js\`

Contains the Mongoose User model used to represent users stored in MongoDB Atlas.

**###** \`middleware/authMiddleware.js\`

Responsible for:

\* Reading the Authorization header

\* Extracting the Bearer token

\* Verifying the JWT

\* Rejecting invalid or missing tokens

\* Allowing authenticated requests to continue

**###** \`.env\`

Contains private configuration values such as:

\`\`\`text

MONGO_URI

JWT_SECRET

PORT

\`\`\`

**###** \`.env.example\`

Provides the environment-variable structure without exposing real credentials.

**###** \`.gitignore\`

Prevents sensitive or unnecessary files such as \`.env\` and \`node_modules\` from being committed.

\---

**# 🧠 Core Security Concept**

The most important security principle demonstrated by this project is:

\`\`\`text

NEVER STORE:

Rahul\@123

STORE:

$2b$10$................................

\`\`\`

During registration:

\`\`\`text

Password

   ↓

bcrypt.hash()

   ↓

Hashed Password

   ↓

MongoDB Atlas

\`\`\`

During login:

\`\`\`text

Entered Password

       ↓

bcrypt.compare()

       ↓

Stored Hash

       ↓

Password Match

       ↓

JWT Generated

\`\`\`

This separates password storage from authentication and prevents the original password from being stored directly in the database.

\---

**# 🏁 Conclusion**

The **\*\*User Registration, Login & JWT Authentication Using Express.js\*\*** project successfully implements a complete authentication workflow using Node.js, Express.js, MongoDB Atlas, Mongoose, bcrypt, JWT, and dotenv.

The project demonstrates:

\`\`\`text

Registration

     ↓

Secure Password Hashing

     ↓

MongoDB Atlas Storage

     ↓

Login Authentication

     ↓

JWT Generation

     ↓

JWT Verification

     ↓

Protected /profile Endpoint

\`\`\`

The implementation was tested using Postman for successful registration, successful login, missing-token access, invalid-token access, and valid-token access.

\---

**## 👩‍💻 Author**

**\*\*Akhila Anish Das\*\***

**\*\*Roll No.: 150096725016\*\***

\---

**## 📌 Project Status**

\`\`\`text

Authentication API

        │

        ├── Registration       ✅

        ├── Password Hashing   ✅

        ├── MongoDB Atlas      ✅

        ├── Login              ✅

        ├── JWT Generation     ✅

        ├── JWT Middleware     ✅

        ├── Protected Profile  ✅

        └── Postman Testing    ✅

\`\`\`