# BÁO CÁO KIỂM THỬ API

**Tên Dự Án:** Kiểm thử API hệ thống quản lý người dùng (Reqres.in)  
**Ngày Kiểm Thử:** 02/06/2026  
**Người Kiểm Thử:** Nguyễn Văn Trường  

---

## 1. Mục Tiêu Kiểm Thử
Sử dụng công cụ Postman để kiểm thử các phương thức HTTP (GET, POST) trên một hệ thống API thực tế nhằm đánh giá khả năng phản hồi và xử lý lỗi của máy chủ.

## 2. Môi Trường Kiểm Thử
* **Công cụ:** Postman (Desktop/Web App)
* **Nền tảng:** Môi trường kiểm thử giả lập ([https://reqres.in](https://reqres.in))

## 3. Phương Pháp Kiểm Thử
Kiểm thử thủ công (Manual Testing) thông qua việc xây dựng các kịch bản gọi API trên phần mềm Postman.

---

## 4. Các Kịch Bản Kiểm Thử

### Kịch Bản Lần 1: Lấy danh sách người dùng (Thành công)
* **Tên Kịch Bản:** Kiểm thử cơ bản của 1 URL lấy dữ liệu
* **Mục Đích:** Test khả năng hoạt động của URL và phương thức GET để lấy danh sách người dùng ở trang số 2.
* **Phương Thức HTTP:** `GET`
* **URL:** `https://reqres.in/api/users`
* **Tham Số:** `page=2`
* **Kết Quả Mong Đợi:** Gửi yêu cầu thành công, Server trả về mã 200 OK và danh sách người dùng.
* **Kết Quả Thực Tế:** Đã gửi yêu cầu thành công, nhận đúng cấu trúc dữ liệu JSON.
* **Trạng Thái:** Thành công (200 OK)

**Ảnh minh họa kết quả:** <img width="1106" height="724" alt="image" src="https://github.com/user-attachments/assets/7a121dba-39dd-417a-8e7f-44b06f3b3767" />


**Chi tiết JSON phản hồi (rút gọn):**

    {
        "page": 2,
        "per_page": 6,
        "total": 12,
        "data": [
            {
                "id": 7,
                "email": "michael.lawson@reqres.in",
                "first_name": "Michael",
                "last_name": "Lawson"
            }
        ]
    }

---

### Kịch Bản Lần 2: Thêm người dùng mới (Thành công)
* **Tên Kịch Bản:** Kiểm thử truyền dữ liệu lên Server
* **Mục Đích:** Test khả năng tạo mới một bản ghi người dùng thông qua phương thức POST và Body JSON.
* **Phương Thức HTTP:** `POST`
* **URL:** `https://reqres.in/api/users`
* **Dữ liệu truyền vào (Body - raw JSON):** `{"name": "Truong", "job": "Developer"}`
* **Kết Quả Mong Đợi:** Yêu cầu được chấp nhận, Server tạo mới thành công và trả về mã 201 Created cùng ID.
* **Kết Quả Thực Tế:** Yêu cầu thành công, nhận được phản hồi chứa thông tin vừa tạo và thời gian tạo.
* **Trạng Thái:** Thành công (201 Created)

**Ảnh minh họa kết quả:** <img width="856" height="706" alt="image" src="https://github.com/user-attachments/assets/83385fc0-33df-42c5-87fb-25275d017938" />


**Chi tiết JSON phản hồi:**

    {
        "name": "Truong",
        "job": "Developer",
        "id": "153",
        "createdAt": "2026-06-02T07:15:20.123Z"
    }

---

### Kịch Bản Lần 3: Tìm kiếm người dùng không tồn tại (Thất bại)
* **Tên Kịch Bản:** Kiểm thử URL với ID không hợp lệ
* **Mục Đích:** Kiểm tra cách Server xử lý ngoại lệ khi Client yêu cầu một tài nguyên không tồn tại.
* **Phương Thức HTTP:** `GET`
* **URL:** `https://reqres.in/api/users/999`
* **Tham Số:** Không có (Truyền ID 999 trực tiếp vào URL)
* **Kết Quả Mong Đợi:** Máy chủ xử lý lỗi đúng cách và trả về mã lỗi 404 Not Found.
* **Kết Quả Thực Tế:** Hệ thống phản hồi lỗi 404 với thân trang (body) trống.
* **Trạng Thái:** Không thành công (404 Not Found)

**Ảnh minh họa kết quả:** <img width="1091" height="709" alt="image" src="https://github.com/user-attachments/assets/f78d68b3-1777-402b-b294-23c99433b73c" />


**Chi tiết phản hồi:** *(Body trả về rỗng {})*

---

## 5. Tổng Kết Kết Quả Kiểm Thử
Tóm tắt kết quả kiểm thử các tính năng của hệ thống API Reqres.in:

* **Số lượng kịch bản đã kiểm thử:** 3
* **Số lần thành công (20x):** 2
* **Số lần thất bại (40x):** 1
* **Tỉ lệ hoạt động đúng logic:** 100% (Cả 3 trường hợp API đều phản hồi chính xác theo tiêu chuẩn REST).

## 6. Phát Hiện Lỗi
Chi tiết về lỗi phát hiện được trong quá trình kiểm thử (Từ Kịch bản 3):

* **ID Lỗi:** 404 Not Found
* **Mô Tả Lỗi:** Truy vấn thông tin của một người dùng không tồn tại trong Database (ID = 999).
* **Mức Độ Ảnh Hưởng:** Không (Hệ thống bắt lỗi tốt, không gây Crash Server).
* **Ghi Chú/Đề Xuất:** API xử lý lỗi chuẩn mực.
