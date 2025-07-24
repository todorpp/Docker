# Docker lab 2

About the code:
1. Imports Express and body-parser modules to create a web server and handle form data.

2. Sets a default course goal using a variable: userGoal = 'Learn Docker!'.

3. 3Uses body-parser middleware to parse form submissions.

4. Serves static files (like styles.css) from the public folder.

5. Handles GET request at /:

6. Sends an HTML page with the current goal.

7. Includes a form to submit a new goal.

8. Handles POST request at /store-goal:

9. Reads the submitted goal from the form.

10. Updates the userGoal variable.

11. Redirects back to the main page.

12. Starts the server on port 80.

-----------------------------------------
After image is build execute with

docker run -p [port]:80 [image name]  
