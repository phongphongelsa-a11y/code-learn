if (điều_kiện) {
bên trong lệnh sẽ chạy nếu điều kiện true
nếu điều kiện false thì sẽ chạy xuống dưới
}
else if (điều_kiện){
lệnh bên trong này sẽ chạy nếu điều kiện bên trên false 
}
else {
lệnh này sẽ được chạy khi tất cả điều kiện ở trên false
}

VD
if ( điểm >= 8 ) {
    cout << " giỏi" << endl;
}
else if (điểm >=6) {
    cout << "khá" << endl;
}
else if ( điểm >= 5 ) {
    cout << " trung binh " << endl;
}
else {
    cout << "yếu"<< endl;
}

INTPUT: 7
OUTPUT: KHÁ


2 if rời không loại trừ nhau
if ( x>0 ) {
cout << "DUONG" << endl;
}

if ( x>=0) { 
cout << "KHONG AM" << endl;

Input: 4
Output : DUONG
         KHONG AM

đây là viết bằng if else để so sánh     
if ( x>0 ) {
cout << "DUONG" << endl;
}

else if ( x>=0) { 
cout << "KHONG AM" << endl;

Input: 4
Output: DƯƠNG
Thứ tự điều kiện
FIZZ BUZZ
for (int i = 1; i <= n; i++) {
        if (i % 3 == 0) {
            cout << "Fizz";
        } else if (i % 5 == 0) {
            cout << "Buzz";
        } else if (i % 3 == 0 && i % 5 == 0) {
            cout << "FizzBuzz";
        } else {
            cout << i;
        }
Code ở trên là sai. Vì nếu nhập 15 phải cout ra "Fizz Buzz" theo code ở trên thì sẽ chạy đến if là sẽ bị dưng chương trình và cout ra fizz luôn. Phải đảo điều kiện FizzBuzz lên đầu.

if lồng nhau ( khi điều kiện bên ngoài đúng mới vào bên trong để kiểm tra)









