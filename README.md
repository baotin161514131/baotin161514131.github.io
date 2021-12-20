# Bài tập nhóm cuối kì - Nhập môn lập trình web - CT188 - CTU

## Các thành viên
    + Nguyễn Hữu Nhân
    + Mai Bảo Tín
    + Nguyễn Văn Minh

## Website bao gồm 11 trang 
    1. Trang chủ
    2. Giới thiệu
    3. Khuyến mãi
    4. Thực đơn
    5. Tuyển dụng
    6. Form tuyển dụng
    7. Dịch vụ
    8. Liên hệ
    9. Thanh toán
    10. Đăng kí
    11. Đăng nhập

## Phần HTML
    + Sử dụng các thẻ HTML 5 mới nhất 
    + Bố cục rõ ràng
    + Web tối giản, giao diện dễ hiểu không quá cầu kì mang đậm tính chất báng hàng

## Phần CSS
    + Website sử dụng các kĩ thuật chia bố cục phổ biến như GRID-LAYOUT và FLEX-LAYOUT
    + Có Animation thêm phần sinh động cho website
    + Có thiết kế WEB đáp ứng trên 2 thiết bị - Responsive
        + Trên máy tính bảng - Tablet - IPAD
        + Trên điện thoại thông minh - Mobile - Iphone 6/7/8plus
    + Thiết kế các file rõ ràng dễ dàng chỉnh sửa bảo trì
    + Các thành phần dùng chung của website được đưa vào 1 file để tái sử dụng
    + Các thành phần dùng chung như header, footer, button, form

## Phần JavaScript

### Các chức năng chính
    + Đăng kí
    + Đăng nhập
    + Hiển thị menu
    + Giỏ hàng
    + Trang thanh toán
    + Xử lí form nhập
    + Luôn hiển thị được số lượng của giỏ hàng tại thời điểm hiện tại

### Ưu điểm

- Hiển thị menu: đã hiển thị được menu từ tập dữ liệu thông tin các món ăn dạng JSON theo phân loại 
- Thay vì code HTML: thì chỉ cần render các món ăn từ file data.js nếu số lượng món lên đến hàng trăm
                    thì rõ ràng không thể ngồi code theo cách thủ công được 

```
const data = [{
        "name": "Cơm gà chiên xù",
        "price": "25000",
        "image": "/images/rice-chicken-1.jpg",
        "note": ["1 phần dưa chua", "  1 Phần cơm", "1 Phần gà"],
        "phanloai": "Cơm gà"
    }]
```

- Giỏ hàng: luôn được cập nhật mỗi khi được thêm, xóa và thay đổi số lượng món hàng, có thể xem ở mọi 
                trang ở icon 'giỏ hàng' trên phần header. Dữ liệu được lưu ở Local Storage. Chi tiết, một
                key tên 'Names' sẽ quản lí tên các món ăn trong giỏ hàng (do tên của món hàng là không 
                trùng nhau,sau này nên thêm vào id của mỗi món để dễ quản lí) và các key có tên là tên của 
                các món ăn. Sẽ lưu thông tin của từng món theo dữ liệu được thêm vào.

- Trang thanh toán giỏ hàng: Tại đây người dùng có thêm, chỉnh sửa số lượng và xóa món ăn hiện tại có trong 
                giỏ, sau đó giỏ hàng sẽ được cập nhật lại trên local storage và trên tất cả trang. Để tiến 
                hành thanh toán, người dùng cần nhập đầy đủ và đúng thông tin tại form đặt món.

- Xử lí form nhập: Đã xử lí chuỗi được kha khá các loại dữ liệu nhập như: số điện thoại, mật khẩu 
                (trên 8 kí tự),...Các input sẽ được kiểm tra vào báo lỗi ngay khi người dùng click
                 ra khỏi input đó hoặc bấm SUBMIT.

- Đăng nhập / Đăng kí: Đây chỉ là demo đăng kí, vì vốn dĩ quá trình đăng kí cần dc xử lí ở phía 
                backend để lưu vào cơ sở dữ liệu kiểm tra xác thực, mã hóa, giải mã, ...Việc sử dụng
                localStorage để lưu mật khẩu không qua mã hóa là sai về nguyên tắc bảo mật. Và ở đây, 
                trang chỉ lưu duy nhất người đăng kí gần nhất nhưng cũng đã có chức năng kiểm tra DB tài 
                khoản người dùng đã đăng kí. Khi đăng nhập nếu chưa đăng kí trước sẽ báo lỗi 'người dùng không tồn tại'.Đăng nhập thành công sẽ quay về trang chủ.