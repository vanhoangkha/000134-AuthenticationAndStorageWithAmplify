---
title : "Access Level"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
When uploading files to S3 bucket, we have 3 levels of access: *public*, *protected* and *private*:

- **Public**: Accessible by all users of your app. Files are stored under the public/ path in your S3 bucket.
- **Protected**: Readable by all users, but writable only by the creating user. Files are stored under protected/{user_identity_id}/ where the user_identity_id corresponds to the unique Amazon Cognito Identity ID for that user.
- **Private**: Only accessible for the individual user. Files are stored under private/{user_identity_id}/ where the user_identity_id corresponds to the unique Amazon Cognito Identity ID for that user.

In this section we will change the user permission to upload files to S3.

1. Open [Cognito console](https://ap-southeast-1.console.aws.amazon.com/cognito/v2/idp/user-pools?region=ap-southeast-1)

2. Select **Federated Identities** on the left menu. Then select **fcjdms..._identitypool_...**

![Cognito](/images/4-access-level/4-access-level-1.png?featherlight=false&width=90pc)

3. Click **Edit identity pool**

![Cognito](/images/4-access-level/4-access-level-2.png?featherlight=false&width=90pc)

4. Note down the name of the **Authenticated role**

![Cognito](/images/4-access-level/4-access-level-3.png?featherlight=false&width=90pc)

5. Open [IAM console](https://us-east-1.console.aws.amazon.com/iamv2/home?region=us-east-1#/home)
- Select **Roles** on the left menu
- Enter name of **Authenticated role** and click to searched role

![Cognito](/images/4-access-level/4-access-level-4.png?featherlight=false&width=90pc)

6. Expand policies to view user permissions

![Cognito](/images/4-access-level/4-access-level-5.png?featherlight=false&width=90pc)

{{% notice note %}}
You can see the permission to add, remove and get objects in the S3 bucket for the *identity_id* folder in the *protected* folder
{{% /notice %}}

7. Select **Protected_policy_...** policy
    - Click **Remove**

![Cognito](/images/4-access-level/4-access-level-6.png?featherlight=false&width=90pc)

8. Enter policy name and click **Delete**

![Cognito](/images/4-access-level/4-access-level-7.png?featherlight=false&width=90pc)

9. You have successfully removed.

![Cognito](/images/4-access-level/4-access-level-8.png?featherlight=false&width=90pc)

10. Back in the application, click **Add files** and select the file you want to upload. Then click **Upload**

![Cognito](/images/4-access-level/4-access-level-9.png?featherlight=false&width=90pc)

11. The screen still says success, but you should see the error in **Inspect | Console** mode. They received an **Access Denied** error.

![Cognito](/images/4-access-level/4-access-level-10.png?featherlight=false&width=90pc)

12. Re-add permissions for the user.
- Click **Add permissions**
- Select **Create inline policy**

![Cognito](/images/4-access-level/4-access-level-11.png?featherlight=false&width=90pc)

13. Select **S3** for service

![Cognito](/images/4-access-level/4-access-level-12.png?featherlight=false&width=90pc)

14. In **Actions | Read** section, select **GetObject**

![Cognito](/images/4-access-level/4-access-level-13.png?featherlight=false&width=90pc)

15. In **Actions | Write** section, select **PutObject** and **DeleteObject**

![Cognito](/images/4-access-level/4-access-level-14.png?featherlight=false&width=90pc)

16. In **Resources** secttion, click **Add ARN**

![Cognito](/images/4-access-level/4-access-level-15.png?featherlight=false&width=90pc)

17. Click **List ARNs manually**

![Cognito](/images/4-access-level/4-access-level-16.png?featherlight=false&width=90pc)

18. Enter ARN: `arn:aws:s3:::fcjdmsstore101547-dev/protected/${cognito-identity.amazonaws.com:sub}/*`
- Click **Add**

![Cognito](/images/4-access-level/4-access-level-17.png?featherlight=false&width=90pc)

19. Click **Review policy**

![Cognito](/images/4-access-level/4-access-level-18.png?featherlight=false&width=90pc)

20. Enter policy name: `Protected_policy`. Then click **Create policy**

![Cognito](/images/4-access-level/4-access-level-19.png?featherlight=false&width=90pc)

21. Go back to the web app, reload the file you just failed
- Click **Add files**, select the file you want to download
- Click **Upload**

![Cognito](/images/4-access-level/4-access-level-20.png?featherlight=false&width=90pc)

24. Open the console of the S3 bucket to see if the file has loaded successfully.

![Cognito](/images/4-access-level/4-access-level-21.png?featherlight=false&width=90pc)

We've learned about *protected* access levels. If you want to add permissions for other level or edit any permissions, you can do the same.
