# OPERATORS # 
## Toán tử gán, các phép so sánh ##
| Phép tính | Công thức | Ý nghĩa |
| :---  | :---: | ---: |
| = ( = là gán ) | x=1 | x=1 | 
| += | x+=y | x=x+y |
| -= | x-=y | x=x-y | 
| *= | x*=y | x=x*y |
| += | x+=y | x=x+y |
| /= ( này là chia lấy phần nguyên )  | x/=y | x=x/y | 
| %= ( này là chia lấy phần dư ) | x%=y | x=x%y | 


## so sánh ##
| Phép tính | Công thức | Ý nghĩa  | Nội dung |
| :--- | :---: | :---: | ---: |
| <=  | < hoặc =  | 2<=2 | True |
| >=  | > hoặc =  | 2>=1 | True |
| ==  | = nhau  | 1==1 | True |
| !=  | khác nhau  | 1!=1 | False |
| >  | lớn hơn  | 1>2 | False |
| <  | nhỏ hơn  | 2<1 | False |

## Toán tử logic, tiền tố, hậu tố 
### Toán tử logic ###
 && ( AND ) : Trả về True khi cả 2 đều đúng ( hiểu đơn giản là phải 2 điều kiện đúng )
| x | y | giá trị trả về |
| :--- | :---: | ---: |
| x=true | y=true | 1 |
| x=false | y=true | 0 |
| x=true | y=false | 0 |
| x=false | y=false | 0 | 

|| (HOẶC) : Trả về false khi cả 2 đều sai ( hiểu đơn giản là chỉ cần đúng 1 trong 2 )

| x | y | giá trị trả về |
| :--- | :---: | ---: |
| x=true | y=true | 1 |
| x=false | y=true | 1 |
| x=true | y=false | 1 |
| x=false | y=false | 0 | 

! Phép phủ định ( đảo ngược giá trị )
| x | ! | giá trị trả về |
| :--- | :---: | ---: |
| x=true | !x  | 0 |
| x=false | !x | 1 |

Tiền tố: ++n; --n; ( tăng trước, dùng sau)
```cpp
vd:
int a=5;
int b= ++a;
Output: a=6; b=6
// a tăng lên thành 6
// sau khi tăng rồi a mới gán cho b
```
Hậu tố: n++; n-- (dùng trước, tăng sau ) 
```cpp
int x=5
int x=y;
x++
Output: x=6;y=5
// y gán cho x; x=5
// tăng x lên 1; x=6
```














