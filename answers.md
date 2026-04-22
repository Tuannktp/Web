Phần A:
    Câu A1(5đ) — HTTP & Browser

        Câu 1:5 Bước Chính từ DNS Lookup đến Render:
            Bước 1: DNS Lookup
                Trình duyệt chuyển đổi domain shopee.vn thành IP address của server thực tế
                Nguồn: tuan_1_html5/01_introduction_html_universe.md - Phần "1.2. HTTP — Ngôn  ngữ để Client và Server hiểu nhau" (liên quan đến kiến trúc Client-Server)
            Bước 2:Kết nối mạng & Gửi HTTP Request
                Request của bạn xuất phát từ laptop → qua router WiFi → qua ISP (nhà mạng) → chạy qua cáp quang xuyên đất → đến Data Center của Shopee
                Nguồn: tuan_1_html5/01_introduction_html_universe.md - Phần "Cuộc Hành Trình 0.3 Giây Xuyên Đại Dương":
            Bước 3:Server Xử lý & Gửi Response
                Server nhận request, xử lý logic (query database, chuẩn bị dữ liệu) → gửi trả file HTML, CSS, JavaScript
                Nguồn: tuan_1_html5/01_introduction_html_universe.md - 
            Bước 4:Browser Parse HTML/CSS/JS
                Chrome nhận file từ server
                Parse HTML: Đọc cấu trúc DOM (các phần tử, tags)
                Parse CSS: Đọc styling (màu sắc, bố cục, font)
                Execute JavaScript: Chạy logic tương tác
                Nguồn: tuan_1_html5/01_introduction_html_universe.md - Phần "1.3. Browser Rendering":
            Bước 5:Paint & Render (Hiển thị Giao diện)
                Browser vẽ trang web lên màn hình → Bạn thấy trang Shopee
                Nguồn: tuan_1_html5/01_introduction_html_universe.md - Phần "1.3. Browser Rendering":
    Câu 2:
        Các thông tin chính:
        Danh sách Requests - Tất cả HTTP requests được gửi:
            HTML files, CSS files, JS files
            Hình ảnh, fonts, media
            API calls (fetch requests)
        Response Status & Code:
            200 OK - Thành công
            404 Not Found - File không tìm thấy
            500 Server Error - Lỗi server
            Nguồn:(Theo tuan_1_html5/01_introduction_html_universe.md - phần HTTP Response Codes)
        Headers (Request & Response):
            Content-Type, User-Agent
            Authorization tokens
            Cache control info
            Response Body
        Data trả về từ server (JSON, HTML, CSS, etc.):
            Waterfall & Timing
            DNS Lookup time
            Connection time
            Request time
            Response time
            Nguồn:(Liên quan đến khái niệm "0.3 giây" trong tuan_1_html5/01_introduction_html_universe.md
            ![Ảnh screenshot](CauA1.png)
    Câu A2:
        Google Dùng AI/Bot Để "Đọc" Trang Web
        Google bot không nhìn trang web như con người
        Nó chỉ đọc HTML code để hiểu nội dung
        Nếu code dùng <div> ở khắp nơi → Bot không biết phần nào là gì.
        4 lỗi semantic:
        Lỗi 1: Dùng `<div class="header">` thay vì `<header>`
        Trước 
        <div class="header">
            <div class="logo">ShopTLU</div>
        </div>
        Sau 
        <header>
            <div class="logo">ShopTLU</div>
        </header>

        ---
        Lỗi 2: Dùng `<div>` thay vì `<nav>` cho menu
        Trước 
        <div class="menu">
            <div><a href="/">Trang chủ</a></div>
            <div><a href="/products">Sản phẩm</a></div>
        </div>
        Sau 
        <nav>
            <ul>
                <li><a href="/">Trang chủ</a></li>
                <li><a href="/products">Sản phẩm</a></li>
            </ul>
        </nav>
        ---
        Lỗi 3: Dùng `<div class="main">` thay vì `<main>`
        Trước 
        <div class="main">
            <div class="product">...</div>
        </div>

        Sau 
        <main>
            <article class="product">...</article>
        </main>

        ---
        Lỗi 4: Dùng `<div class="product">` thay vì `<article>`
        Trước
        <div class="product">
            <div class="title">iPhone 16 Pro</div>
            <div class="price">25.990.000đ</div>
            <div class="image"><img src="iphone.jpg"></div>
        </div>
        Sau 
        <article class="product">
            <h2>iPhone 16 Pro</h2>
            <p class="price">25.990.000đ</p>
            <figure>
                <img src="iphone.jpg" alt="iPhone 16 Pro">
                <figcaption>iPhone 16 Pro</figcaption>
            </figure>
        </article>
    Câu A3:
        <div>Hộp 1</div>	Kiểu:Block   
       -> Xuống dòng mới → chiếm cả dòng
        <span>Text A</span>	Kiểu:Inline	
       -> Nằm trên cùng dòng với phần tử inline kế tiếp
        <span>Text B</span>	Kiểu:Inline	
       -> Nằm cạnh Text A (cùng dòng)
        <div>Hộp 2</div>	Kiểu:Block	
       -> Xuống dòng mới → chiếm cả dòng
        <span>Text C</span>	Kiểu:Inline	
        ->Nằm trên cùng dòng với Text D
        <strong>Text D</strong>	Kiểu:Inline	
        ->Nằm cạnh Text C (cùng dòng)
        <div>Hộp 3</div>	Kiểu:Block	
        ->Xuống dòng mới → chiếm cả dòng.
    Câu A4:

        Sự khác nhau cơ bản:
        Element	    Vai Trò 	    Nội Dung	            Hiển Thị
        <thead>	    Đầu bảng	    Tiêu đề cột (header)	In đậm, nền xám
        <tbody>	    Thân bảng	    Dữ liệu chính	        Text bình thường
        <tfoot>	    Chân bảng	    Tổng kết, summary	    Có thể highlight
        Tại sao KHÔNG NÊN dùng table để tạo layout trang web?
            Lỗi 1: SEO Bị Suy Giảm Nghiêm Trọng
            Vấn đề:
                Table được thiết kế cho dữ liệu dạng bảng, không phải layout
                Google bot đọc table từ trái → phải, trên → dưới
                Nếu dùng table làm layout → nội dung bị xáo trộn khi bot đọc.
            Lỗi 2: Trang Web KHÔNG Responsive (Mobile Unfriendly)
            Vấn đề:
                Table có chiều rộng cố định từ thuộc tính width
                Trên mobile, table không thể scale down → user phải cuộn ngang
                CSS Grid/Flexbox có thể responsive dễ dàng    
            Lỗi 3: Code HTML Phức Tạp & Khó Bảo Trì
            Vấn đề:
                Table layout cần nhiều nested <tr><td> để tạo layout
                Mỗi khi thay đổi design → phải sửa cả HTML lẫn CSS
                Dễ gây lỗi alignment khi update.
    Phần B: 
        Bài 3:Debug html
            Lỗi 1: Dòng 1 — Thiếu khai báo kiểu tài liệu đầy đủ — Cách sửa: Sửa thành <!DOCTYPE html>.
            Lỗi 2: Dòng 2 — Thiếu thuộc tính ngôn ngữ cho thẻ html — Cách sửa: Sửa thành <html lang="vi">.
            Lỗi 3: Dòng 3 — Thẻ <title> chưa có thẻ đóng — Cách sửa: Thêm </title> sau chữ "Trang web".
            Lỗi 4: Dòng 4 — Giá trị charset không chuẩn và đặt sai vị trí (nên đặt đầu thẻ head) — Cách sửa: Sửa thành <meta charset="UTF-8">.
            Lỗi 5: Dòng 6 — Sai thẻ đóng cho tiêu đề <h1> — Cách sửa: Sửa <h1>Welcome to ShopTLU<h1> thành <h1>Welcome to ShopTLU</h1>.
            Lỗi 6: Dòng 10 — Thẻ <a> đầu tiên chưa đóng đúng — Cách sửa: Sửa <a> ở cuối dòng thành </a>.
            Lỗi 7: Dòng 10, 11 — Đường dẫn href thiếu phần mở rộng .html — Cách sửa: Sửa thành href="home.html" và href="products.html".
            Lỗi 8: Dòng 18 — Thẻ <img> thiếu thuộc tính alt và dấu ngoặc kép cho src — Cách sửa: Sửa thành <img src="iphone.jpg" alt="iPhone 16 Pro">.
            Lỗi 9: Dòng 20 — Đóng thẻ sai thứ tự (thẻ <b> đóng sau thẻ <p>) — Cách sửa: Sửa thành <p>Giá: <b>25.990.000đ</b></p>.
            Lỗi 10: Dòng 36 — Sử dụng thẻ <main> lần thứ hai (một trang web chỉ được có duy nhất một thẻ <main>) — Cách sửa: Thay thẻ <main> này thành thẻ <aside> vì đây là nội dung phụ (Sidebar).
