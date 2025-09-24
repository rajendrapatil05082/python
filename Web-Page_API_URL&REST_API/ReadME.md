# Difference between Web Page, API, URL & REST API
### 1. URL (Uniform Resource Locator)

The address of something on the internet.

Can point to a web page or an API endpoint.

Example:

https://www.google.com → Google’s homepage

https://api.github.com/users/octocat → GitHub API endpoint

### 2. Web Page

A document you see in your browser, built with HTML, CSS, JavaScript.

Designed for humans to read.

Example:

https://www.wikipedia.org → Opens Wikipedia homepage with text and links.

### 3. API (Application Programming Interface)

A service that provides data or functions to other programs.

Designed for computers/programs, not humans.

Output is usually in JSON or XML.

Example:

https://api.github.com/users/octocat → Returns JSON like:

{
  "login": "octocat",
  "id": 583231,
  "type": "User"
}

### 4. REST API (Representational State Transfer)

A popular style of API that uses HTTP methods (GET, POST, PUT, DELETE).

Each resource (like a user, product, or order) has a unique URL.

Simple, stateless, and widely used in web and mobile apps.

Example (User API):

GET https://api.example.com/users → Get all users

GET https://api.example.com/users/1 → Get user with ID = 1

POST https://api.example.com/users → Add a new user

PUT https://api.example.com/users/1 → Update user 1

DELETE https://api.example.com/users/1 → Delete user 1

### ✅ Quick Analogy:

URL = Address of a shop

Web Page = The shop itself (humans go and see products)

API = Shop’s delivery service (apps request raw items)

REST API = The delivery service with fixed rules (order, update, cancel, etc.)
