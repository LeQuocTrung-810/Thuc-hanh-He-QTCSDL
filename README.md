# Thuc-hanh-He-QTCSDL  
## THỰC HÀNH BUỔI 1  
### Bài 1: Cài đặt SQL-SERVER, tạo cơ sở dữ liệu Sinhvien  
### Bài 2: Thực hành về bảng dữ liệu (Table)  
1. Nêu các bước tạo Table bằng công cụ.  
2. Tạo bảng table có tên tb_Sinhvien bằng lệnh T-SQL với các cột dữ liệu như dưới đây trong
cơ sở dữ liệu Thuchanh  
![image](https://github.com/user-attachments/assets/301c3ee4-e8b9-4d37-bf44-422fe07d0f0b)  
3. Sử dụng lệnh T-SQL để nhập dữ liệu cho bảng tb_Sinhvien gồm 02 sinh viên có mã MaSV là  
01 và 02 cùng với các thông tin khác.  
![image](https://github.com/user-attachments/assets/986fbb8e-3977-4a7a-9f22-f9a2b5842b07)  
4. Sử dụng lệnh T-SQL để hiển thị thông tin của sinh viên có MaSV là 01  ![image](https://github.com/user-attachments/assets/b1e3efe3-57ae-4143-8d24-093c73cb48fd)  

5. Sử dụng lệnh T-SQL để xóa sinh viên có MaSV là 02  ![image](https://github.com/user-attachments/assets/ecd5be33-9bdf-461d-ae66-78b4e9ed9ca5)  
![image](https://github.com/user-attachments/assets/26a8fdeb-4dca-4b5b-bd27-33be284c3e58)  

6. Sử dụng lệnh T-SQL thêm cột Ghichu vào bảng tb_Sinhvien  ![image](https://github.com/user-attachments/assets/960b0b1f-2d72-4fc4-921c-19abf894c2ca)  
![image](https://github.com/user-attachments/assets/090ced68-fa04-4c5c-979d-eb87779ccb75)  

### Bài 3: Thực hành về bảng ảo (View)  
1. Nêu các bước tạo View bằng công cụ.
- Mở SSMS và kết nối đến CSDL.
- Mở phần DataBase => tb_SinhVien => view.
- Nhấp chuột phải vào views => New view.
- Chọn bảng cần tạo view => nhấn Add => Close.
- Chọn các cột cần hiển thị.
- Nhấn nút Save, đặt tên là v_SinhVien.
2. Sử dụng lệnh T-SQL để tạo ra View có tên là v_sinhvien để hiển thị toàn bộ các sinh viên trong bảng tb_sinhvien gồm các cột dữ liệu: MaSV, HoTen, Ngaysinh, GioiTinh, MaLop.
```
CREATE VIEW v_sinhvien AS
SELECT MaSV, HoTen, NgaySinh, GioiTinh, MaLop
FROM tb_Sinhvien;
```
3. Sử dụng lệnh T-SQL để hiển thị sinh viên có MaSV là 01 trong v_sinhvien  ![image](https://github.com/user-attachments/assets/1636abcd-0a1b-4388-9b26-a2d42756a6bb)  

4. Sử dụng lệnh T-SQL thêm cột HoKhau vào v_Sinhvien  ![image](https://github.com/user-attachments/assets/a81a6734-f717-4741-a447-6abd79b03579)  

5. Sử dụng lệnh T-SQL để xóa v_sinhven
```
DROP VIEW v_sinhvien;
```
### Bài 4: Thực hành về thủ tục lưu trữ (STORED PROCEDURE)
1. Nêu các bước tạo thủ tục bằng công cụ.
- Mở SSMS
2. Sử dụng lệnh T-SQL tạo ra thủ tục có tên là st_sinhvien từ bảng dữ liệu tb_sinhvien có tham số đầu vào Maso để hiển thị sinh viên có MaSV bằng Maso được truyền vào khi thực thi thủ tục.
```
CREATE PROCEDURE st_sinhvien
    @Maso NVARCHAR(10)
AS
BEGIN
    SELECT *
    FROM tb_Sinhvien
    WHERE MaSV = @Maso;
END;
```  
![image](https://github.com/user-attachments/assets/8c0bb87e-af18-4742-bcaf-a9d9d552e606)  

3. Sử dụng lệnh T-SQL để gọi và thực thi thủ tục st_sinhvien để hiển thị thông tin có MaSV là 01.
![image](https://github.com/user-attachments/assets/5177287e-026e-40d1-b2cd-e7d399879d1e)  

4. Sử dụng lệnh T-SQL để xóa thủ tục st_sinhvien.
```
Drop Procedure st_sinhvien
```
![image](https://github.com/user-attachments/assets/797cc7a1-fcce-4bb8-90cd-dd433d1da8a5)  
