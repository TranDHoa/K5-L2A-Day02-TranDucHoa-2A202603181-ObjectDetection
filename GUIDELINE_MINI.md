# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Là phương tiện đường bộ có động cơ, thường có 4 bánh, chủ yếu dùng để chở người, có khoang hành khách và khu vực chứa hành lý | Bao gồm sedan, SUV, taxi và xe bán tải. Thường có thân xe nhỏ hoặc vừa.|
| `truck` | Là phương tiện đường bộ có động cơ, được thiết kế chủ yếu để vận chuyển hàng hóa, thường có cabin phía trước và thùng hoặc khu vực chở hàng phía sau. | Thường to hơn từ thân đến đuôi xe thường xe có thùng và khoang để trở hàng |
| `bus` | Là phương tiện đường bộ có động cơ, được thiết kế để vận chuyển nhiều hành khách, thường có thân xe dài, nhiều cửa sổ và nhiều hàng ghế ngồi. | Bao gồm xe buýt và minibus chở khách. Cao và to hơn các xe khác, từ đầu đến cuối sẽ chỉ chở khách thường có led hiển thị số xe |
| `van` |Là phương tiện đường bộ có động cơ, thường có 4 bánh, thân xe tương đối cao và khoang phía sau được sử dụng để chở người hoặc hàng hóa. | Xe van gần giống xe car nhưng van thường có tổng cộng 6 cửa sổ ở hai bên thân xe |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Là 4 cạnh của box sát với vật nhất có thể không để hở mặt đường, trời hay xe bên cạnh
- Vật thể bị che khuất: Vẫn gắn box quanh phần nhìn thấy với nhãn tương ứng, nếu bị che khuất quá không thể xác định được lớp thì hỏi giảng viên.
- Vật thể bị cắt bởi rìa ảnh: Vẫn gắn box quanh phần nhìn thấy với nhãn tương ứng, nếu phần nhìn thấy không thể xác định được lớp thì hỏi giảng viên.
- Vật thể rất nhỏ/mơ hồ: Nếu chỉ còn mảnh rất nhỏ, không thể xác định chắc lớp, không tự đoán. Ghi vào guideline và hỏi giảng viên.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_001` | Xe bị che bởi cột | Vẫn gán nhãn | Bị che nhưng mà vẫn có thể xác định được đó thuộc lớp car |
| `drive_005` | Xe bị cắt bởi rìa ảnh | Vẫn gán nhãn | Bị che nhưng mà vẫn có thể xác định được đó thuộc lớp car |
| `drive_006` | Xe ở xa bị che và rất mờ | Không gán nhãn | Vật thể rất nhỏ/mơ hồ |
