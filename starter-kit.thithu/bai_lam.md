# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** PHẠM NGỌC DUY
- **Lớp:** HN-KS26-CNTT3
- **Link repository:** https://github.com/Phamduy2206/HN-KS26-CNTT3_Nhap-mon-CNTT_ThiThu.git
- **Hệ điều hành (Windows/macOS):** windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> pwd
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> Get-ChildItem -Force -Recurse
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> mv .\nhap_hang.txt ".\docs"
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> mv .\logo_van_phong_pham.png ".\media"
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> cp .\media\logo_van_phong_pham.png ".\backup"
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> rm .\temp_131.tmp
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website\logs> Get-ChildItem -Recurse
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website\logs> cd ..
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> Get-ChildItem -Force -Recurse
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
  Directory: C:\starter-kit\starter-kit.thithu\van-phong-pham-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026   8:50 AM                backup
d-----        10/23/2026   8:44 AM                data
d-----        10/23/2026   8:49 AM                docs
d-----        10/23/2026   8:44 AM                logs
d-----        10/23/2026   8:49 AM                media
-a----        10/19/2026   9:41 AM             78 .env


    Directory:
    C:\starter-kit\starter-kit.thithu\van-phong-pham-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png


    Directory:
    C:\starter-kit\starter-kit.thithu\van-phong-pham-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6105 don_ban_thang_10.xlsx


    Directory:
    C:\starter-kit\starter-kit.thithu\van-phong-pham-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM             51 nhap_hang.txt


    Directory:
    C:\starter-kit\starter-kit.thithu\van-phong-pham-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           1053 shop.log


    Directory:
    C:\starter-kit\starter-kit.thithu\van-phong-pham-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> cd logs
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website\logs> Get-Content .\shop.log | Select-String "ERROR"
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website\logs> Get-Content .\shop.log | Select-String "ERROR" > .\daily_report.txt
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> .\auto_report.ps1
```

### Nội dung file logs/auto_report.txt

```text
=== BAO CAO LOI ===

2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi

```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> (Get-Content .\logs\shop.log | Select-String "ERROR").Count
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
6
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> "=== TONG HOP LOG ===" > .\logs\tong_hop.txt
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> Get-Content .\logs\shop.log | Select-String "WARNING" >> .\logs\tong_hop.txt
PS C:\starter-kit\starter-kit.thithu\van-phong-pham-website> (Get-Content .\logs\shop.log | Select-String "ERROR").Count >> .\logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===

2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham


6

```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
