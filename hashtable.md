# Hash Table — "Tính ra luôn vị trí, không cần tìm"

## 1. Bắt đầu từ nỗi đau: Array tìm chậm
Duc, hình dung em là sinh viên năm nhất, có một danh sách 1000 sinh viên trong một mảng:

`students = ["An", "Bình", "Cường", ..., "Yên", "Zung"]`

Giờ cần tìm "Yên" -> phải duyệt từ đầu đến cuối, tệ nhất là 1000 bước. Đó là O(n).
Câu hỏi tự nhiên sẽ nảy ra: "Có cách nào từ cái tên, tính ra luôn vị trí trong mảng không?"
Có. Và đó chính xác là ý tưởng của Hash Table.

---

## 2. Ví dụ thực tế: Tủ locker ở trường
Hình dung trường có 10 cái tủ locker, đánh số 0-9.
Quy tắc gửi đồ: Lấy số cuối của mã sinh viên -> đó là số tủ.

* SV "An" — MSSV 2021043 -> 3 % 10 = 3 -> tủ số 3
* SV "Bình" — MSSV 2021087 -> 7 % 10 = 7 -> tủ số 7
* SV "Cường" — MSSV 2021056 -> 6 % 10 = 6 -> tủ số 6

Khi cần lấy đồ của "An" (MSSV 2021043):
* Không cần mở từng tủ ra kiểm tra
* Tính `2021043 % 10 = 3` -> đi thẳng đến tủ 3 -> xong

Phép tính `MSSV % 10` chính là **hash function**. Dãy tủ locker chính là **hash table**.

---

## 3. Vấn đề: Va chạm (Collision)
Nếu có thêm SV "Dũng" — MSSV 2021073 -> `3 % 10 = 3` -> cũng tủ số 3!

Hai người cùng được gán vào một tủ -> đây gọi là collision.

Giải quyết thế nào? Hai cách phổ biến:

* **Cách A — Chaining (mỗi tủ chứa một danh sách):** Tủ số 3 không chỉ chứa 1 món, mà chứa một cái "túi" bên trong — mở ra thấy cả đồ của An và Dũng, lục thêm một chút.
* **Cách B — Open Addressing (tủ đầy thì sang tủ kế):** Tủ 3 có người rồi -> thử tủ 4, tủ 4 trống -> gửi vào tủ 4.

---

## 4. Nhìn dưới góc độ Orientation (khái niệm)
Hash Table về bản chất là:

`Key -> hash(key) -> index -> Value`

Ba thành phần cốt lõi:

1.  **Array bên dưới** — cái mảng thật sự lưu dữ liệu. Hash table không phải phép màu, nó vẫn dùng array, nhưng thông minh hơn ở cách chọn vị trí.
2.  **Hash function** — hàm biến key (string, số, bất kỳ) thành một con số (index). Yêu cầu: cùng input luôn ra cùng output, và phân bố đều.
3.  **Chiến lược xử lý collision** — vì không có hash function nào hoàn hảo, luôn cần kế hoạch B khi hai key ra cùng index.

### Complexity:

| Thao tác | Array (tìm theo giá trị) | Hash Table |
| :--- | :--- | :--- |
| **Tìm** | O(n) | O(1) trung bình |
| **Thêm** | O(1) cuối mảng | O(1) trung bình |
| **Xóa** | O(n) | O(1) trung bình |

Cái "trung bình" rất quan trọng — nếu hash function tệ, mọi key đều chạy vào cùng 1 ô -> thoái hóa thành linked list -> O(n). Nên hash function tốt là linh hồn của hash table.

---

## 5. Pseudocode Implementation (Chaining)

```cpp
HASH_TABLE:
    size = 10
    buckets = array of 10 empty lists

FUNCTION hash(key):
    total = 0
    FOR each character c in key:
        total = total + ASCII(c)
    RETURN total % size

FUNCTION put(key, value):
    index = hash(key)
    bucket = buckets[index]
    // Nếu key đã tồn tại -> cập nhật
    FOR each pair (k, v) in bucket:
        IF k == key:
            pair.v = value
            RETURN
    // Chưa có -> thêm mới
    bucket.append( (key, value) )

FUNCTION get(key):
    index = hash(key)
    bucket = buckets[index]
    FOR each pair (k, v) in bucket:
        IF k == key:
            RETURN v
    RETURN NOT_FOUND

FUNCTION delete(key):
    index = hash(key)
    bucket = buckets[index]
    FOR each pair (k, v) in bucket:
        IF k == key:
            bucket.remove(pair)
            RETURN TRUE
    RETURN FALSE
```
**Dòng chảy khi gọi `get("An")`:**

`"An"` $\rightarrow$ `hash("An")` = $(65 + 110) \pmod{10} = 175 \pmod{10} = 5$
$\rightarrow$ đi thẳng đến `buckets[5]`
$\rightarrow$ duyệt bucket nhỏ, tìm key `"An"`
$\rightarrow$ trả về `value`

*Bucket thường chỉ có 1-2 phần tử (nếu hash tốt) -> gần như O(1).*

---

## 6. Tóm lại cho sinh viên năm nhất
Bản chất hash table trả lời đúng câu hỏi ban đầu: *"Tìm trong array chậm quá, có cách nào tính ra luôn vị trí không?"*

Có. Dùng một hàm (**hash function**) biến key thành số $\rightarrow$ số đó là vị trí trong mảng. **Trade-off** (sự đánh đổi) là phải xử lý khi hai key ra cùng vị trí (va chạm) và tốn thêm bộ nhớ. Nhưng đổi lại, tốc độ trung bình đạt $O(1)$ — nhanh gấp hàng trăm, hàng nghìn lần so với duyệt tuần tự.

Đó là lý do `dict` trong Python, `object`/`Map` trong JavaScript, `HashMap` trong Java (hay `std::unordered_map` / `std::unordered_set` trong C++) đều dùng Hash Table bên dưới — vì nó giải quyết bài toán "tìm nhanh theo key" một cách cực kỳ hiệu quả.
