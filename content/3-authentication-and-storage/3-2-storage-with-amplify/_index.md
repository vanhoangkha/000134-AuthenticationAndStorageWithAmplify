---
title : "Storage with Amplify"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
After you have successfully created an account with Cognito User Pool, we will use that account to upload files to S3 bucket with Amplify in this section.

1. Press the combination **Ctrl+C** in terminal or command line

2. Run the below command at the root of the application you cloned to add authentication to the application:
```
amplify add storage
```
- Select and enter follow the below informations: 

    ? Please select from one of the below mentioned services: *Content (Images, audio, video, etc.)*\
    Provide a friendly name for your resource that will be used to label this cateogry in the project: `fcjdmsstore`\
    Provide bucket name: `fcjdmsstore`\
    Who should have access: *Auth users only*\
    What kind of access do you want for Authenticated user? *Ấn tổ hợp Ctrl + A*\
    Do you want to add a Lambda Trigger for your S3 Bucket? `no`

![CreateStorage](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-1.png?featherlight=false&width=90pc)

3. Run the following command to update cloud resources:
```
amplify push
```

![CreateStorage](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-2.png?featherlight=false&width=90pc)

4. Navigate to the CloudFormation console to check if the stack has been created.
- Click on a bucket's name to open the S3 bucket's dashboard

![CreateStorage](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-3.png?featherlight=false&width=90pc)

5. Run the following command to start the application: `npm start`
- Click **Upload**

![UploadFile](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-4.png?featherlight=false&width=90pc)

6. Click **Add files** and select the files you want to upload

![UploadFile](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-5.png?featherlight=false&width=90pc)

7. Add tags to files or can be omitted. Then press **Upload**

![UploadFile](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-6.png?featherlight=false&width=90pc)

8. You have successfully uploaded your files

![UploadFile](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-7.png?featherlight=false&width=90pc)

{{% notice note %}}
You may get an error message, click OK to ignore it because we have not set up the API for the application.
{{% /notice %}}

9. Back to the S3 bucket dashboard, check if the files have been uploaded.

![UploadFile](/images/3-2-storage-with-amplify/3-2-storage-with-amplify-8.png?featherlight=false&width=90pc)

You are done with user authentication and file upload to S3 with Amplify. The S3 bucket has created a **protected** folder because our application chooses **Access Level** as *protected*. To learn more about **Access Level**, go to the next section.