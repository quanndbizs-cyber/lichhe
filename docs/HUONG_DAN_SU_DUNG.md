# Hướng dẫn sử dụng Bảng sao mùa hè

Tài liệu này tổng hợp các tính năng hiện có của project Bảng sao mùa hè. Ứng dụng dùng để ghi nhận hoạt động hằng ngày, cộng hoặc trừ sao, bố mẹ duyệt và phản hồi, sau đó dùng sao đã được duyệt để đổi thưởng.

## 1. Truy cập ứng dụng

Mở trình duyệt và truy cập URL nơi app được cài đặt.

Ví dụ khi chạy dưới subfolder mặc định:

```text
http://<IP_MAY_CHU>/lich-he-test/
```

Nếu server được cấu hình chạy ở domain hoặc đường dẫn khác, dùng URL tương ứng do người quản trị cung cấp.

## 2. Đăng nhập

Ứng dụng có 2 loại đăng nhập:

- Đăng nhập cho con: dùng để xem bảng sao, ghi nhận hoạt động, đổi thưởng và sửa task trong ngày hiện tại.
- Đăng nhập bố mẹ: dùng để xem bảng sao, thao tác như con, đồng thời có thêm quyền duyệt, like, comment, sửa, xóa hoạt động/phần thưởng và xem audit.

Mật khẩu mặc định đang được cấu hình trong `app/config.php`:

- Bố mẹ: `1234`
- Con: `1234`

Khi vận hành thật, nên cấu hình qua biến môi trường:

- `PARENT_PASSWORD`
- `CHILD_PASSWORD`

## 3. Dashboard tổng quan

Khu vực đầu trang hiển thị:

- Số sao hiện có.
- Tổng sao đã nhận.
- Tổng sao đã đổi.
- Danh hiệu hiện tại.
- Số sao hôm nay.
- Số sao tuần này.
- Số sao tháng này.
- Phần thưởng gần đạt nhất.
- Thanh tiến độ tới mốc thưởng tiếp theo.
- Số sao còn thiếu để đạt phần thưởng tiếp theo.

Lưu ý về cách tính sao:

- Dashboard và điều kiện đổi thưởng chỉ tính các hoạt động đã được bố mẹ duyệt với trạng thái `OK`, `Good` hoặc `Excellent`.
- Hoạt động đang `Chờ duyệt` chưa được tính vào tổng sao dùng để đổi thưởng.
- Hoạt động bị duyệt `NG` không được tính sao nếu đó là hoạt động cộng sao.
- Các mục trừ sao vẫn là sao âm theo dữ liệu ghi nhận.

## 4. Ghi nhanh trong 1 chạm

Khu vực `Ghi nhanh trong 1 chạm` dùng để nhập hoạt động nhanh trong ngày.

Cách dùng:

1. Chọn ngày áp dụng.
2. Chọn loại hoạt động.
3. Chọn hoạt động cụ thể thuộc loại đã chọn.
4. Chọn mục trừ sao nếu có.
5. Upload ảnh minh chứng.
6. Nhập ghi chú nếu cần.
7. Bấm `Lưu ghi nhanh`.

Ràng buộc hiện có:

- Chỉ được lưu cho ngày hiện tại.
- Không được lưu ngày quá khứ hoặc tương lai.
- Ảnh minh chứng là bắt buộc với ghi nhanh.
- Ảnh hợp lệ gồm JPEG, PNG, WebP.
- Dung lượng ảnh tối đa là 5MB.
- Một ngày chỉ được ghi tối đa 12 hoạt động.
- Có thể ghi một hoạt động cộng sao, một mục trừ sao, hoặc cả hai trong cùng lần ghi nhanh.

## 5. Ghi nhận thành tích hôm nay

Khu vực `Ghi nhận thành tích hôm nay` hiển thị danh sách hoạt động của ngày hiện tại.

Mỗi dòng có thể hiển thị:

- Icon theo loại hoạt động.
- Tên hoạt động.
- Loại hoạt động.
- Thời gian ghi nhận.
- Trạng thái duyệt của bố mẹ.
- Ghi chú.
- Số sao được hiển thị.
- Ảnh minh chứng nếu có.

Con hoặc bố mẹ có thể sửa task đã nhập trong ngày hiện tại:

- Sửa tên hoạt động.
- Sửa ghi chú.
- Bấm `Sửa task` để lưu.

Không thể sửa task của ngày cũ bằng form dành cho con.

## 6. Bảng nhận sao

App có sẵn các hoạt động cộng sao:

| Hoạt động | Sao |
| --- | ---: |
| Học ban ngày 2 giờ từ thứ 2 đến thứ 6 | +2 |
| Đọc sách | +1 |
| Chép kinh | +1 |
| Viết truyện | +1 |
| Viết nhật ký | +1 |
| Tập thể dục / vận động | +1 |
| Vẽ tranh / sáng tạo | +1 |
| Việc nhà được giao | +1 |
| Tưới cây / chăm cây | +1 |
| Cho cá ăn / chăm bể cá | +1 |
| Dọn bàn học, phòng ngủ | +1 |
| Không vượt thời gian màn hình | +1 |

Các mục trừ sao màn hình:

| Hoạt động | Sao |
| --- | ---: |
| Chơi 1 giờ YouTube/TV/Game | -3 |
| Chơi 2 giờ YouTube/TV/Game | -10 |

Các loại hoạt động hiện có:

- Học tập.
- Đọc sách.
- Viết lách.
- Vận động.
- Sáng tạo.
- Việc nhà.
- Cây & cá.
- Trừ sao màn hình.
- Thưởng thêm.
- Khác.

## 7. Thêm hoạt động nâng cao

Khu vực `Thêm hoạt động nâng cao` dùng khi hoạt động không nằm trong danh sách ghi nhanh hoặc cần nhập số sao riêng.

Cách dùng:

1. Chọn ngày.
2. Nhập tên hoạt động.
3. Chọn loại hoạt động.
4. Nhập số sao.
5. Upload ảnh minh chứng nếu có.
6. Nhập ghi chú nếu cần.
7. Bấm `Lưu hoạt động`.

Ràng buộc:

- Chỉ lưu cho ngày hiện tại.
- Một ngày tối đa 12 hoạt động.
- Ảnh không bắt buộc ở form nâng cao.
- Nếu upload ảnh, ảnh phải là JPEG, PNG hoặc WebP và không quá 5MB.

## 8. Đổi thưởng

Khu vực `Đổi thưởng` cho phép dùng sao hiện có để đổi phần thưởng.

Cách dùng:

1. Chọn ngày đổi.
2. Chọn phần thưởng.
3. App tự điền số sao cần dùng.
4. Nhập ghi chú nếu cần.
5. Bấm `Đổi thưởng`.

Ràng buộc:

- Chỉ đổi thưởng cho ngày hiện tại.
- Không đổi được nếu số sao hiện có chưa đủ.
- Khi đổi thành công, số sao dùng sẽ được trừ khỏi số sao hiện có.

Danh sách phần thưởng mặc định:

| Phần thưởng | Sao cần dùng |
| --- | ---: |
| Hoạt động gia đình | 20 |
| 1 quyển truyện | 25 |
| 1 cây nhỏ | 25 |
| Phần thưởng tự chọn bất kỳ | 35 |
| Về ngủ chơi nhà bà nội | 50 |

## 9. Lịch sử thành tích

Khu vực `Lịch sử thành tích` hiển thị tối đa 30 hoạt động gần nhất.

Thông tin hiển thị gồm:

- Ngày áp dụng.
- Thời gian ghi nhận.
- Icon.
- Loại hoạt động.
- Tên hoạt động.
- Số sao.
- Ghi chú.
- Ảnh minh chứng.
- Phản hồi bố mẹ.
- Thao tác sửa/xóa nếu bố mẹ đã đăng nhập.

Trên mobile, bảng lịch sử được làm gọn để dễ xem hơn. Khi xoay ngang màn hình mobile, các cột phản hồi bố mẹ và thao tác được mở lại để bố mẹ có thể duyệt, like, comment, sửa và xóa trực tiếp.

Nếu có ảnh minh chứng, bấm vào ảnh để mở preview phóng to. Có thể đóng preview bằng nút đóng, bấm ra ngoài ảnh hoặc nhấn phím `Esc`.

## 10. Bố mẹ duyệt và phản hồi hoạt động

Sau khi đăng nhập quyền bố mẹ, trong lịch sử thành tích sẽ có form phản hồi cho từng hoạt động.

Bố mẹ có thể:

- Chọn trạng thái duyệt.
- Like hoạt động.
- Nhập comment nhận xét.
- Lưu phản hồi.

Các trạng thái duyệt:

| Trạng thái | Ý nghĩa |
| --- | --- |
| Chờ duyệt | Hoạt động mới ghi, chưa được tính vào dashboard |
| NG | Không đạt, hoạt động cộng sao không được tính sao |
| OK | Đạt, được tính sao |
| Good | Tốt, được tính sao |
| Excellent | Xuất sắc, được tính sao |

Khi bố mẹ đổi trạng thái, like hoặc lưu comment:

- App lưu bằng AJAX, không reload toàn trang.
- Dashboard được cập nhật lại ngay.
- Số sao hiển thị của hoạt động được cập nhật ngay nếu trạng thái ảnh hưởng tới cách tính.
- Dòng phản hồi dùng cho bản in cũng được cập nhật.

## 11. Bố mẹ sửa hoặc xóa dữ liệu

Khi đăng nhập quyền bố mẹ:

- Có thể sửa tên hoạt động và ghi chú của từng hoạt động trong lịch sử.
- Có thể xóa hoạt động.
- Khi xóa hoạt động có ảnh, file ảnh tương ứng trong `public/uploads/` cũng được xóa.
- Có thể xóa lịch sử đổi thưởng.

Các thao tác tạo, sửa, xóa và duyệt được ghi vào audit log.

## 12. Lịch sử đổi thưởng

Khu vực `Lịch sử đổi thưởng` hiển thị tối đa 30 lần đổi thưởng gần nhất.

Thông tin gồm:

- Ngày đổi.
- Tên phần thưởng.
- Số sao đã dùng.
- Ghi chú.
- Nút xóa nếu bố mẹ đã đăng nhập.

## 13. Nhật ký audit cho bố mẹ

Khi đăng nhập quyền bố mẹ, app hiển thị khu vực `Nhật ký audit cho bố mẹ`.

Khu vực này mặc định được thu gọn. Bấm vào tiêu đề để mở.

Audit log hiển thị tối đa 50 dòng gần nhất, gồm:

- Thời gian.
- Người thực hiện.
- Hành động.
- Loại dữ liệu.
- Nội dung chi tiết.

Các thao tác được ghi audit gồm:

- Thêm hoạt động.
- Ghi nhanh hoạt động.
- Sửa task bởi con.
- Sửa hoạt động bởi bố mẹ.
- Bố mẹ cập nhật phản hồi và trạng thái duyệt.
- Xóa hoạt động.
- Đổi thưởng.
- Xóa đổi thưởng.

## 14. Di chuyển nhanh trên trang

App hỗ trợ di chuyển nhanh:

- Nhấn phím `Home` để lên đầu trang.
- Nhấn phím `End` để xuống cuối trang.
- Dùng nút nổi mũi tên lên/xuống ở góc dưới bên phải màn hình.

Khi đang nhập trong ô input, textarea hoặc select, phím `Home` và `End` giữ hành vi mặc định của trình duyệt để không ảnh hưởng thao tác nhập liệu.

## 15. Danh hiệu

Danh hiệu được tính theo số sao hiện có:

| Sao hiện có | Danh hiệu |
| ---: | --- |
| Từ 300 sao | Công chúa mùa hè |
| Từ 200 sao | Nhà sáng tạo |
| Từ 100 sao | Siêu chăm chỉ |
| Từ 50 sao | Mầm xanh |
| Dưới 50 sao | Chim non |

## 16. In ấn

Giao diện có hỗ trợ chế độ in:

- Các khu vực thao tác không cần thiết được ẩn khi in.
- Nội dung phản hồi của bố mẹ vẫn được hiển thị ở dạng text.
- Card và bảng được tối ưu để không bị vỡ bố cục quá nhiều.

## 17. Dữ liệu và lưu trữ

Dữ liệu chính:

```text
database/summer.db
```

Ảnh upload:

```text
public/uploads/
```

Các bảng dữ liệu chính:

- `activities`: hoạt động, sao, loại, ghi chú, ảnh, trạng thái duyệt, phản hồi bố mẹ.
- `rewards`: lịch sử đổi thưởng.
- `audit_logs`: nhật ký thao tác.

## 18. Cấu hình thường dùng

Các cấu hình chính nằm trong `app/config.php`.

Những mục thường cần chỉnh:

- `app_version`: phiên bản hiển thị ở footer và màn hình đăng nhập.
- `public_base_path`: đường dẫn public khi app chạy trong subfolder, mặc định lấy từ biến môi trường `PUBLIC_BASE_PATH` hoặc `/lich-he-test`.
- `parent_password`: mật khẩu bố mẹ, ưu tiên biến môi trường `PARENT_PASSWORD`.
- `child_password`: mật khẩu con, ưu tiên biến môi trường `CHILD_PASSWORD`.
- `activity_categories`: danh sách loại hoạt động.
- `activity_options`: danh sách hoạt động cộng sao.
- `penalty_options`: danh sách hoạt động trừ sao.
- `reward_options`: danh sách phần thưởng.
- `max_upload_size`: dung lượng upload tối đa.
- `allowed_upload_types`: định dạng ảnh được phép upload.

## 19. Backup

Dữ liệu cần backup:

- File SQLite trong `database/summer.db`.
- Toàn bộ ảnh trong `public/uploads/`.

Có thể dùng script:

```bash
scripts/backup.sh
```

Hoặc backup thủ công:

```bash
tar -czf backup/sao-he-$(date +%F).tar.gz database/summer.db public/uploads
```

## 20. Ghi chú vận hành

- App phù hợp chạy trong LAN gia đình.
- Nếu public ra Internet, nên bổ sung bảo vệ ở tầng web server như HTTPS, Basic Auth, giới hạn IP hoặc cơ chế xác thực mạnh hơn.
- Nên đổi mật khẩu mặc định trước khi dùng thật.
- Nên backup định kỳ database và thư mục upload.
- Nếu đổi đường dẫn public của app, cần cập nhật `PUBLIC_BASE_PATH` hoặc `public_base_path` để ảnh và CSS load đúng.
