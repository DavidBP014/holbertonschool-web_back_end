Session authentication
Description
What you should learn from this project:

What authentication means
What session authentication means
What Cookies are
How to send Cookies
How to parse Cookies
0. Et moi et moi et moi!
Copy all your work of the 0x06. Basic authentication project in this new folder.
1. Empty session
Create a class SessionAuth that inherits from Auth. For the moment this class will be empty. It’s the first step for creating a new authentication mechanism:
2. Create a session
Update SessionAuth class:
3. User ID from Session ID
Update SessionAuth class:
4. Session cookie
Update api/v1/auth/auth.py by adding the method def session_cookie(self, request=None): that returns a cookie value from a request:
5. Before request
Update the @app.before_request method in api/v1/app.py:
6. Use Session ID for identifying a User
Update SessionAuth class:
7. New view for Session Authentication
Create a new Flask view that handles all routes for the Session authentication.
8. Logout
Update the class SessionAuth by adding a new method def destroy_session(self, request=None): that deletes the user session / logout: