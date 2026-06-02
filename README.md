# BÁO CÁO KIỂM THỬ API

**Tên Dự Án:** Test Collection of APIs  
**Ngày Kiểm Thử:** 24/05/2024  
**Người Kiểm Thử:** Nguyễn Văn Trường - Đại học Phenikaa  

---

## 1. Mục Tiêu Kiểm Thử
Sử dụng công cụ Postman để thực hiện gửi các HTTP Request và kiểm thử cách một API thực tế phản hồi.

## 2. Môi Trường Kiểm Thử
* **Công cụ:** Postman
* **Nền tảng:** Môi trường Desktop/Web

## 3. Phương Pháp Kiểm Thử
Kiểm thử tự động và thủ công API endpoint thông qua phần mềm Postman.

---

## 4. Các Kịch Bản Kiểm Thử

### Kịch Bản 1: Kiểm thử cơ bản của 1 URL
* **Mục Đích:** Test khả năng hoạt động của URL và tính năng GET của Postman.
* **Phương Thức HTTP:** `GET`
* **URL:** `https://random-data-api.com/api/v2/users`
* **Tham Số:** `?size=2&is_xml=true`
* **Kết Quả Mong Đợi:** Gửi yêu cầu thành công, API trả về dữ liệu của 2 users.
* **Kết Quả Thực Tế:** Đã gửi yêu cầu thành công (Status 200 OK).
* **Trạng Thái:** ✅ Thành công

**Ảnh minh họa kết quả:** ![Kết quả Kịch bản 1](https://github.com/gtaAsian/New-Collection-of-APIs/assets/170786444/c340d30f-fea5-4f45-b752-369a1f066f80)

**Dữ liệu phản hồi (JSON):**
<details>
<summary>Click để xem chi tiết JSON</summary>

```json
[
    {  
        "id": 9209,
        "uid": "61b0ecef-a169-49c1-9b7e-616aebe82641",
        "password": "zWosu2p6UN",
        "first_name": "Davis",
        "last_name": "Hand",
        "username": "davis.hand",
        "email": "davis.hand@email.com",
        "gender": "Genderfluid",
        "date_of_birth": "1978-03-23"
    },
    {
        "id": 4506,
        "uid": "1f8ef347-e420-4e50-8b66-8cf92ab6ad74",
        "password": "RQpDo89cFw",
        "first_name": "Trent",
        "last_name": "Quitzon",
        "username": "trent.quitzon",
        "email": "trent.quitzon@email.com",
        "gender": "Genderqueer",
        "date_of_birth": "1999-03-10"
    }
]
