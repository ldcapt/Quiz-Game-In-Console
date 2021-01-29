# Câu hỏi ôn tập

## Developer [Nguyễn Hoàng Anh](https://www.facebook.com/ldcapt/)

---

### 1. Lý thuyết hướng đối tượng có mấy tính chất?
- Tính trừu tượng
- Tính kế thừa
- Tính đa hình
- Tính đóng gói và che dấu dữ liệu

### 2. Tính trừu tượng hóa? Ví dụ?
- Loại bỏ hoặc không chú ý đến một số thuộc tính, phương thức dư thừa của đối tượng

- Ví dụ:
	+ Một `học sinh` có rất nhiều `đặc điểm` như: Màu tóc, màu mắt, màu da, ...
	+ Với bài toán `quản lý học sinh` thì những đặc điểm cần quan tâm chỉ là: *ngày sinh*, *quê quán*, *họ tên*, ...

### 3. Tính kế thừa, ví dụ?
- Là sự thừa hưởng các phương thức, thuộc tính của đối tượng con từ một đối tượng cha mà không cần phải khai báo

- Ví dụ:
```java
public abstract class TuGiac {
	// Khai bao thuoc tinh
	protected int canhA;
	protected int canhB;
	protected int canhC;
	protected int canhD;

	protected int tinhDienTich() {
	    // Nội dung phương thức	
	}

	protected void tinhChuVi() {
	    // Nội dung phương thức
	}
}
----------------------------------------
public class HinhVuong extends TuGiac {
	/**
	 * Hình vuông sẽ được kết thừa và sử dụng 
	 *
	 *  - Phương thức
	 *    tinhDienTich();
	 *    tinhChuVi();
	 *
	 *  - Thuộc tính
	 *    canhA
	 *    canhB
	 *    canhC
	 *    canhD
	 *
	 * của hình tứ giác mà không cần khai báo
	 */
}

```

### 4. Ghi đè phương thức là gì? Viết 1 class cha và 1 class con để minh họa?
(Ghi đè chỉ xuất hiện trong kế thừa)
- Định nghĩa lại phương thức trừu tượng đã được khai báo trong class cha được gọi là ghi đè
- Ví dụ minh họa
```java
public class TuGiac {
	int tinhDienTich();
    
	void tinhChuVi() {
	    // Nội dung phương thức
	}
}
----------------------------------------
public class HinhVuong extends TuGiac {
	@Override
	int tinhDienTich();
	
	@Override
	void tinhChuVi() {
	    // Nội dung phương thức
	    super.tinhChuVi();
	    // Tính chu vi tiếp    
	}
}
```
### 5. Nạp chồng phương thức là gì? Nêu ví dụ:
- Là các phương thức có tên giống nhau nhưng khác nhau về kiểu dữ liệu trả về hoặc số lượng các tham số.

```java
public class TuGiac {
	int tinhDienTich() {
	    // Nội dung phương thức
	}
    
	String tinhDienTich() {
	    // Nội dung phương thức
	}
}
```

### 6. Một lớp là lớp trừu tượng khi nào?
+ Bản thân lớp đó chứa các phương thức trừu tượng 
+ Khi đối tượng này không trực tiếp tham gia vào bài toán, nhưng được tạo ra để xây dựng một kiến trúc code tường minh

### 7. Các kiểu dữ liệu nguyên thủy gồm?
```java
- boolean
- char	
- byte	
- short	
- int	
- long	
- float	
- double
```
### 8. Sắp xếp theo chiều public dần các quyền riêng tư của đối tượng.
```java
1. private
2. default
3. protected
4. public
```

### 9. Inteface dùng để làm gì?
- Để định nghĩa các phương thức dùng chung cho nhiều đối tượng khác nhau để dễ quản lý

### 10. Từ khóa instanceof dùng trong hoàn cảnh nào? Nêu ví dụ?
- `Instanceof` dùng để so sánh thực thể với một kiểu dữ liệu và trả về giá trị boolean là true hoặc false.

```java
public class TuGiac {
	public static void main(String args[]) {
	    TuGiac tugiacA = new TuGiac();
	    System.out.println(tugiacA instanceof TuGiac); // true
	}
}
```

### 11. Có bao nhiêu mối quan hệ giữa các đối tượng? Chỉ rõ nội dung từng mối quan hệ đó?

**1. Mối quan hệ kế thừa**
   - A và B có cùng bản chất
   - Đối tượng A được thừa hưởng lại các phương thức và thuộc tính của đối tượng B mà không cần khai báo

**2. Mối quan hệ phụ thuộc**
   - Nếu B trở thành thuộc tính của đối tượng A thì ta nói A phụ thuộc B
   - Khi B thay đổi => A thay đổi

**3. Mối quan hệ song song**
   - A và B độc lập với nhau, không có bất kỳ sự ràng buộc nào

### 12. Nêu đặc điểm và ý nghĩa của phương thức khởi tạo?

- `Đặc điểm`: 
	+ Tên phương thức trùng với tên đối tượng
	+ Không có kiểu dữ liệu trả về
- `Ý nghĩa`:
	+ Khởi tạo thông tin các thuộc tính của đối tượng
	+ Có thể thay thế phương thức nhập thông tin

### 13. Giá trị mặc định của các kiểu dữ liệu là gì?
- Là các giá trị được gán mặc định sau khi khai báo một biến liệu.
