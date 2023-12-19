# StudyNotion Edtech Project
# Pre-requisites:

1) Nodejs
2) MongoDB
3) Open the terminal, enter `npm i` to install all the dependencies
4) To launch the server, enter command `nodemon start`.

![Screenshot (15)](https://github.com/insia-meraj/Task2_Studynotion_project/assets/142750155/3d180f7d-40ae-4bf5-9a69-ee11154da607)


# To register the user:


1) Click on signup button on the top right corner.
2) Enter your details and click submit.


As soon as the user clicks on submit, the form data containing username, email, password and confirm password is sent to the server via request object. 
At the serverside, we access the form data through the incoming request.body object.
Now first we check whether the password matches the confirm password, if it doesnot we send it back to the signup page, otherwise we moveon to the next step wherein we check if any user with the specified email ID exists or not, if it does, we send it back to the signup page, otherwise we moveon to the next step wherein we register the user. After which user.save() method is called before which due to our custom middleware which we have set in the user model our password gets encrypted using bcrypt library (using 10 salt rounds).

Because of password encryption, the password doesnot get exposed even if someone gets access to our database.


# To Login the user:


1) Click on Sign in button on the top right corner.
2) Enter your details and click submit.



As soon as the user clicks on submit the form data containing email and password is sent to the server via request object. 
At the serverside, we access the form data through the incoming request.body object.
Now first we check if any user with the specified email ID exists or not, if it doesnot, we send it back to the signin page, otherwise we moveon to the next step wherein we check if the password matches or not using bcrypt.compare() method,



which compares the password from the request object with the encrypted password which we have saved in our database and returns true or false respectively. If it returns true then we send a cookie from the server side.



After this the user gets redirected to the profile page, before which we extract the user from request.cookies.



# To log out


1) Click on Log out button on the top right corner.


As soon as the user clicks on Logout button we simply remove the cookie from the request object and redirect the user to the sign in page.


# To Contact us


1) Click on Contact us button on the top right corner.


