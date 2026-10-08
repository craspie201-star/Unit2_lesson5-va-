# Easy Steps to Chinese 1 – Unit 2: Bài tập & trò chơi

Trang web học tiếng Trung dạng bài tập kết hợp trò chơi cho giáo trình 《轻松学中文》*Easy Steps to Chinese 1*, **Unit 2: Lesson 5 (年龄 – Tuổi tác) + Lesson 6 (电话号码 – Số điện thoại)**.

Toàn bộ sản phẩm là **một file HTML duy nhất** (HTML + CSS + JavaScript thuần), không cần cài đặt, không gọi mạng, chạy được offline.

## Demo

Mở file `index.html` bằng Chrome, Edge hoặc Safari. Khi đưa lên GitHub Pages, bạn sẽ có một đường link để gửi cho học sinh.

## Tính năng

- **2 bản đồ bài học** (Bài 5, Bài 6), mỗi bản đồ có 7 màn, mở khóa tuần tự. Màn cuối là Boss tổng ôn.
- **Boss chung 60 giây** cho cả Unit, tính điểm theo số câu đúng và combo.
- **Không có bài nghe**: mọi câu hỏi dựa trên việc nhìn và đọc.
- **Giao diện tiếng Việt**: hiển thị chữ Hán, pinyin có dấu thanh và nghĩa tiếng Việt. Có nút bật/tắt pinyin.
- **Hai chế độ**: Luyện tập (không mất tim) và Thử thách (3 tim mỗi màn).
- **Ôn lại câu sai** ngay sau mỗi màn.
- **Nhập tên học sinh**: nhiều học sinh dùng chung một máy, mỗi người có điểm riêng.
- **Báo cáo điểm**: tổng hợp cả lớp trên máy và chi tiết từng màn, có nút sao chép để gửi giáo viên.
- **Làm lại từ đầu** cho từng học sinh, hoặc xóa dữ liệu cả máy.
- Giao diện responsive, hỗ trợ cảm ứng, chế độ sáng/tối theo hệ thống.

## Các màn chơi

| Bài | Màn | Nội dung |
|---|---|---|
| 5 | 1 | Từ mới (nối cặp, chọn nghĩa, đúng/sai) |
| 5 | 2 | Chọn pinyin đúng |
| 5 | 3 | Hỏi tuổi (多大 / 几岁) |
| 5 | 4 | Ngày tháng, thứ trong tuần (lịch tháng 9/2006) |
| 5 | 5 | Ghép câu |
| 5 | 6 | Bộ thủ |
| 5 | 7 | Boss |
| 6 | 1 | Từ mới |
| 6 | 2 | Chọn pinyin đúng |
| 6 | 3 | Đọc số điện thoại (số 1 đọc là yāo), quy luật số |
| 6 | 4 | Nơi ở (住在哪儿) |
| 6 | 5 | Ghép câu |
| 6 | 6 | Bộ thủ và cấu trúc chữ |
| 6 | 7 | Boss |

## Cách tính điểm

- **Sao mỗi màn**: đúng từ 90% trở lên được 3 sao, từ 70% được 2 sao, từ 50% được 1 sao. Dưới 50% là chưa đạt và màn tiếp theo vẫn bị khóa. Ở chế độ Thử thách, hết tim cũng tính là chưa đạt.
- **XP**: mỗi câu đúng được 10 điểm, cộng thêm điểm thưởng khi trả lời đúng liên tiếp (tối đa thêm 10 điểm mỗi câu).
- **Boss tốc độ**: từ 60 điểm được 1 sao, từ 150 được 2 sao, từ 250 được 3 sao. Điểm cao nhất được lưu lại.
- **Huy hiệu**: "Chuyên gia hỏi tuổi" (3 sao Bài 5 màn 3), "Bậc thầy số điện thoại" (3 sao Bài 6 màn 3), "Siêu tốc Unit 2" (3 sao Boss chung).
- **Chuỗi ngày học** được tính theo ngày có hoàn thành ít nhất một màn.

## Cách chạy

### Chạy trên máy

1. Tải file HTML về, đổi tên thành `index.html`.
2. Nhấp đúp để mở bằng trình duyệt.

### Đưa lên GitHub Pages

1. Tạo repository mới trên GitHub.
2. Tải lên `index.html` và `README.md`.
3. Vào **Settings → Pages**, ở mục *Build and deployment* chọn **Deploy from a branch**, chọn nhánh `main` và thư mục `/ (root)`, bấm **Save**.
4. Sau 1–2 phút, trang có địa chỉ dạng `https://<tên-tài-khoản>.github.io/<tên-repo>/`.

> Gửi link thay vì gửi file qua Zalo. Zalo thường không mở được file `.html` trực tiếp trên điện thoại.

## Cấu trúc mã nguồn

Toàn bộ nằm trong `index.html`, phần `<script>` chia thành các khối:

| Khối | Nội dung |
|---|---|
| Dữ liệu | `W5`, `W6` (từ vựng), `RA5`, `RA6` (bộ thủ), `F5`, `F6` (câu điền khuyết), `S5`, `S6` (câu ghép), `ST` (cấu trúc chữ) |
| Bộ sinh câu hỏi | Đối tượng `G`: `vm`, `pm`, `tf`, `m`, `age`, `qa`, `cal`, `ph`, `seq`, `city`, `fl`, `rad`, `st`, `ord` |
| Định nghĩa màn chơi | Đối tượng `LV`: danh sách bộ sinh câu hỏi cho từng màn; `SG` cho Boss tốc độ |
| Lưu tiến độ | Đối tượng `DB` lưu trong `localStorage` với khóa `es1u2b` |
| Giao diện và điều khiển | `home`, `play`, `run`, `show`, `end`, `login`, `report` |

## Chỉnh sửa nội dung

- **Thêm hoặc sửa từ vựng**: sửa mảng `W5` / `W6` theo dạng `["chữ Hán", "pinyin", "nghĩa tiếng Việt"]`.
- **Thêm câu ghép**: thêm vào `S5` / `S6` theo dạng `[["từ1","từ2",...], "nghĩa tiếng Việt"]`.
- **Thêm câu điền khuyết**: thêm vào `F5` / `F6` theo dạng `["câu có ___", "đáp án đúng", ["đáp án nhiễu 1","2","3"]]`.
- **Đổi cấu trúc một màn**: sửa danh sách tên bộ sinh câu hỏi trong `LV`, ví dụ `["age","qa","fl"]`.
- **Đổi ngưỡng sao**: sửa các điều kiện `a>=.9`, `a>=.7`, `a>=.5` trong hàm `end`.
- **Đổi màu sắc**: sửa các biến CSS ở đầu file (`--red`, `--jade`, `--gold`, `--bg`...).

## Hạn chế hiện tại

- Điểm lưu trong trình duyệt của từng thiết bị. Giáo viên chỉ xem được báo cáo của máy mà học sinh đã dùng, nên cần học sinh gửi bản sao chép từ màn "Báo cáo điểm".
- Chưa có các dạng bài: lật thẻ Memory, điền dấu thanh, luyện nét viết, hỏi–đáp theo tranh.
- Ghép câu dùng cách bấm chọn từ, chưa hỗ trợ kéo thả.
- Nếu mở file trực tiếp từ bộ nhớ điện thoại, một số trình duyệt không lưu được tiến độ. Nên mở qua đường link.

## Nguồn nội dung

Từ vựng, mẫu câu, bộ thủ và dữ kiện lịch được lấy từ giáo trình *Easy Steps to Chinese 1* (Unit 2, Lesson 5 và 6, trang 30–45). Đây là dự án học tập; bản quyền nội dung giáo trình thuộc về tác giả và nhà xuất bản.

## Giấy phép

Bạn tự chọn giấy phép cho mã nguồn (ví dụ MIT) và thêm file `LICENSE` vào repository.
