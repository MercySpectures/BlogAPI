# BlogAPI

This is a simple Blog API that allows users to create, read, update, and delete blog posts. It is built using REST API architecture and consists of two main parts: the backend API and the frontend server.

## Folder Structure

```
BLOGAPI/
│
├── public/
│   └── styles/
│       └── main.css
│
├── views/
│   ├── index.ejs
│   └── modify.ejs
│
├── index.js
├── package.json
└── server.js
```

## Prerequisites

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/)

## Installation

1. Clone the repository
    ```sh
    git clone https://github.com/MercySpectures/BlogAPI.git
    ```
2. Navigate into the project directory
    ```sh
    cd blogapi
    ```
3. Install the dependencies
    ```sh
    npm install
    ```

## Running the API

To start the backend API server, run:

```sh
node index.js
```

The API server will start on `http://localhost:4000`.

To start the frontend server, run:

```sh
node server.js
```

The frontend server will start on `http://localhost:3000`.

## API Endpoints

### Create a new blog post

**Endpoint:** `POST /posts`

**Request Body:**
```json
{
    "title": "Blog Title",
    "content": "Blog Content",
    "author": "Author Name"
}
```

**Response:**
```json
{
    "id": 4,
    "title": "Blog Title",
    "content": "Blog Content",
    "author": "Author Name",
    "date": "2024-06-06T00:00:00.000Z"
}
```

### Get all blog posts

**Endpoint:** `GET /posts`

**Response:**
```json
[
    {
        "id": 1,
        "title": "The Rise of Decentralized Finance",
        "content": "Content of the first blog",
        "author": "Alex Thompson",
        "date": "2023-08-01T10:00:00Z"
    },
    ...
]
```

### Get a single blog post

**Endpoint:** `GET /posts/:id`

**Response:**
```json
{
    "id": 1,
    "title": "The Rise of Decentralized Finance",
    "content": "Content of the first blog",
    "author": "Alex Thompson",
    "date": "2023-08-01T10:00:00Z"
}
```

### Update a blog post

**Endpoint:** `PATCH /posts/:id`

**Request Body:**
```json
{
    "title": "Updated Blog Title",
    "content": "Updated Blog Content",
    "author": "Updated Author"
}
```

**Response:**
```json
{
    "id": 1,
    "title": "Updated Blog Title",
    "content": "Updated Blog Content",
    "author": "Updated Author",
    "date": "2023-08-01T10:00:00Z"
}
```

### Delete a blog post

**Endpoint:** `DELETE /posts/:id`

**Response:**
```json
{
    "message": "Post deleted successfully"
}
```

## Frontend Routes

### Render the main page

**Endpoint:** `GET /`

Fetches all posts and renders the `index.ejs` view.

### Render the new post page

**Endpoint:** `GET /new`

Renders the `modify.ejs` view with heading "New Post" and submit button "Create Post".

### Render the edit post page

**Endpoint:** `GET /edit/:id`

Fetches a specific post by ID and renders the `modify.ejs` view with heading "Edit Post" and submit button "Update Post".

### Create a new post (form submission)

**Endpoint:** `POST /api/posts`

Creates a new post and redirects to the main page.

### Update a post (form submission)

**Endpoint:** `POST /api/posts/:id`

Partially updates a post by ID and redirects to the main page.

### Delete a post (link click)

**Endpoint:** `GET /api/posts/delete/:id`

Deletes a post by ID and redirects to the main page.

## Frontend Views

- **index.ejs:** Displays the list of all blog posts.
- **modify.ejs:** Provides a form to create or edit a blog post.

## Styles

- **main.css:** Contains the CSS styles for the project, located in `public/styles/`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
