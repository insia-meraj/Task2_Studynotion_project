# StudyNotion Edtech Project
It is a fully functional project with responsive design
# Pre-requisites:
1) Nodejs
2) MongoDB
3) Open the terminal, enter `npm i` to install all the dependencies
4) To launch the server, enter command `nodemon start`.

![home](https://github.com/insia-meraj/Task2_Studynotion_project/assets/142750155/4017f4e6-ce75-4d3e-b2ad-e5ddf560b5a2)

# To register the user:

![register](https://github.com/insia-meraj/Task2_Studynotion_project/assets/142750155/24d4be26-579a-4074-831f-02a00093d1cb)

1) Click on signup button on the top right corner.
2) Enter your details and click submit.As soon as the user clicks on submit, the form data containing username, email, password and confirm password is sent to the server via request object. 
At the serverside, we access the form data through the incoming request.body object.
Now first we check whether the password matches the confirm password, if it doesnot we send it back to the signup page, otherwise we moveon to the next step wherein we check if any user with the specified email ID exists or not, if it does, we send it back to the signup page, otherwise we moveon to the next step wherein we register the user. After which user.save() method is called before which due to our custom middleware which we have set in the user model our password gets encrypted using bcrypt library (using 10 salt rounds).

Because of password encryption, the password doesnot get exposed even if someone gets access to our database.
# To Login the user:
![Login](https://github.com/insia-meraj/Task2_Studynotion_project/assets/142750155/12d54ebd-fa01-4c73-abae-b00b7f38b77c)
1) Click on Sign in button on the top right corner.
2) Enter your details and click submit.

As soon as the user clicks on submit the form data containing email and password is sent to the server via request object. 
At the serverside, we access the form data through the incoming request.body object.
Now first we check if any user with the specified email ID exists or not, if it doesnot, we send it back to the signin page, otherwise we moveon to the next step wherein we check if the password matches or not using bcrypt.compare() method,which compares the password from the request object with the encrypted password which we have saved in our database and returns true or false respectively. If it returns true then we send a cookie from the server side.
After this the user gets redirected to the profile page, before which we extract the user from request.cookies.
# To log out
1) Click on Log out button on the top right corner.
As soon as the user clicks on Logout button we simply remove the cookie from the request object and redirect the user to the sign in page.
# To Contact us
![Contactform](https://github.com/insia-meraj/Task2_Studynotion_project/assets/142750155/77dd03a0-835f-4c10-9ffe-55301dd29a24)


1) Click on Contact us button on the top right corner.


