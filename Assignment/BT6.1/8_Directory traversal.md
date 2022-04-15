# Challenge: Directory traversal
## Người làm:   
    Nguyễn Ngọc Trưởng - 19522440
    Thời gian:
## Link: 
    https://www.root-me.org/en/Challenges/Web-Server/Directory-traversal

- Thử thách cho chúng ta những trang, trong những trang có danh sách các hình ảnh, có thể đây là liệt kê các file ảnh có trong thư mục
<p align="center"><img src="./images/8.1.png"></p>

- Đọc bài tham khảo đính kèm trong challenge, https://www.root-me.org/fr/Documentation/Web/Directory-traversal, ta thấy bài này là liệt kê các file có trong thư mục, thư mục này được truyền vào bởi tham số galerie
<p align="center"><img src="./images/8.2.png"></p>

- Ta thử show thư mục hiện tại bằng giá trị `galerie=.` thì ta thấy ở đây có các forder khác nhau, có 1 thư mục không được show lên trên thanh menu,
<p align="center"><img src="./images/8.3.png"></p>

- ta thử vào đó với giá trị `galerie=86hwnX2r`, vì nó hiển thị không đầy đủ nên ta cần xem source code (crlt U)
<p align="center"><img src="./images/8.4.png"></p>

- Ta thấy thư mục hiện tại có file passwo... ta xem source code
<p align="center"><img src="./images/8.5.png"></p>

- Vì này là một tệp tin nên ta cũng không thể truyền vào tham số cho galerie. ta click vào link trong source code này, để truy cập vào file, khi đó ta nhận được password.
<p align="center"><img src="./images/8.6.png"></p>

## Kết quả password là `kcb$!Bx@v4Gs9Ez`