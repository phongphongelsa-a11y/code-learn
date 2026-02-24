# VÒNG LẶP  #

## while loop (được sử dụng khi không biết chính xác số lần lặp) ## 
```cpp
while (điều_kiện ) {
// nếu điều kiện đúng sẽ chạy vào lệnh trong này
// khối lệnh này sẽ chạy cho đến khi nào điều kiện bên ngoài false
// chú ý điều kiện nếu không sẽ bị lặp vô tận nếu điều kiện luôn đúng và không bao giờ thành sai
}

VD: Nhập n=1;
    while (n<=5){
    cout << n << endl;
    n++;
}
return 0;

Input: 1 2 3 4 5

// vòng lặp ở trên chạy như sau
// n=1
// 1<=5 True
// cout << n;
// tăng biến n lên 1

// n=2
// 2<=5 True
// cout << n;
// tăng biến n lên 1
.....
// chạy cho đến khi nào điều kiện sai VD như n=6
```
## for loop ( được sử dụng nhiều khi biết trước số lần lặp, for này em thấy hay được dùng nhiều trong phần mảng ) ## 
```cpp
for (khởi_tạo_biến; điều_kiện; tăng/giảm biến){
         khối lệnh;
}
// vòng lặp for chạy như sau:

// khởi tạo biến
// kiểm tra điều kiện
// nếu điều kiện đúng sẽ chạy vào khối lệnh bên dưới
// tăng/giảm biến

vd
for (int i=1; i<5 ; i++){
  cout << i << endl;
}
return 0;

Output: 1 2 3 4

vòng lặp trên chạy như sau:
// i=1;
// i<5 True
// cout << i
// tăng biến i lên 1

// i=2
// i<5 True
// cout << i
// tăng biến i lên 1
......
// i=5
// i<5 False
// dừng chương trình và output
```
# do while ( thực hiện khối lệnh ít nhất 1 lần trước khi kiểm tra điều kiện ) cái do while này trước em làm btap chưa dùng nó lần nào:))) #
```cpp
do {
// khối lệnh
}
while (điều_kiện)

VD:
int n;
do {
cin>>n;
}
while (n<0);

// đoạn code ở trên là nếu nhập n âm thì sẽ cho nhập lại cho đến khi nào dương thì thoái vòng lặp


















