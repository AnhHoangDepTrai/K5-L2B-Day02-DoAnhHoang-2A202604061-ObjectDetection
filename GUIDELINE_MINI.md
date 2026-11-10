# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | xe 4 đến tối đa khoảng 9 chỗ ngồi | Nhỏ gọn|
| `truck` | xe vận chuyển hàng hóa, vật liệu, gồm cabin riêng và thùng chở hàng phía sau| Có thùng xe chở hàng tách biệt hoặc liền khối|
| `bus` | Phương tiện giao thông cỡ lớn| Kích thước rất lớn, nhiều cuawr sổ|
| `van` | có khoang chở người hoặc chở hàng nguyên khối| Thiết kế hình hộp, tối ưu hóa không gian chứa đồ|

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Khung giới hạn phải ôm trọn toàn bộ vật thể một cách khít khao nhất có thể
- Vật thể bị che khuất: box thường sẽ bám sát phần ranh giới của phần vật thể còn đang hiển thị
- Vật thể bị cắt bởi rìa ảnh: Cạnh của box sẽ chạm đúng mép biên của bức ảnh tại điểm vật thể bị cắt ngang, các cạnh còn lại vẫn tiếp tục bám sát biên thực tế của vật thể bên trong khung hình
- Vật thể rất nhỏ/mơ hồ: vật thể quá nhỏ, hoặc bị mờ, nhòe, không thể nhận diện rõ hình thù hay ranh giới để phân biệt với nền, thông thường sẽ không vẽ box

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_004` | Hai xe taxi màu đỏ/cam chạy gần nhau ở giao lộ ban đêm | Gán mỗi xe một box riêng, lớp `car` nếu hình dáng là xe con; không tạo lớp taxi | Schema phân loại theo loại xe, không theo dịch vụ. Xe gần nhau vẫn là hai vật thể riêng. |
| `drive_028` | Taxi bị nhòe chuyển động và cắt bởi mép trái ảnh | Nếu phần nhìn thấy đủ nhận diện là ô tô, gán `car` và vẽ box quanh phần nhìn thấy, chạm mép ảnh; không ước lượng phần nằm ngoài khung | Xe bị cắt khung vẫn gán khi nhận diện được; chỉ bỏ qua mảnh quá nhỏ hoặc không thể xác định chắc lớp. |
| `drive_030` | Nhiều xe sát/chồng lấp nhau; có xe buýt lớn và các xe thân hộp giống van/minivan | Vẽ box riêng cho từng xe nhận diện được; xe buýt lớn là `bus`. Chỉ gán `van` khi nhận diện rõ kiểu van/minivan; trường hợp không phân biệt chắc với `car` thì ghi lại và hỏi giảng viên, không đoán | Mỗi xe là một box. Phân lớp theo schema; van/minivan mơ hồ không được tự chọn lớp. |
