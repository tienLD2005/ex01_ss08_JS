## 1. Phân tích lỗi và cách sửa

- Lỗi 1: Sai logic hàng đợi khi dùng pop
  - Đoạn mã sai: waitingQueue.pop()
  - Nguyên nhân: Hàm pop() lấy phần tử ở cuối mảng, làm cho xe đến sau lại được sạc trước
  - Cách sửa: Đổi thành waitingQueue.shift() để lấy đúng xe đến trước ở đầu mảng 

- Lỗi 2: Vượt biên mảng dẫn đến NaN
  - Đoạn mã sai: for (let i = 0; i <= completedSessionsKwh.length; i++)
  - Nguyên nhân: Điều kiện i <= length khiến vòng lặp truy cập vượt quá chỉ số mảng
  - Cách sửa: Sửa điều kiện lặp thành i < completedSessionsKwh.length.

## 2. Bảng Test Cases đối chứng

| STT | Trường hợp kiểm thử | Dữ liệu đầu vào | Kết quả sai thực tế | Kết quả đúng mong đợi |
| --- | --- | --- | --- | --- |
| TC01 | Điều phối xe vào sạc theo FIFO | waitingQueue = ['29A-112.33', '30E-889.12', '51K-678.99'] | Xe được điều phối vào sạc: 51K-678.99 | Xe được điều phối vào sạc: 29A-112.33 |
| TC02 | Tính tổng sản lượng điện và doanh thu | completedSessionsKwh = [45.2, 30.5, 62.8, 28.0], fastChargingRate = 4500 | Tổng sản lượng: NaN kWh, Tổng doanh thu: NaN VNĐ | Tổng sản lượng: 166.5 kWh, Tổng doanh thu: 749250 VNĐ |
