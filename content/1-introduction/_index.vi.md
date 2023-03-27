---
title : "Giới Thiệu Amplify"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
#### Tổng quan

Các thư viện Amplify open-source client cung cấp các use-case centric, opinionated, khai báo và giao diện dễ sử dụng trên các loại hoạt động khác nhau do đám mây cung cấp, cho phép các nhà phát triển web và di động dễ dàng tương tác với các phần phụ trợ của họ. Các thư viện này có thể được cung cấp bởi AWS cloud và cung cấp một mô hình pluggable có thể mở rộng để sử dụng các nhà cung cấp khác. Các thư viện có thể được sử dụng với cả các phụ trợ mới tạo bằng Amplify CLI và backend resource hiện có. 

Amplify mã nguồn mở cung cấp các sản phẩm sau để xây dựng các ứng dụng iOS, Android, Flutter, Web và React Native đầy đủ:

**Amplify CLI** - Định cấu hình tất cả các dịch vụ cần thiết để cung cấp năng lượng cho chương trình phụ trợ của bạn thông qua giao diện dòng lệnh đơn giản.
**Amplify Libraries** - Sử dụng thư viện case-centric client để tích hợp mã ứng dụng của bạn với phần phụ trợ bằng cách sử dụng giao diện khai báo.
**Amplify UI Components** - Thư viện giao diện người dùng cho React, React Native, Angular, Vue và Flutter.

#### Authentication với Amplify

Amplify sử dụng Amazon Cognito làm nhà cung cấp xác thực chính. Amazon Cognito là một dịch vụ thư mục người dùng mạnh mẽ xử lý đăng ký người dùng, xác thực, khôi phục tài khoản và các hoạt động khác. Trong hướng dẫn này, bạn sẽ tìm hiểu cách thêm xác thực vào ứng dụng của mình bằng Amazon Cognito và đăng nhập tên người dùng/mật khẩu.

#### Storage với Amplify

Mô-đun AWS Amplify Storage cung cấp một cơ chế đơn giản để quản lý nội dung người dùng cho ứng dụng của bạn trong các bộ chứa lưu trữ công khai, được bảo vệ hoặc riêng tư. Danh mục Lưu trữ đi kèm với hỗ trợ tích hợp cho Amazon S3.