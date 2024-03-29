Basic authentication
Description
What you should learn from this project:

What authentication means
What Base64 is
How to encode a string in Base64
What Basic authentication means
How to send the Authorization header
0. Simple-basic-API
Download and start your project from this archive.zip
1. Error handler: Unauthorized
What the HTTP status code for a request unauthorized? 401 of course!
2. Error handler: Forbidden
What the HTTP status code for a request where the user is authenticate but not allowed to access to a resource? 403 of course!
3. Auth class
Now you will create a class to manage the API authentication.
4. Define which routes don't need authentication
Update the method def require_auth(self, path: str, excluded_paths: List[str]) -> bool: in Auth that returns True if the path is not in the list of strings excluded_paths:
5. Request validation!
Now you will validate all requests to secure the API:
6. Basic auth
Create a class BasicAuth that inherits from Auth. For the moment this class will be empty.
7. Basic - Base64 part
Add the method def extract_base64_authorization_header(self, authorization_header: str) -> str: in the class BasicAuth that returns the Base64 part of the Authorization header for a Basic Authentication:
8. Basic - Base64 decode
Add the method def decode_base64_authorization_header(self, base64_authorization_header: str) -> str: in the class BasicAuth that returns the decoded value of a Base64 string base64_authorization_header:
9. Basic - User credentials
Add the method def extract_user_credentials(self, decoded_base64_authorization_header: str) -> (str, str) in the class BasicAuth that returns the user email and password from the Base64 decoded value.
10. Basic - User object
Add the method def user_object_from_credentials(self, user_email: str, user_pwd: str) -> TypeVar('User'): in the class BasicAuth that returns the User instance based on his email and password.
11. Basic - Overload current_user - and BOOM!
Now, you have all pieces for having a complete Basic authentication.
12. Basic - Allow password with ":"
Improve the method def extract_user_credentials(self, decoded_base64_authorization_header) to allow password with :.