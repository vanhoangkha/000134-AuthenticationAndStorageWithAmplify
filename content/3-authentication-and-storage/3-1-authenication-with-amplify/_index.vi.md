---
title : "Authentication với Amplify"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---
1. Chạy câu lệnh dưới đây tại thư mục gốc của ứng dụng mà bạn clone về để thêm authentication cho ứng dụng:
```
amplify add auth
```
- Chọn theo các thông tin dưới đây:

    Do you want to use the default authentication and security configuration? *Default configuration*\
    Warning: you will not be able to edit these selections.\
    How do you want users to be able to sign in? *Username*\
    Do you want to configure advanced settings? *No, I am done*.

![CreateAuth](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-1.png?featherlight=false&width=90pc)

2. Chạy câu lệnh sau để cập nhật tài nguyên trên cloud:
```
amplify push
```

![CreateAuth](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-2.png?featherlight=false&width=90pc)

3. Mở lại bảng điều khiển của CloudFormation để kiểm tra xem stack đã được tạo hay chưa. 
- Ấn vào **id** của UserPool để mở bảng điều khiển của **Cognito User Pool**

![CreateAuth](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-3.png?featherlight=false&width=90pc)

4. Chạy câu lệnh sau để bắt đầu với ứng dụng: `npm start`
- Ấn **Sign up** để đăng ký một tài khoản mới.

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-4.png?featherlight=false&width=90pc)

5. Nhập thông tin người dùng:
- Tên người dùng, ví dụ: `admin`
- Nhập email của bạn.
- Mật khẩu, ví dụ: `Admin123`
- Ấn **Sign up**

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-5.png?featherlight=false&width=90pc)

6. Mở lại bảng điều khiển của Cognito User Pool, chọn tab **User** bạn sẽ thấy một người dùng đã được đăng ký nhưng chưa xác nhận

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-6.png?featherlight=false&width=90pc)

7. Mở mail của bạn để lấy mã xác thực đã được gửi tự động.

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-7.png?featherlight=false&width=90pc)

8. Nhập mã xác nhập vào ứng dụng rồi ấn **Submit**

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-8.png?featherlight=false&width=90pc)

9. Mở lại bảng điều khiển của Cognito User Pool, ấn biểu tượng **Refresh** bạn sẽ thấy ngừoi dùng đã được xác thực

![Signup](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-9.png?featherlight=false&width=90pc)

10. Đăng nhập vào ứng dụng với tài khoản bạn vừa đăng ký.

![Signin](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-10.png?featherlight=false&width=90pc)

11. Bạn đã đăng nhập thành công.

![Signin](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-11.png?featherlight=false&width=90pc)

12. Chọn **My Profile** ở menu phía bên trái, sau đó ấn **Update profile**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-12.png?featherlight=false&width=90pc)

13. Nhập mật khẩu cũ, mật khẩu mới để cập nhật mật khẩu. Sau đó ấn **Update**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-13.png?featherlight=false&width=90pc)

14. Ấn **OK**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-14.png?featherlight=false&width=90pc)

15. Ấn **Sign out** để đăng xuất

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-15.png?featherlight=false&width=90pc)

16. Ấn **Sign in** để đăng nhập lại

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-16.png?featherlight=false&width=90pc)

17. Nhập thông tin tài khoản sau khi cập nhật để đăng nhập, sau đó ấn **Sign in**

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-17.png?featherlight=false&width=90pc)

18. Bạn đã đăng nhập thành công bằng thông tin mới.

![UpdateProfile](/images/3-1-authenication-with-amplify/3-1-authenication-with-amplify-18.png?featherlight=false&width=90pc)
