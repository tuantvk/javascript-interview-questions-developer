# Danh sách những câu hỏi trong phỏng vấn Javascript

Những lý thuyết này cung cấp cho bạn danh sách các câu hỏi phỏng vấn JavaScript thường được hỏi với câu trả lời cho người mới bắt đầu. Các câu hỏi không sắp xếp theo thứ tự khó dần lên bạn có thể lướt hết qua mọi thứ để thử thách bản thân mình.

Nếu bạn có câu hỏi phỏng vấn JavaScript nào hay thì chia sẻ cho mọi người bằng cách bằng cách tạo **issue** hoặc **pull request** cho mình :rocket:.

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