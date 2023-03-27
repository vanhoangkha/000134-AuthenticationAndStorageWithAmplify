---
title : "Serverless - Sử dụng Amplify Authentication và Storage"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Serverless - Sử dụng Amplify Authentication và Storage

### Tổng quan

Trong bài lần trước, chúng ta đã biết cách tạo và sử dụng Lambda function tương tác với DynamoDB. Tiếp theo trong series này, chúng ta sẽ sử dụng thư viện Amplify để xác thực người dùng bằng Amazon Cognito, upload tệp lên S3 bucket.

Kiến trúc của ứng dụng chúng ta sẽ xây dựng:

![WebArchitect](/images/amplify.png?featherlight=false&width=50pc)

### Nội dung

 1. [Giới thiệu](1-introduction/)
 2. [Chuẩn bị](2-preparation/)
 3. [Xác thực và Lưu trữ](3-authentication-and-storage/)
 4. [Cấp độ truy cập](4-access-level/)
 5. [Dọn dẹp tài nguyên](5-cleanup)