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

- Định nghĩa lại phương thức trừu tượng đã được khai báo trong class cha hoặc `interface` được gọi là ghi đè
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
	int tinhDienTich() {
	    // Nội dung phương thức
	}
	
	@Override
	void tinhChuVi() {
	    // Nội dung phương thức
	    super.tinhChuVi();
	    // Tính chu vi tiếp    
	}
}
```
### 5. Nạp chồng phương thức là gì? Nêu ví dụ:
- Là các phương thức có tên giống nhau nhưng khác nhau về kiểu dữ liệu truyền vào hoặc số lượng các tham số.

```java
    public class TuGiac {
	String tinhDienTich() {
	    // Nội dung phương thức
	}

	String tinhDienTich(int a, int b, int c, int d) {
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
|int		|0	     	  |
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
	    for(int i = 0; i < 1000; i += 2) {
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
- Thay đổi biểu thức điều kiện lặp

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
	    return father.indexOf(son, index + 1);
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
	+ Số lượng phần tử của mảng là cố định và được xác định khi khai báo mảng. Sau đó không thể thay đổi số lượng phần tử trong mảng.
- Phạm vi sử dụng
	+ Mảng được sử dụng để giải quyết các bài toán về tập hợp như: duyệt, tìm kiếm, xóa, sắp xếp ...

### 26. Khai bảo mảng 1 chiều, 2 chiều như thế nào?

```java
    // Mảng 1 chiều
    String array[]   = new String[6];
    String array[]   = new String[] {"abc", "abc", "abc", "abc", "abc"};

    // Mảng 2 chiều
    String array[][] = new String[SL_PHAN_TU][SL_THUOC_TINH];
    int    array[][] = new int[][] { {1,2,3},
				     {1,2,3},
				     {1,2,3} };
```

### 27. Thư viện hỗ trợ các phương thức của mảng là thư viện nào? Nêu ra tên và nội dung của các phương thức đó.

- Thư viện `Arrays`, hỗ trợ các phương thức của mảng
- Các phương thức đặc trưng bao gồm

<table>
    <thead>
        <tr>  
            <th> Phương thức
            <th> Chức năng
    <tbody>            
        <tr>
            <td> <code>Arrays.fill()</code>
            <td> Khởi tạo các phần tử có cùng giá trị cho mảng
        <tr>
            <td> <code>Arrays.toString()</code> 
            <td> Trả về một <code>String</code> chứa tất cả các phần tử của mảng
        <tr>
            <td> <code>Arrays.sort()</code>
            <td> Sắp xếp các phần tử của mảng theo hướng tăng dần hoặc giảm dần
        <tr>
            <td> <code>Arrays.copyOf()</code>
            <td> Sao chép mảng hiện tại, và trả về một mảng mới
</table>

### 28. Viết đoạn code sắp xếp tăng dần 1 mảng 1 chiều (không sử dụng thư viện)?

```java
	public void sort() {
	    for (int i = 0; i < arr.length; i++) {
		for (int j = i + 1; j < arr.length; j++) {
		    if(arr[i] > arr[j]) {
			int temp = arr[i];
			arr[i] = arr[j];
			arr[j] = temp;
		    }
		}
	    }
        }
```

### 29. Muốn kiểm tra xem 1 đối tượng HocSinh nào đó có trong danh sách không thì có thể dùng những phương thức gì trong ArrayList? Để sử dụng phương thức đó thì bản thân đối tượng HocSinh cần phải làm gì?

- Muốn kiểm tra sự tồn tại của thực thể `HocSinh` trong `ArrayList<HocSinh>` thì có thể sử dụng phương thức `contain()` hoặc `indexOf()`

- Trước khi sử dụng 2 phương thức này cần ghi đè phương thức `equals()` bên trong đối tượng `HocSinh`

### 30. Viết đoạn code để tạo ra 1 mảng 10 phần tử số nguyên bất kì có giá trị lớn hơn 100 và nhỏ hơn 200? 

```java
	public static void main(String[] args) {
	    int arr[] = new int[10];
	    for (int i = 0; i < 10; i++) {
		arr[i] = (int) (101 + Math.random() * 99);
	    }
	}
```

### 31. Collections là gì? Đối tượng này được sử dụng để làm gì (Nêu tên và nội dung của các phương thức đặc trưng)?

- `Collections` là một bộ thư viện của Java, cung cấp các phương thức `static` để thao tác với các nhóm đối tượng như `List`, `ArrayList`, ... Tất cả các hoạt động  như tìm kiếm, phân loại, chèn, xóa,... đều có thể được thực hiện bởi Java Collections.

- Các phương thức đặc trưng

<table>
    <thead>
        <tr>  
            <th> Phương thức
            <th> Chức năng
    <tbody>            
        <tr>
            <td> <code>Collections.fill()</code>
            <td> Thay thế tất cả các phần tử của danh sách bằng 1 giá trị giống nhau
        <tr>
            <td> <code>Collections.min()</code>
	    <br> <code>Collections.max()</code>
            <td> Trả về phần tử có giá trị lớn nhất, nhỏ nhất trong danh sách
        <tr>
            <td> <code>Collections.sort()</code>
            <td> Sắp xếp các phần tử của danh sách theo thứ tự tăng dần hoặc giảm dần
        <tr>
            <td> <code>Collections.reverse()</code>
            <td> Đảo ngược vị trí các phần tử trong danh sách
	<tr>
            <td> <code>Collections.shuffle()</code>
            <td> Trộn ngẫn nhiên vị trí các phần tử trong danh sách
</table>

### 32. Xóa một phần tử khỏi ArrayList thì có mấy cách? Nếu sự khác nhau của từng cách?

+ Cách 1: Xóa một phần tử ở vị trí `index` ra khỏi danh sách. Chỉ số của các phần tử tiếp theo bị giảm đi 1 (Do kích thước của danh sách bị co lại)
+ Cách 2: Duyệt từ trên xuống dưới, nếu gặp phần tử `Object` bằng với phần tử muốn xóa thì xóa phần tử đó và kết thúc phương thức `remove()`
```java
	// ----------- Cách 1 : Dùng vị trí của phần tử -----------
	ArrayList<HocSinh> dsHocSinh = new ArrayList<HocSinh>();
	dsHocSinh.remove(int index);

	// ----------- Cách 2 : Truyền trực tiếp phần tử -----------
	ArrayList<HocSinh> dsHocSinh = new ArrayList<HocSinh>();
	dsHocSinh.remove(Object o);
```

### 33. Có mấy dạng lỗi (kể tên và khái niệm), ngoại lệ được sử dụng để xử lý dạng lỗi nào?

|  Tên lỗi    |                                       Khái niệm							  |
|------------ |---------------------------------------------------------------------------------------------------|
|Lỗi cấu hình |Gặp phải khi cấu hình, cài đặt môi trường để phát triển phần mềm					  |
|Lỗi biên dịch|Xảy ra trong quá trình viết code như: lỗi cú pháp, lỗi thiếu dấu ngoặc, lỗi truy cập trái phép, ...|
|Lỗi thực thi |Xảy ra khi thực thi chương trình, dẫn tới việc treo, dừng đột ngột, xử lý chậm ...                 |

- Ngoại lệ là các trường hợp lỗi như: Xử lý chậm, bị treo, dừng đột ngột, tuy nhiên ở mức tiên đoán và phòng tránh được. 

### 34. Nêu các bước xử lý ngoại lệ?
- B1: dự đoán lỗi gặp phải cho từng dòng lệnh hoặc khối lệnh mà chúng ta nghi ngờ bị exception
- B2: Cố gắng dùng `if` - `else` để loại bỏ các trường hợp bất thường
    + Nếu dùng được `if` - `else` thì xử lý trong khối `if` - `else`
    + Không được thì chuyển qua bước 3
- B3: Kiểm tra xem bắt bằng `try` - `catch` ở đó có được không
    + Được thì xử lý tiếp công việc trong khối `try` - `catch` ... `finally`
    + Không được thì dùng `throw` hoặc `throws` ném ra ngoại lệ sau đó dùng `try` - `catch` để bắt ở nơi gọi đến

### 35. Sử dụng phương thức chuyển đổi 1 chuỗi sang số thì có nguy cơ bị lỗi gì? Viết code để xử lí ngoại lệ theo 2 cách là regex và try catch.

- Nếu chuyển từ chuỗi sang số thì có nguy cơ gặp lỗi `NumberFormatException`.
- Code xử lý lỗi

```java
	// ----------- REGEX -----------
	boolean validate(String number) {
	    if(number.matches("-?\\d+(\\.\\d+)?")) {
		return true;
	    }
	    return false;
	}

	// ----------- try - catch -----------
	boolean validate(String number) {
	    try {
		Double.parseDouble(number);
		return true;
	    } catch (NumberFormatException e) {
		return false;
	    }
	}
```

### 36. Sử dụng phương thức lấy ký tự ở vị trí nào đó trong chuỗi thì có nguy cơ bị lỗi gì? Viết code xử lý ngoại lệ trường hợp này theo 2 cách?

- Lỗi có thể gặp `IndexOutOfBoundsException`
- Code xử lý lỗi

```java
	// ------------- Logic -------------
        boolean getCharAtLogic(String str, int index) {
	    if (str.length() <= index || index < 0) {
                return false;
	    }
	    char ch = str.charAt(index);
	    return true;
	}
	
	// ----------- try - catch -----------
        boolean getCharAtTryCath(String str, int index) {
	    try {
		char ch = str.charAt(index);
		return true;
	    } catch (IndexOutOfBoundsException e) {
		return false;
	    }
	}
```
### 37. Đối tượng File dùng để làm gì? Các phương thức quan trọng của File là gì? Liệt kê và nếu tác dụng của từng phương thức?

- Đối tượng `File` dùng để thao tác, làm việc với tập tin, thư mục hệ thống.
- Các phương thức điển hình: 

| Phương thức                    | Chức năng 				 |
|--------------------------------|---------------------------------------|
<code>exists()</code>            | Kiểm tra xem file có tồn tại hay không
<code>getName()</code>           | Lấy tên file (input-file.txt)
<code>getPath()</code>           | Đường dẫn đầy đủ
<code>isDirectory()</code>       | Kiểm tra xem là thư mục hay không
<code>isFile()</code>            | Kiểm tra xem là file hay không
<code>length()</code>            | Kích cỡ file (byte)
<code>createNewFile()</code>     | Tạo ra file mới
<code>delete()</code>            | Xóa file
<code>mkdir()</code>             | Tạo thư mục

### 38. Sử dụng đối tượng nào để đọc file? Nêu các bước để đọc file?

- Đối tượng dùng để đọc file: có thể dùng `FileInputStream`
- Các bước đọc file
```
	B1: Trỏ vào file cần làm việc
	B2: Kiểm tra xem file có tồn tại không để thông báo
	B3: Mở file để đọc
	B4: Đọc file
	B5: Đóng file
```

### 39: Có mấy cách đọc file? Cách đọc nào nhanh hơn, tối ưu hơn?
```
	Có 2 cách đọc file:
	    Cách 1: Đọc từng byte
	    Cách 2: Đọc theo mảng byte

	=> Cách đọc theo mảng byte sẽ tối ưu hơn.
```

### 40. Viết đoạn code đọc file text abc.txt ở ổ D và in ra màn hình?

```java
	public static void main(String[] args) {
		String data = readFile("D:\\abc.txt");
		System.out.println(data);
	}

	private String readFile(String path) {
	    String data = "";
	    try {
		File file = new File(path);
		if (!file.exists()) {
		    return null;
		}
		byte[] bytes = Files.readAllBytes(file.toPath());
		    data = new String(bytes);
		    return data;
	    } catch (IOException e) {
		System.err.println("Lỗi Hệ Thống");
	    }
	    return null;
	}
```

### 41. Ghi 1 chuỗi vào file thì làm thế nào? Viết đoạn code mô tả?

- Các bước ghi file
```
B1: Trỏ vào file cần làm việc 
B2: Tạo mới file nếu file đó chưa tồn tại
B3: Mở file để ghi (dùng OuputStream)
B4: Ghi file (ghi String)
B5: Đóng file
```
- Code minh họa

```java
	void writeFile(String data, File file) {
	    try {
		if (!file.exists()) {
			file.getParentFile().mkdirs();
			file.createNewFile();
		}
		FileOutputStream writer = new FileOutputStream(file);
		writer.write(data.getBytes());
		writer.close();
	    } catch (IOException e) {
		System.out.println("Lỗi hệ thống");
	    }
        }
```


### 42. Nêu mối quan hệ của JFrame, JPanel , JComponent? Ý nghĩa của từng đối tượng trong mối quan hệ này như thế nào?

- `JFrame` là nơi chứa các thông tin về cửa sổ của giao diện, như thu nhỏ, phóng to, đóng, mở, ... 
- `JPanel` là lớp giao diện được đặt bên trong `JFrame`, mỗi một `JFrame` có thể chứa nhiều `JPanel`
- `JComponent` là các thành phần của giao diện như nút nhấn, textField, ... Các `JComponent` này được gói gọn trên `JPanel`



### 43. Viết đoạn lệnh để tạo 1 JFrame có tên là GUI kích thước 500x500,  không co dãn và ra giữa màn hình?

```java
	public static void main(String[] args) {
	    JFrame GUI = new JFrame();
	    GUI.setTitle("GUI");
	    GUI.setSize(500, 500);
	    GUI.setLocationRelativeTo(null);
	    GUI.setResizable(false);
	    GUI.setVisible(true);
	}
```
### 44. Đối tượng nào giúp lấy được độ rộng, chiều cao của 1 chuỗi của 1 font chữ? Phương thức đó là gì?

- Đối tượng giúp lấy chiều cao, độ rộng của một chuỗi là `FontMetrics`
- Phương thức lấy chiều cao : `getHeight()`
- Phương thức lấy chiều rộng : `stringWidth()`

### 45. JList dùng để làm gì? JCombobox dùng để làm gì?

- `JList` giúp hiển thị dữ liệu danh sách theo chiều dọc hoặc chiều ngang
- `JComboBox` là đối tượng giao diện giúp hiển thị data dưới dạng một danh sách xổ xuống

### 46. Có 3 đối tượng JTable, Model, ArrayList<Data>. Hãy mô tả ngắn gọn cách thức hoạt động của 3 đối tượng trên để hiển thị được danh sách data trên table?

`Arraylist<data>` chứa dữ liệu gốc, dữ liệu này được chuyển đổi sang dạng `Model` để nạp vào trong `JTable` thông qua phương thức `setModel()`

### 47. Thread là gì? Có bao nhiêu cách khởi tạo nó trong java?
- `Thread` là một đối tượng được Java định nghĩa để thực thi các tác vụ trên 1 luồng riêng
- Cách khởi tạo và thực thi `Thread`
	+ Cách 1: Tạo một thực thể `Runnable` chứa khối lệnh cần thực thi. Sau đó dùng `Thread` trỏ đến thực thể `Runnable` đó
	+ Cách 2: Tạo một đối tượng `Thread` rồi trực tiếp ghi đè phương thức `run()`
	+ Cách 3: Kế thừa class `Thread` và đưa các tác vụ vào phương thức `run()` và `overide` phương thức `run()`
	+ Cách 4: Dùng một class **implements** **`Runnable`** sau đó dùng thread để chạy một thực thể của class này.


### 48. Viết đoạn code ví dụ sử dụng Runnable trong Thread?
```java
	public static void main(String[] args) {
	    Runnable runnable = new Runnable() {
		@Override
		public void run() {
		    for(int i = 0; i < 100; i++) {
			System.out.print(i);
		    }
		}
	    }

	    Thread newThread = new Thread(runnable);
	    newThread.start();
	}
```

### 49. Muốn run 1 Thread thì phải gọi phương thức gì? Một Thread có thể start 2 lần không?

- Sử dụng phương thức `start()` của đối tượng `Thread`
- Một `Thread` không thể `start` 2 lần

### 50. Muốn dừng một Thread đang chạy thì có những cách nào?
- Cách 1: sử dụng 1 biến `flag`, luôn kiểm tra trạng thái của `flag` khi `Thread` chạy, nếu `flag = true` thì chạy tiếp, `flag = false` thì dừng
- Cách 2: gọi đến phương thức `interupt()` của `Thread`

### 51. Viết đoạn chương trình thực hiện đếm từ 1 - 1000, mỗi bước đếm cách nhau 2 giây và in ra màn hình console?
```java
	public static void main(String[] args) {
	    try {
		for (int i = 1; i < 1000; i++) {
		    System.out.println(i);
		    Thread.sleep(2000);
		} catch (InterruptedException e) {
		    System.out.println("Lỗi hệ thống");
		}
	    }
	}
```