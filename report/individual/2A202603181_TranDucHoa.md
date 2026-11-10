# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên: Trần Đức Hòa
- MSSV:2A202603181
- Email:26ai.hoatd@vinuni.edu.vn
- Lớp:L2A
- Link repo bài làm:https://github.com/TranDHoa/K5-L2A-TranDucHoa-2A202603181-Day02-ObjectDetection
- Link Colab đã chạy:https://colab.research.google.com/drive/1efMUS2Afi4x5Fxt-HYGevpOBs4Ygi_Nt#scrollTo=YwQn5Ncgm6z-

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md]. Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train:50
- Kết quả checker và lỗi đã xử lý:Kết quả checker thành công
- Danh sách ít nhất 10 ảnh đã rà bằng mắt:
drive_001,drive_002,drive_003,drive_005,drive_006,drive_008,drive_009,drive_011,drive_012,drive_015
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa:
+ Sửa box có chứa quá nhiều mặt đường: kéo cho khít nhất và sát nhất với vật
+ Xe chưa có box: bổ sung thêm box
- Commit khóa nhãn ban đầu:

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP | 506 | |
| FP | 329 | |
| FN | 147 | |
| Precision | 0.606 | |
| Recall | 0.7749 | |
| F1 | 0.6801 | |
| mean_iou_of_matches | 0.8525 | |
| passed | false | |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch: T4-GPU
- Các tham số thay đổi so với notebook nếu có và lý do: không có
- Đường dẫn best checkpoint trong phiên chạy:
/content/Day2-Lab/outputs/yolo26_runs/vehicle_annotation/weights/best.pt

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision | 0.3156193471665181 |
| Recall | 0.30664893617021277 |
| mAP50 | 0.2739647516429376 |
| mAP50–95 | 0.20063156304965743 |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?

Lớp bus thấp nhất với recall là 0.Ảnh drive_002

2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box?

Cần kiểm tra độ chính xác vị trí kích thước bounding box

3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét?

Lỗi id class của gold label, id chuẩn phải theo thứ tự là car, van, truck, bus theo thứ tự 0, 1, 2, 3 trong đáp án ground true. Tôi đã thử đổi theo id đó và được kết quả là f1 = 0.832, mean_iou_of_matches = 0.8605.

4. Vì sao không dùng 10 ảnh eval để train? Vai trò validation của chúng trong notebook là gì?

50 ảnh train được sử dụng để cập nhật trọng số mô hình, còn 10 ảnh eval dùng để validation, theo dõi metrics và lựa chọn best.pt.
Nếu đưa 10 ảnh eval vào train, sẽ xảy ra rò rỉ dữ liệu giữa hai tập, khiến kết quả đánh giá không còn độc lập với dữ liệu học.
Ngoài ra, do tập eval được dùng để chọn best.pt, nó cũng không phải test set độc lập hoàn toàn.

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
| Gán nhãn | Sự nhầm lẫn giữa van và car | Đổi nhãn | OK |

## 7. Tự đánh giá theo rubric

Đối chiếu [RUBRIC.md](../../RUBRIC.md): phần nào đã có kết quả, phần nào còn thiếu hoặc chưa kiểm được. Không tự nhận hoàn thành bước chưa chạy.

## 8. Công cụ AI và tài liệu tham khảo

Ghi công cụ đã dùng, dùng ở bước nào và phần đã tự kiểm tra; không dùng thì ghi rõ. Liệt kê nguồn ngoài repo được sử dụng. Không ghi mật khẩu/token hoặc đính kèm gold train.

Viết báo cáo và đọc tài liệu có sử dụng chat gpt
