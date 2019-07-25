# iframe authentication proof of concept

- The story renders, and creates an invisible iframe loading a google.com URL
- The invisible iframe being on google.com can access Google cookies and know the authentication status
- If logged in, user can use reactions
- If not logged in, clicking the "Log in" button sends a postMessage to the google.com iframe asking for authentication
- The google.com iframe receives the message and opens a popup to login, with a return URL
- When the user completes the login form, they get redirected to the return URL
- That return URL loads a page containing JavaScript that communicates back to the google.com iframe the authentication success failure or success
- The google.com iframe now knows that the user is authenticated, closes the popup window, and communicates back to the story
- User can now use reactions
