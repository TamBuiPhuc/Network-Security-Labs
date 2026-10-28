# Lab 03 - Task 2.3: MD5 Collision

## Mục tiêu
Thực hành tạo hai tệp có nội dung khác nhau nhưng cùng giá trị băm MD5 bằng công cụ md5collgen.

## Môi trường thực hành
- Google Colab (Linux)
- Python 3
- md5collgen v1.5

## Nội dung thực hiện
1. Tạo tiền tố có độ dài 20 byte, không phải bội số của 64.
2. Tạo tiền tố có độ dài chính xác 64 byte.
3. Sử dụng md5collgen để tạo hai tệp có cùng MD5.
4. Kiểm tra kết quả bằng các lệnh diff, cmp, md5sum và xxd.

## Hướng dẫn chạy
Tải và biên dịch công cụ:

```bash
git clone https://github.com/zhijieshi/md5collgen.git
cd md5collgen
make
```

Chạy công cụ với tệp tiền tố:

```bash
./md5collgen -p prefix.txt -o out1.bin out2.bin
```

Kiểm tra kết quả:

```bash
diff out1.bin out2.bin
cmp -l out1.bin out2.bin
md5sum out1.bin out2.bin
```

## Kết luận
Hai tệp có thể khác nhau về nội dung nhưng vẫn có cùng giá trị băm MD5, minh họa điểm yếu về tính kháng va chạm của thuật toán MD5.

## Nguồn công cụ
https://github.com/zhijieshi/md5collgen
