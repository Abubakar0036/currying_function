# Simple Function
* function simpleFunction(param1, param2, param3) {
    return param1 + param2 + param3; }
console.log(simpleFunction(1, 2, 3)); // Output: 6

# Currying Function
* function curriedFunction(param1) {
    return function(param2) {
        return function(param3) {
            return param1 + param2 + param3;
        };
    };  }

console.log(curriedFunction(1)(2)(3)); // Output: 6

# Stateless API Works (General Idea):
1. No Session Memory:
The server does not store any state or session information about the client between requests.
If you send a request to the server, the server will process that request and return the response without storing any data about that interaction.
2. Self-contained Requests:
Every request made to the API must contain all the necessary information (like authentication tokens, data, etc.) so the server can process it.
For example, if you need to access a user's data, the request must include the user's identity (like a token or ID) because the server won't remember the user from a previous interaction.
3. Your authentication token (like a session token or API key) is sent with each request so the server can verify who you are.
 Etsy (or similar e-commerce)
In an e-commerce application like Etsy, a stateless API would manage requests like user authentication, product searches, viewing individual product pages, adding items to the cart, and purchasing products. Here's a breakdown of how a stateless API works in such a scenario:


# Example :
1. Login/Authentication:
When you log in, your client (web browser, mobile app) sends a request to the API to authenticate you.
The server responds with an authentication token (JWT or session token).
Your client stores this token locally (usually in localStorage or cookies).

2. Searching for Products:
You search for a product, say "handmade earrings".
Your client sends a request to the API with your search term and includes the authentication token to verify your identity.

3. Viewing a Product:
When you click on a product to view details, your client sends another request to the server (API) for that product's details.
Again, the request includes the authentication token and the product ID.

4. Adding an Item to the Cart:
To add an item to the cart, your client sends a request to the API with the product ID and quantity, along with the authentication token.
The cart can be stored client-side (in localStorage) or server-side (often linked to the user ID stored in the database).