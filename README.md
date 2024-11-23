# Alura - Nodejs and Gemini

## Introduction

This project is a web application that allows users to upload and view images with AI-generated descriptions and alt texts. The project is divided into two main parts: the backend and the frontend.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Environment Variables](#environment-variables)
- [Project Structure](#project-structure)
- [License](#license)

## Installation

### Backend

1. Clone the repository:

```sh
git clone https://github.com/Mauricifj/alura-node-gemini-backend
cd alura-node-gemini-backend
```

2. Install dependencies:

```sh
npm install
```

3. Create a `.env` file in the root directory and add the following environment variables:

```env
GEMINI_API_KEY="your-gemini-api-key"
MONGO_DB_NAME="your-mongo-db-name"
MONGO_DB_POSTS_COLLECTION="your-mongo-db-posts-collection"
MONGO_DB_CONNECTION_STRING="your-mongo-db-connection-string"
```

### Frontend

1. Clone the repository:

```sh
git clone https://github.com/Mauricifj/alura-node-gemini-frontend
cd alura-node-gemini-frontend
```

2. Install dependencies:

```sh
npm install
```

## Usage

### Backend

1. Start the server:

```sh
npm run dev
```

2. The server will be running on `http://localhost:3000`.

### Frontend

1. Start the development server:

```sh
npm run dev
```

2. The project will be available at `http://localhost:8000`.

## API Endpoints

### Get All Posts

- **URL:** `/posts`
- **Method:** `GET`
- **Response:**

```json
[
    {
        "_id": "post-id",
        "imageUrl": "image-url",
        "description": "image-description",
        "alt": "image-alt"
    },
    ...
]
```

### Create Post

- **URL:** `/posts`
- **Method:** `POST`
- **Request Body:**

```json
{
    "imageEncoded": "base64-encoded-image",
    "isAIEnabled": true, // Will replace image description and alt text for AI generated content
    "description": "image-description",
    "alt": "image-alt"
}
```

- **Response:**

```json
{
    "_id": "post-id",
    "imageUrl": "image-url",
    "description": "image-description",
    "alt": "image-alt"
}
```

## Environment Variables

- `GEMINI_API_KEY`: Your Gemini API key.
- `MONGO_DB_NAME`: The name of your MongoDB database.
- `MONGO_DB_POSTS_COLLECTION`: The name of your MongoDB posts collection.
- `MONGO_DB_CONNECTION_STRING`: Your MongoDB connection string.

## Project Structure

### Backend

```plaintext
backend/
├── .env
├── .gitignore
├── LICENSE
├── package.json
├── README.md
├── server.js
├── services.sh
├── src
│   ├── config
│   │   └── dbConfig.js
│   ├── controllers
│   │   └── postsController.js
│   ├── models
│   │   └── postsModel.js
│   ├── routes
│   │   └── postsRoutes.js
│   ├── services
│   │   └── geminiService.js
└── images
```

### Frontend

```plaintext
frontend/
├── .gitignore
├── assets
│   ├── images
│   ├── js
│   │   ├── fetchApis.js
│   │   └── index.js
│   └── style.css
├── index.html
├── package.json
└── README.md
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
