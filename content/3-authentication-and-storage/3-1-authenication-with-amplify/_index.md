---
title : "Authentication with Amplify"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Run the following command at the root of the application you cloned to add authentication to the application:
```
amplify add auth
```
- Select follow the informations below:

    Do you want to use the default authentication and security configuration? *Default configuration*\
    Warning: you will not be able to edit these selections.\
    How do you want users to be able to sign in? *Username*\
    Do you want to configure advanced settings? *No, I am done*.

![CreateAuth](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-1.png?featherlight=false&width=90pc)

2. Run the following command to update cloud resources:
```
amplify push
```

![CreateAuth](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-2.png?featherlight=false&width=90pc)

3. Navigate to the CloudFormation console to check if the stack has been created.
- Click **id** of UserPool to open dashboard of **Cognito User Pool**

![CreateAuth](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-3.png?featherlight=false&width=90pc)

4. Run the following command to start the application: `npm start`
- Click **Sign up** to register a new account.

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-4.png?featherlight=false&width=90pc)

5. Enter user information:
- Username, for example: `admin`
- Enter your email.
- Password, for example: `Admin123`
- Click **Sign up**

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-5.png?featherlight=false&width=90pc)

6. Navigate to Cognito User Pool console, select**User** tab you will see a registered but unconfirmed user

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-6.png?featherlight=false&width=90pc)

7. Open your email to get the verification code that was sent automatically.

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-7.png?featherlight=false&width=90pc)

8. Enter the verification code into the app and click **Submit**

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-8.png?featherlight=false&width=90pc)

9. Navigate to Cognito User Pool console, click the **Refresh** icon and you will see that the user is confirmed

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-9.png?featherlight=false&width=90pc)

10. Log in to the app with the account you just registered with.

![Signin](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-10.png?featherlight=false&width=90pc)

11. Successful login.

![Signin](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-11.png?featherlight=false&width=90pc)

12. Select **My Profile** on the left menu, then click **Update profile**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-12.png?featherlight=false&width=90pc)

13. Enter old password, new password to update password. Then click **Update**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-13.png?featherlight=false&width=90pc)

14. Click **OK**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-14.png?featherlight=false&width=90pc)

15. Click **Sign out** to log out

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-15.png?featherlight=false&width=90pc)

16. Click **Sign in** to login again

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-16.png?featherlight=false&width=90pc)

17. Enter your account information after updating to log in, then click **Sign in**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-17.png?featherlight=false&width=90pc)

18. You have successfully signed in with your new account.

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-18.png?featherlight=false&width=90pc)