# 🛠️ Hướng dẫn cài đặt

## Yêu cầu đã cài đặt NodeJS

### Bước 1

Tải về phiên bản mới nhất của tool tại đây ⬇️

### Bước 2

Giải nén tool

### Bước 3

Tại thư mục tool vừa giải nén (thư mục có chứa file `package.json`), chạy lệnh sau để cài đặt các thư viện bổ trợ:

```bash
npm install
```

### 💾 Dữ liệu cần chỉnh sửa để chạy tool

- **Tổng số lần chạy**: Tìm biến `COUNT = 200` đổi thành số thích hợp.
- **Số BNB chuyển qua để claim + chuyển token về ví vệ tinh**: Tìm biến `AMOUNT_SEND = "0.000001"` đổi thành số phù hợp, thường dao động từ `0.0000001` đến `0.00000011` tuỳ thời giá.
- **Private key của ví vệ tinh** (ví chứa BNB mạng Matchain để chia gas cho các ví): Tìm biến `PRIVATE_KEY = "XXX"` đổi `XXX` thành private key của bạn.
- **Địa chỉ (mạng Matchain) của ví vệ tinh** hoặc bất kỳ ví nào bạn muốn gom token về: Tìm biến `PARENT_WALLET_ADDRESS = "YYY"` đổi `YYY` thành địa chỉ ví của bạn.

### >_ Các lệnh và chức năng tương ứng

| **Lệnh**          | **Chức năng**                                                     |
|-------------------|-------------------------------------------------------------------|
| `npm run start`    | Dùng để chạy tạo ví, chia gas, claim, gom token, nói chung là tất cả công việc trong một |

### 🕹️ Các tính năng có trong tool

- Tự động tạo ví
- Tự động chia gas vào ví vừa tạo
- Tự động claim token LOL
- Tự động chuyển token về ví vệ tinh chỉ định
- Bỏ qua khi lỗi

---

### ⚠️ **Warning**

- Nếu lâu lâu gặp lỗi thì kệ nó, đông người claim mạng bị nghẽn thôi.
- **BNB** dùng để chia gas (phí mạng lưới) phải thuộc mạng **Matchain**, không phải mạng **BSC**.
- Địa chỉ ví gom token phải là địa chỉ ví của **mạng Matchain**.
- Ước tính với $1 giá trị BNB sẽ claim được tầm 100,000,000 token LOL, chơi bao nhiêu là quyền của bạn.
- Hãy coi việc claim LOL như mua tờ vé số, vốn hoá mà được 10M$ thì về bờ, 100M$ thì x10,... cứ thế tính lên. Chơi tầm chục đô cho vui thôi, đừng ham đấm nhiều nhé 😉.

---

### ♾ **Cài đặt đa luồng**

Tool không chạy đa luồng do cơ chế claim token chạy đa luồng dễ gặp lỗi mạng. Chạy $1 mất gần 12h nhé.

- **Muốn chạy nhanh**: sao chép tool ra nhiều bản, nhưng nhớ phải đổi cả ví vệ tinh (ví chia gas). Nếu chạy 2 tool mà chung một ví cũng sẽ gặp lỗi. Ví dụ: chạy 5 bản thì chia tiền vào 5 ví để chạy.
