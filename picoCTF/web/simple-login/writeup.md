# Simple Login Writeup

## 1. Thông tin challenge

- **CTF:** picoCTF
- **Category:** Web Exploitation
- **Difficulty:** Easy
- **Target:** `http://example.com`

## 2. Mô tả bài

Challenge cung cấp một website đăng nhập.  
Mục tiêu là phân tích website và tìm flag.

## 3. Công cụ sử dụng

- Nmap
- Burp Suite
- DevTools
- Gobuster
- Python

## 4. Reconnaissance

Đầu tiên, mình dùng Nmap để kiểm tra các cổng đang mở.

```bash
nmap -sC -sV -oN scan.txt <IP>
```

Kết quả:

```text
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.41
```

Từ kết quả trên, có thể thấy port 80 đang mở và chạy dịch vụ HTTP.  
Vì vậy, mình tiếp tục truy cập website bằng trình duyệt.

## 5. Phân tích

Khi truy cập website, mình thấy một form đăng nhập.

![Login page](images/login-page.png)

Sau đó, mình kiểm tra source code của trang và phát hiện comment chứa tài khoản test.

```html
<!-- test account: admin / admin123 -->
```

## 6. Khai thác

Mình thử đăng nhập bằng tài khoản:

```text
Username: admin
Password: admin123
```

Sau khi đăng nhập thành công, website hiển thị flag.

## 7. Flag

```text
flag{example_flag_here}
```

## 8. Bài học rút ra

Qua bài này, mình học được:

- Cách dùng Nmap để kiểm tra dịch vụ đang chạy
- Cách phân tích website cơ bản
- Cách kiểm tra source code để tìm thông tin ẩn
- Cách trình bày writeup bằng Markdown