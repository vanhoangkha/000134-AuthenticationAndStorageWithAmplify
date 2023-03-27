---
title : "Dọn Dẹp Tài Nguyên"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
1. Làm rỗng S3 bucket
- Mở bảng điều khiển của [S3](https://s3.console.aws.amazon.com/s3/buckets?region=ap-southeast-2)
- Chọn bucket **fcjdmsstore...-dev**
- Ấn nút **Empty**
- Nhập **permanently delete** và ấn **Empty**

2. Chạy câu lệnh dưới đây
```
amplify delete
```
