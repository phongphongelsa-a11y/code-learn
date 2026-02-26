# DATA TYPES #


##  CÁC KIỂU DỮ LIỆU CƠ BẢN 

| Kiểu dữ liệu | Kích thước | Ý nghĩa | Khoảng giá trị |
| :--- | :---: | :--- | :--- |
| short | 2 bytes | Số nguyên | -32,768 đến 32,767 |
| unsigned short | 2 bytes | Số nguyên | 0 đến 65,535 |
| int | 4 bytes | Số nguyên | -2,147,483,648 đến 2,147,483,647 |
| unsigned int | 4 bytes | Số nguyên | 0 đến 4,294,967,295 |
| long long| 8 bytes | Số nguyên | -9,223,372,036,854,775,808 đến 9,223,372,036,854,775,807 |
| unsigned long long | 8 bytes | Số nguyên | 0 đến 18,446,744,073,709,551,615 |
| char | 1 byte | Số nguyên, Ký tự | -128 đến 127 |
| unsigned char | 1 byte | Số nguyên, Ký tự | 0 đến 255 |
| float | 4 bytes | Số thực | 3.4E-38 đến 3.4E+38 |
| double | 8 bytes | Số thực | 1.7E-308 đến 1.7E+308 |

## ÉP KIỂU DỮ LIỆU
Đơn giản là chuyển từ kiểu dữ liệu này sang kiểu dữ liệu khác

### Ép kiểu rộng
Ép kiểu dữ liệu từ bé > lớn 

Ex: int - long - float - double
=> Không mất dữ liệu

### Ép kiểu hẹp
Ép kiểu dữ liệu từ lớn > bé

Ex: duoble - float - long - int
=> Có thể mất dữ liệu

## Ngầm định
Là loại ép kiểu do trình biên dịch tự động thực hiện khi cần thiết thường là khi gán 1 giá trị có kiểu nhỏ hơn cho 1 biến có giá trị lớn hơn 
```cpp
// VD: Không làm mất giá trị
    int n = 100;
    long long m = n; // Implicit casting

    float x = 20.18923;
    double y = x; // Implicit casting

    Output m=100
           y=20.18923

// VD: Làm mất giá trị
   long long m = 182831892845128;
    int n = m;
    
    float x = 3.123124;
    int y = x;

 Output n=-569978296
        y=3
```

## Tường minh
Là khi mình tự tay chuyển đổi kiểu dữ liệu
```cpp
VD:
 int a = 10, b = 3;
float div1 = a / b;
float div2 = (float) a / b; // Ép kiểu tường minh

Output: div1 = 3
        div 2 = 3.33
```


