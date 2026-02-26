# FUNCITION
- Hàm là 1 các khối lệnh có nhiệm vụ thực hiện chức năng nào đó
## Lợi ích của việc chia code thành các hàm 
- Code mạch lạc, dễ đọc
- Dễ debug khi gặp lỗi
- Khả năng tái sử dụng lại code
- Dễ bảo trì khi cần thay đổi 1 chức năng nhỏ

```cpp
// cú pháp
data_type funcition_name ( type1 parameter1, type2 parameter2...){
    //code 
}
// data_type: kiểu dữ liệu của hàm
// funcition_name: tên hàm
// type1 parameter1: tham số của hàm
// code: các câu lệnh bên trong hàm
```
## Hàm có trả về (return) 
- Nếu muốn hàm trả về giá trị, sử dụng các kiểu dữ liệu và dùng return
```cpp
VD:
int tong( int a, int b){
      int sum= a+b;
      return sum;
}
```
## Void ( Không trả về)
- Void nghĩa là hàm không có giá trị trả về
```cpp
VD:
void Hello() {
   cout << "Hello";
}
```
## Gọi 1 hàm
```cpp
VD:
void Hello() {
  cout << "Hello everyone";
}

int main() {
    Hello();
    Hello();
    Hello();
    return 0;
}
Output:
// Hello everyone
// Hello everyone
// Hello everyone
```
## Khai báo và định nghĩa hàm
- nếu khai báo hàm sau hàm main() thì sẽ bị báo lỗi
```cpp
void Hello() {       // khai báo hàm 
    // khối lệnh bên trong hàm  
}

VD:
int main() {
    Hello();
    Hello();
    Hello();
    return 0;
}

void Hello() {
  cout << "Hello everyone";
}
// error

// cách sửa (khai báo trước)
void Hello() // khai báo hàm ở đây

int main(){ // hàm main ở đây
    Hello() // gọi hàm
    return 0;
}

// định nghĩa hàm
void Hello() {
cout << "Hello everyone";
}

```
### Truyền tham số, đối số, tham chiếu và tham trị
```cpp
- Tham số: là biến trong phần khai báo hàm và tham số chỉ tồn tại bên trong hàm
VD:
int Tong(int n){ // int n là tham số

{

- Đối số: là giá trị truyền vào khi gọi hàm
VD:
int a=5;
Tong(a) // a là đối số

- Tham trị: Hàm nhận bản sao của đối số
VD:
void tang(int x) {
    x = x + 1;
}

int main(){
int a=5;
tang(a);
cout << a;  // a=5
}

// x gán cho a
// sau đó sửa x
// a ko đổi 

- Tham chiếu: Hàm nhận trực tiếp biến gốc
VD:
void tang(int &x) {
    x = x + 1;
}
int main(){
int a = 5;
tang(a);
cout << a; // a=6
}
// x chính là a
// sửa x
// a đổi

    

















