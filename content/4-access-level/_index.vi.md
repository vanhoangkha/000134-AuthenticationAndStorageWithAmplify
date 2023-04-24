---
title : "Cấp Độ Truy Cập"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 4. </b> "
---
Khi tải tệp lên S3 bucket, chúng ta có 3 cấp độ truy cập là *public*, *protected* và *private*:

- **Public**: Tất cả người dùng ứng dụng của bạn có thể truy cập. Các tệp được lưu trữ dưới đường dẫn chung/trong bộ chứa S3 của bạn.
- **Protected**: Tất cả người dùng có thể đọc nhưng chỉ người dùng tạo mới có thể ghi. Các tệp được lưu trữ trong protected/{user_identity_id}/ trong đó user_identity_id tương ứng với ID nhận dạng Amazon Cognito duy nhất cho người dùng đó.
- **Private**: Chỉ có thể truy cập cho người dùng cá nhân. Các tệp được lưu trữ trong private/{user_identity_id}/ trong đó user_identity_id tương ứng với ID nhận dạng Amazon Cognito duy nhất cho người dùng đó.

Trong phần này chúng ta sẽ thay đổi quyền của người dùng để tải tệp lên S3.

1. Truy cập vào bảng điều khiển của [Cognito]()

2. Chọn **Federated Identities** ở menu phía bên trái. Sau đó chọn **fcjdms..._identitypool_...**

![Cognito](/images/4-access-level/4-access-level-1.png?featherlight=false&width=90pc)

3. Ấn **Edit identity pool**

![Cognito](/images/4-access-level/4-access-level-2.png?featherlight=false&width=90pc)

4. Ghi lại tên của **Authenticated role**

![Cognito](/images/4-access-level/4-access-level-3.png?featherlight=false&width=90pc)

5. Mở bảng điều khiển của [IAM]()
- Chọn **Roles** ở menu phía bên trái
- Nhập tên của **Authenticated role** và ấn vào role tìm thấy

![Cognito](/images/4-access-level/4-access-level-4.png?featherlight=false&width=90pc)

6. Mở rộng các policy để xem quyền của user

![Cognito](/images/4-access-level/4-access-level-5.png?featherlight=false&width=90pc)

{{% notice note %}}
Bạn có thể thấy quyền thêm, xoá và lấy object trong S3 bucket đối với thư mục *identity_id* trong thư mục *protected*
{{% /notice %}}

7. Chọn policy **Protected_policy_...**
    - Ấn nút **Remove**

![Cognito](/images/4-access-level/4-access-level-6.png?featherlight=false&width=90pc)

8. Nhập tên của policy và ấn **Delete**

![Cognito](/images/4-access-level/4-access-level-7.png?featherlight=false&width=90pc)

9. Bạn đã xoá thành công.

![Cognito](/images/4-access-level/4-access-level-8.png?featherlight=false&width=90pc)

10. Quay lại với ứng dụng, ấn **Add files** và chọn tệp bạn muốn tải lên. Sau đó ấn **Upload**

![Cognito](/images/4-access-level/4-access-level-9.png?featherlight=false&width=90pc)

11. Màn hình vẫn báo thành công, nhưng bạn hãy xem lỗi ở chế độ **Inspect | Console**. Chúng ta đã nhận được lỗi **Access Denied**.

![Cognito](/images/4-access-level/4-access-level-10.png?featherlight=false&width=90pc)

12. Thêm lại quyền cho người dùng.
- Ấn **Add permissions**
- Chọn **Create inline policy** 

![Cognito](/images/4-access-level/4-access-level-11.png?featherlight=false&width=90pc)

13. Chọn service là **S3**

![Cognito](/images/4-access-level/4-access-level-12.png?featherlight=false&width=90pc)

14. Tại mục **Actions | Read**, chọn quyền **GetObject**

![Cognito](/images/4-access-level/4-access-level-13.png?featherlight=false&width=90pc)

15. Tại mục **Actions | Write**, chọn quyền **PutObject** và **DeleteObject**

![Cognito](/images/4-access-level/4-access-level-14.png?featherlight=false&width=90pc)

16. Tại mục **Resources**, ấn **Add ARN**

![Cognito](/images/4-access-level/4-access-level-15.png?featherlight=false&width=90pc)

17. Ấn **List ARNs manually**

![Cognito](/images/4-access-level/4-access-level-16.png?featherlight=false&width=90pc)

18. Nhập ARN: `arn:aws:s3:::fcjdmsstore101547-dev/protected/${cognito-identity.amazonaws.com:sub}/*`
- Ấn **Add**

![Cognito](/images/4-access-level/4-access-level-17.png?featherlight=false&width=90pc)

19. Ấn **Review policy**

![Cognito](/images/4-access-level/4-access-level-18.png?featherlight=false&width=90pc)

20. Nhập tên cho policy: `Protected_policy`. Sau đó ấn **Create policy**

![Cognito](/images/4-access-level/4-access-level-19.png?featherlight=false&width=90pc)

21. Quay lại ứng dụng web, tải lại tệp mà bạn vừa thất bại
- Ấn **Add files**, chọn tệp muốn tải
- Ấn **Upload**

![Cognito](/images/4-access-level/4-access-level-20.png?featherlight=false&width=90pc)

24. Mở bảng điều khiển của S3 bucket xem tệp đã tải thành công hay chưa.

![Cognito](/images/4-access-level/4-access-level-21.png?featherlight=false&width=90pc)

Chúng ta đã tìm hiểu về mức độ truy cập *protected*. Nếu bạn muốn thêm quyền cho các mức độ hay chỉnh sửa quyền nào thì có thể làm tương tự.






