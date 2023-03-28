---
title : "Chuẩn Bị"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2. </b> "
---
Chúng ta thực hiện các bước dưới đây để chuẩn bị cho việc xác thực và lưu tệp với thư viện Amplify trong phần sau:

1. Cài đặt Amplify CLI, chạy câu lệnh dưới đây:
```
npm install -g @aws-amplify/cli
```

{{% notice note %}}
Bạn phải cài đặt NodeJs trước khi cài đặt Amplify CLI\
Bạn nên tạo một user và cấu hình một AWS profile với thông tin xác thực trên máy của bạn.
{{% /notice %}}

2. Chạy các câu lệnh dưới đây để clone ứng dụng về máy của bạn:
```
git clone https://github.com/AWS-First-Cloud-Journey/FCJ-Serverless-DMS
cd FCJ-Serverless-DMS
npm install
```

3. Để khởi tạo Amplify cho ứng dụng, bạn chạy câu lệnh dưới đây từ thư mục gốc của ứng dụng: 
```
amplify init
```

- Nhập theo các thông tin dưới đây:

    ? Enter a name for the project `fcjdms`\
    The following configuration will be applied:

    Project information\
    | Name: fcjdms\
    | Environment: dev\
    | Default editor: Visual Studio Code\
    | App type: javascript\
    | Javascript framework: react\
    | Source Directory Path: src\
    | Distribution Directory Path: build\
    | Build Command: npm run-script build\
    | Start Command: npm run-script start

    ? Initialize the project with the above configuration? `Yes`\
    Using default provider  awscloudformation\
    ? Select the authentication method you want to use: `AWS profile`

    For more information on AWS Profiles, see:\
    https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html

    ? Please choose the profile you want to use default\
    ? Help improve Amplify CLI by sharing non sensitive configurations on failures (y/N) › `No`

6. Chạy câu lệnh dưới đây để cập nhật tài nguyên cloud:
`amplify push`

![AmplifyInit](/images/2-preparation/2-preparation-1.png?featherlight=false&width=90pc)

4. Mở bảng điều khiển của [CloudFormation](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/)
5. Chọn **Stacks** ở menu phía bên trái, bạn sẽ thấy stack mới được tạo. Ấn tab **Resources** bạn sẽ thấy các tài nguyên mà Amplify tạo

![AmplifyInit](/images/2-preparation/2-preparation-2.png?featherlight=false&width=90pc)
