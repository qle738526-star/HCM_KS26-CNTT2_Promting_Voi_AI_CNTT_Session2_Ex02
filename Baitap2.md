**Phần 1: Phân tích vấn đề**

Các dòng bị phân loại sai trong bảng dữ liệu gồm: 1, 2, 4 và 5\.

Lý do phân loại sai dựa trên số lượng ví dụ mẫu (Examples):

* **Dòng 1:** Câu lệnh chỉ đưa ra yêu cầu và dữ liệu đầu vào, không chứa ví dụ mẫu nào. Phân loại đúng là Zero-shot, không phải Few-shot.

* **Dòng 2:** Câu lệnh chỉ có yêu cầu xử lý văn bản, hoàn toàn không cung cấp ví dụ tham khảo. Phân loại đúng là Zero-shot, không phải One-shot.

* **Dòng 4:** Câu lệnh cung cấp cụ thể 3 ví dụ mẫu (Mẫu 1, Mẫu 2, Mẫu 3\) trước khi đưa ra Input. Cấu trúc có từ 2 ví dụ trở lên phải là Few-shot, không phải Zero-shot.

* **Dòng 5:** Câu lệnh chỉ nêu định hướng viết lại email, không đính kèm đoạn văn bản mẫu nào để định hình kết quả. Phân loại đúng là Zero-shot, không phải Few-shot.

**Phần 2: Hoàn thiện bảng**

| STT | Nội dung Câu lệnh (Prompt) | Phân loại hiện tại | Phân loại đúng | Số lượng ví dụ mẫu nhận diện được |
| :---- | :---- | :---- | :---- | :---- |
| 1 | "Phân loại đánh giá sau là Tích cực hay Tiêu cực: 'Pin dùng được nửa ngày là hết'." | Few-shot | Zero-shot | 0 |
| 2 | "Hãy viết hoa tiêu đề sau theo phong cách công nghệ." | One-shot | Zero-shot | 0 |
| 3 | "Đổi thông số sau: 'RAM 16GB'. Mẫu: 'RAM 8GB' \-\> 'Đa nhiệm mượt mà mở 20 tab'." | One-shot | One-shot | 1 |
| 4 | "Phân loại cảm xúc: Mẫu 1: 'Hàng tốt' \-\> Pos. Mẫu 2: 'Giao trễ' \-\> Neg. Mẫu 3: 'Bình thường' \-\> Neu. Input: 'Máy đẹp nhưng sạc chậm' \-\> ?" | Zero-shot | Few-shot | Nhiều (3 ví dụ) |
| 5 | "Viết lại email thông báo bảo hành xong cho khách theo giọng điệu lịch sự." | Few-shot | Zero-shot | 0 |
| 6 | "Dịch mã lỗi sang tiếng Việt. Ví dụ: 'Err\_404' \-\> 'Không tìm thấy trang'. Input: 'Err\_500' \-\> ?" | One-shot | One-shot | 1 |

