## Test Table for jrd15 MP AberDock BitTorrent Tracker Website

| **Ref**     | **Description**                              | **Action** | **Expected result** | **Pass** | **Notes** |
|-------------|----------------------------------------------|------------|---------------------|----------|-----------|
|T-01         | Does the login form log the user in?         | Fill in the username box with "testAccount" and the password box with "testPassword". Then click "Log in". | The user should be logged in and directed to the browse page. | Yes | User is authenticated. |
|T-02         | Does the "Don't have an account?" link on the login page direct to the registration page? | Click the "Don't have an account?" link. | The user should be redirected to the registration page. | Yes | User is redirected to the correct page. |
|T-03         | 