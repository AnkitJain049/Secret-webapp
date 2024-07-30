User Registration:
User visits /register and submits the registration form.
The server checks if the user already exists.
If not, the password is hashed using bcrypt.
A new user is inserted into the database.
The user is logged in and redirected to /secrets.

User Login:
User visits /login and submits the login form.
The server verifies the user's credentials using Passport's local strategy.
If valid, the user is logged in and redirected to /secrets.

Accessing Secrets:
User visits /secrets.
The server checks if the user is authenticated.
If authenticated, the server fetches the user's secret from the database and renders the secrets.ejs view.
If not authenticated, the user is redirected to /login.

Submitting a Secret:
Authenticated user visits /submit and submits the secret form.
The server updates the user's secret in the database.
The user is redirected to /secrets.

Google OAuth2 Authentication:
User clicks on the "Sign in with Google" button.
User is redirected to Google's authentication page.
After authentication, Google redirects back to /auth/google/secrets.
The server handles the callback, checks if the user exists in the database, and creates a new user if necessary.
The user is logged in and redirected to /secrets.
