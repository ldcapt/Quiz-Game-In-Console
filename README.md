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
- Toán tử `instanceof` trong java được sử dụng để kiểm tra một đối tượng có phải là thể hiển của một kiểu dữ liệu cụ thể không (***lớp, lớp con, interface***).

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
Ví dụ:

|Kiểu dữ liệu	| Giá trị mặc định|
|:-------------:|:---------------:|
|boolean	|false		  |
|char		|'\u0000'	  |
|byte		|0		  |
|short		|0		  |
|int		|0		  |
|long		|0L		  |
|float		|0.0f		  |
|double		|0.0d		  |

### 14. Chuyển 1 chuỗi sang số nguyên, số thực như thế nào?

- Sử dụng phương thức ép kiểu. Dùng các đối tượng có sẵn Integer, Double
```java
	String str          = "1000";
	double doubleNumber = Double.parseDouble(str);
	int    intNumber    = Integer.parseInt(str);
```

### 15. `for` và `while` khi thực thi thì công việc được thực hiện ít nhất là mấy lần? Viết 1 đoạn code để thực hiện tính tổng các số chẵn < 1000?

- Vòng lặp `for` và `while - do` kiểm tra điều kiện trước khi bắt đầu vòng lặp. Nếu điều kiện không đúng thì không thực thi khối lệnh bên trong nó.

- Vòng lặp `do - while` thực thi công việc ít nhất một lần rồi mới kiểm tra điều kiện

- Tổng các số chẵn < 1000
```java
    public int caculate() {
	int sum = 0;
	for(int i = 0; i < 1000; i + 2) {
	    sum += i;
	}
	return sum;
    }
```

### 16. Trong java có đa kế thừa class , interface không? Ví dụ?

- Trong java một class chỉ kế thừa trực tiếp  từ 1 class cha và có thể `implements` nhiều `interface` khác nhau.

- Ví dụ
```java
	public interface ICommon {
		void init();
		void addComponent();
		void addEvent();
	}

	public interface IPanelAction {
		void changePanel();
	}

	public class GUI extends JFrame implements ICommon, IPanelAction {
		// Nội dung class

		@Override
		void init() {
		    // Nội dung phương thức
		}
		@Override
		void addComponent() {
		    // Nội dung phương thức
		}
		@Override
		void addEvent() {
		    // Nội dung phương thức
		}
		@Override
		void changePanel() {
		    // Nội dung phương thức
		}
	}
```

### 17. Muốn dừng vòng lặp trong for/while thì có nhưng cách nào ?

Có những cách sau: 
- Dùng toán tử **`break`**
- Dùng lệnh **`return`**
- Dùng lệnh ngắt chương trình `System.exit(0);`
- Ném ra lỗi

### 18. Nêu ý nghĩa của các lệnh return, continue, break ?

- `return` : Thoát khỏi phương thức đang định nghĩa
- `continue` : Bỏ qua khối lệnh phía dưới block code và bắt đầu vòng lặp mới
- `break` : Thoát khỏi một block code

### 19. Toán tử ++a và a++ khác nhau như thế nào? Viết 1 đoạn code cụ thể để thể hiện điều đó.

- Toán tử `++a`: Ưu tiên thực thi tăng `a` lên 1. Sau khi tăng `a` thì bắt đầu thực hiện các phép toán khác.

- Toán tử `a++`: Sau khi kết thúc line code, giá trị của `a` được tăng lên 1.

- Ví dụ
```java
	int a = 0;
	System.out.print(++a); // 1
	System.out.print(a++); // 1
	System.out.print(a);   // 2
```

### 20. String là immutable hay mutable? Giải thích và lấy ví dụ 2 khái niệm này.
- `String` là kiểu dữ liệu `immutable`.
- `immutable`: Khi sử dụng các phương thức, giá trị của thực thể không bị thay đổi.
- `mutable`: Khi sử dụng các phương thức, giá trị của thực thể bị thay đổi

- Ví dụ:
```java
	// -------- immutable -------- 
	String text1 = "abc";
	text1.length();
	System.out.print(text1); // "abc"

	// --------- mutable --------- 
	StringBuilder text2 = new StringBuilder("abc");
	text2.append("def");
	System.out.print(text2); // "abcdef"
```

### 21. Viết code tìm vị trí xuất hiện thứ 2 của 1 chuỗi con trong String?

```java
	public int findSecondIndex(String father, String son) {
	    int index = father.indexOf(son);
	    if (index == -1) {
		return -1;
	    }
	    String temp = father.subString(index + son.length());
	    index = temp.indexOf(son);
	    
	    return index;
	}
```

### 22. String có mấy cách khởi tạo, chỉ rõ sự khác nhau của các cách khởi tạo đó?

- `String` có 2 cách khởi tạo là: 
```java
	// ----------- String pool -----------
	String text1 = "abc";

	// ----------- String heap -----------
	String text2 = new String("abc");
```

- Các khởi tạo dùng toán tử gán trực tiếp với một chuỗi:
```
- Lúc này giá trị của biến sẽ được lưu trong vùng nhớ String pool, 
- Ở đây các giá trị chuỗi bằng nhau sẽ được lưu vào cùng một ô nhớ.
- Giúp tối ưu không gian lưu trữ và tăng tốc độ xử lý
```

- Cách khởi tạo dùng toán tử `new`
```
- Mỗi một thực thể String sẽ được lưu trữ ở các ô nhớ khác nhau
```

### 23. Toán tử == được dùng để so sánh 2 String trong hoàn cảnh nào?

- Toán tử `==` có ý nghĩa là so sánh địa chỉ vùng bộ nhớ lưu trữ của đối tượng.
- Toán tử `==` có thể so sánh 2 `String` nếu cả 2 chuỗi này được khởi tạo trong vùng nhớ `String Pool`

### 24. String khác với StringBuilder ở đặc điểm nào?

| <code>String</code> | <code>StringBuilder</code>|
|---|---|
|Là kiểu đối tượng <code>immutable</code>|Là kiểu đối tượng <code>mutable</code>|
|Hỗ trợ một số phương thức phổ biến|Hỗ trợ nhiều phương thức xử lý nhanh hơn đối tượng <code>String</code>|

### 25. Mảng trong java có đặc điểm gì? Chúng được sử dụng nhằm mục đích gì?

- Đặc điểm
	+ Mảng là một tập hợp hữu hạn các phần tử có cùng kiểu dữ liệu, có địa chỉ liên tiếp nhau trong bộ nhớ.
	+ 