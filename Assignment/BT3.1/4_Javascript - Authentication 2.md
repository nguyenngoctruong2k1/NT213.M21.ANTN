# Javascript - Authentication 2
## Người làm:   
    Nguyễn Ngọc Trưởng - 19522440
## Link: 
    https://www.root-me.org/en/Challenges/Web-Client/Javascript-Authentication-2
- Giao diện web mở đầu, khi ta nhấn vào nút login thì hiển thị thông báo điền username, password.
<p align="center"><img src="./images/4_1.png"></p>

- Ta kiểm tra mã nguồn, ta thấy được trang tải mã javascript từ file login.js
<p align="center"><img src="./images/4_2.png"></p>

- Tiếp tục kiểm tra file login.js
<p align="center"><img src="./images/4_3.png"></p>

từ đây ta thấy username và password được kiểm tra với TheUsername và ThePassword. password được người dùng nhập cũng là password của challenge này. 
password = ThePassword = "GOD:HIDDEN".split(":")[1] = "HIDDEN" 

## Password là `HIDDEN`