# Danh sách những câu hỏi trong phỏng vấn Javascript

Những lý thuyết này cung cấp cho bạn danh sách các câu hỏi phỏng vấn JavaScript thường được hỏi với câu trả lời cho người mới bắt đầu. Các câu hỏi không sắp xếp theo thứ tự khó dần lên bạn có thể lướt hết qua mọi thứ để thử thách bản thân mình.

Nếu bạn có câu hỏi phỏng vấn JavaScript nào hay thì chia sẻ cho mọi người bằng cách bằng cách tạo **issue** hoặc **pull request** cho mình :rocket:.

Danh sách các ngôn ngữ khác:
* [English](./README_EN.md)

Let's go !!!

## Câu 1: Sự khác nhau giữa JavaScript và JScript là gì?

Đơn giản bạn có thể nói JScript giống như JavaScript, nhưng nó được cung cấp bởi Microsoft.

---

## Câu 2: Trong javascript đối tượng window được sử dụng để làm gì?

Đối tượng window được tạo tự động bởi trình duyệt đại diện cho một cửa sổ trình duyệt. Nó được sử dụng để hiển thị hộp thoại bật lên như hộp thoại alert, confirm, v.v. và mọi thứ trong Javascript như __object, functions, variables__ đều có thể trở thành __window object__ bao gồm cả __HTML DOM__.

<details><summary><b>Ví dụ:</b></summary>
<p>
<code>
window.document.getElementById("header");
</code><br />
hoặc:
<br />
<code>
document.getElementById("header");
</code>

<p>
</details>

---

## Câu 3: Sự khác nhau giữa == và === là gì?

Toán tử __==__ chỉ kiểm tra tính bằng nhau, còn __===__ kiểm tra tính bằng nhau và giá trị kiểu dữ liệu tức là phải cùng kiểu dữ liệu.

#### Ví dụ:

```javascript
var number1 = 12;
var number2 = '12';

console.log('log 1: ', number1 == number2)
console.log('log 2: ', number1 === number2)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>log 1: true</code><br />
<code>log 2: false</code>
<p>
</details>

---

## Câu 4: Negative Infinity là gì?

<code></code><br />
__Negative Infinity__ là một số trong JavaScript có thể được bắt nguồn bằng cách chia số âm cho 0. Khi nào sử dung nó, khi nó là __một số__ hoặc __Number object__ và nó sẽ return về  __undefined__.

#### Ví dụ:

```javascript
var my_number = 100;
my_number.NEGATIVE_INFINITY;

console.log(my_number)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>undefined</code>
<p>
</details>

---

## Câu 5: Cách để xử lý các ngoại lệ trong JavaScript?

Sử dụng khối __try/catch__, chúng ta có thể xử lý các ngoại lệ trong JavaScript. JavaScript hỗ trợ các từ khóa try, catch, finally, throw để xử lý ngoại lệ.

#### Ví dụ:

```javascript
function check(x) {
  try {
    if (x == "") throw "empty";
    if (isNaN(x)) throw "not a number";
    x = Number(x);
    if (x < 5) throw "too low";
    if (x > 10) throw "too high";
  }
  catch (err) {
    console.log("catch ", err)
  }
}

console.log(check(""))
console.log(check("test"))
console.log(check(55))
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>catch  empty</code><br />
<code>undefined</code><br />
<code>catch  not a number</code><br />
<code>undefined</code><br />
<code>catch  too high</code><br />
<code>undefined</code><br />
<p>
</details>

---

## Câu 6: Hàm isNaN() là gì?

Hàm __isNaN()__ trả về true nếu giá trị của biến __không phải__ là một số.

#### Ví dụ:

```javascript
console.log(isNaN(123))
console.log(isNaN(0))
console.log(isNaN('Hello'))
console.log(isNaN('2005/12/12'))
console.log(isNaN(''))
console.log(isNaN(true))
console.log(isNaN(undefined))
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>false</code><br />
<code>false</code><br />
<code>true</code><br />
<code>true</code><br />
<code>false</code><br />
<code>false</code><br />
<p>
</details>

---

## Câu 7: Cách để comment trong Javascript?

Sử dụng __//__ cho một dòng

hoặc 

sử dụng __/* nội dung */__ cho nhiều dòng

#### Ví dụ:

```javascript
// Khai báo biến
var number = 2;

/*
  Đây là cách
  để comment
  nhiều dòng
*/
var girl_friend = null;
```

---

## Câu 8: Tại sao 0.1 + 0.2 không bằng 0.3 ?

Vấn đề này liên quan đến việc Javascript lưu trữ dữ liệu float ở dạng nhị phân chính xác tới từng con số sau dấu phẩy.

**Giải pháp:**

- Sử dụng hàm __toFixed()__
- __Mẹo nhỏ__ là nhân với 10 và chia cho 10
- Tham khảo các hàm làm tròn như __round()__, v.v.

#### Ví dụ:

```javascript
console.log(0.1 + 0.2)

// Amazing !
var x = (0.2 * 10 + 0.1 * 10) / 10;
console.log(x)  

// Sử dụng toFixed()
var number = 0.1 + 0.2;
console.log(number.toFixed(2))
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>0.30000000000000004</code><br />
<code>0.3</code><br />
<code>0.3</code>
<p>
</details>

---

## Câu 9: Phân biệt giữa Function Declaration và Function Expression.

__Function declaration__ sử dụng từ khóa function rồi đến tên hàm. Còn __Function expression__ bắt đầu bằng __var__, __let__ hoặc __const__, theo sau là tên của hàm và toán tử __=__.

#### Ví dụ:

```javascript
// Function Declaration
 function sum(x, y) {
   return x + y;
 };
 
 // Function Expression: ES5
 var sum = function(x, y) {
   return x + y;
 };
 // Function Expression: ES6+
 const sum = (x, y) => { return x + y };

```

---

## Câu 10: Tại sao Math.max() lại nhỏ hơn Math.min().

Khi chạy code __Math.max() > Math.min()__, giá trị trả về là __False__, nghe có vẻ không hợp lý. Tuy nhiên, nếu không có tham số nào được truyền vào, __Math.min()__ trả về __Infinity__ và __Math.max()__ trả về __-Infinity__. Vậy nên __Math.max() < Math.min()__.

Nếu tham số xuất hiện là infinity và một số nào khác, kết quả trả về sẽ là số có giá trị đó.

#### Ví dụ:

```javascript
var infinity = 5

var value1 = Math.min(1)
var value2 = Math.min(1, infinity)
var value3 = Math.min(1, -infinity)

console.log(value1)
console.log(value2)
console.log(value3)

```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>1</code><br />
<code>1</code><br />
<code>-5</code><br />
<p>
</details>

---