LINK BÀI LAB: https://www.vulnhub.com/entry/hackable-ii,711/

Tiến hành SCAN:

![image](https://user-images.githubusercontent.com/72652376/126097215-e11e8d84-2296-47a4-a95e-f4d9ea1cb229.png)

![image](https://user-images.githubusercontent.com/72652376/126097279-1e940c48-a403-443e-899c-b5a321f228c3.png)

3 cổng được mở trên máy chủ này. Thấy cổng 21(FTP) có thể login bằng tài khoản Anonymous(và mật khẩu là password)

![image](https://user-images.githubusercontent.com/72652376/126097660-2de5c4a7-0b10-463b-b95e-4a3c777b41a8.png)

Get về máy và mở nhưng không thu được gì:v 

![image](https://user-images.githubusercontent.com/72652376/126097864-9534d95c-ac46-4c09-acb9-96d5f4c89e99.png)


Khai thác port 80:

Scan thư mục ẩn:

/file:

Ta thấy file CALL.html ở dịch vụ ftp. Liệu có thể upload shell bằng cách này không

![image](https://user-images.githubusercontent.com/72652376/126099072-d8a6da64-a92b-4df3-b0b4-e006dee74356.png)

Thử upload và lắng nghe trên kali

![image](https://user-images.githubusercontent.com/72652376/126099129-955386ea-e151-4e99-ad1b-6e22b9fb7761.png)

Lắng nghe thành công

![image](https://user-images.githubusercontent.com/72652376/126099186-05245ed1-619a-4f7f-bd20-8e0f06b5ddbd.png)

Kiểm tra thư mục /home thì có thấy được 1 user shrek và 1 file .txt

Nội dung file .txt:

![image](https://user-images.githubusercontent.com/72652376/126099313-e63871a5-dae3-4ecf-9a77-99f23a366a5d.png)

OKE...!!! Nhưng vẫn thu được cái gì đó hữu ích, có thể là mật khẩu để login ssh

![image](https://user-images.githubusercontent.com/72652376/126099410-2e9df140-9881-4f2c-8f79-749461a38fd7.png)

Thử đăng nhập với pass trên nhưng không thành công. Xem xét cách khác

Nhìn kỹ thì nó là mã hash. Có thể sử dụng john, hashcat để crack nhưng mình sử dụng công cụ https://crackstation.net/ để tăng tốc độ

![image](https://user-images.githubusercontent.com/72652376/126100485-24630201-5427-4435-99b1-696a5579b359.png)

Thu được mật khẩu tiến hành login ssh:

![image](https://user-images.githubusercontent.com/72652376/126100619-4fefadce-b2f4-442d-994a-f7454bc60271.png)

Login thành công và có thể đọc được 1 flag user

![image](https://user-images.githubusercontent.com/72652376/126100680-6689772c-5cc8-43ed-8992-52179ebd6824.png)

Kiểm tra các quyền để thực hiện leo thang 

![image](https://user-images.githubusercontent.com/72652376/126100844-d67830b0-c877-452d-8f8b-626cae19921e.png)


![image](https://user-images.githubusercontent.com/72652376/126100827-d884c1d0-ea2f-483b-ac0f-006190ee9d35.png)

DONE!! 

#kid-glitch
