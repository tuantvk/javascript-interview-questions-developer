# Danh sách những câu hỏi trong phỏng vấn Javascript

Những lý thuyết này cung cấp cho bạn danh sách các câu hỏi phỏng vấn JavaScript thường được hỏi với câu trả lời cho người mới bắt đầu. Các câu hỏi không sắp xếp theo thứ tự khó dần lên bạn có thể lướt hết qua mọi thứ để thử thách bản thân mình.

Nếu bạn có câu hỏi phỏng vấn JavaScript nào hay thì chia sẻ cho mọi người bằng cách bằng cách tạo **issue** hoặc **pull request** cho mình.

Let's go !!!

## Câu 1: Sự khác nhau giữa JavaScript và JScript là gì?

Đơn giản bạn có thể nói JScript giống như JavaScript, nhưng nó được cung cấp bởi Microsoft.

---

## Câu 2: Trong javascript đối tượng window được sử dụng để làm gì?

Đối tượng window được tạo tự động bởi trình duyệt đại diện cho một cửa sổ trình duyệt. Nó được sử dụng để hiển thị hộp thoại bật lên như hộp thoại alert, confirm, v.v. và mọi thứ trong Javascript như __object, functions, variables__ đều có thể trở thành __window object__ bao gồm cả __HTML DOM__.

<details><summary><b>Ví dụ:</b></summary>
<p>
window.document.getElementById("header");

hoặc:

document.getElementById("header");

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
log 1: true

log 2: false
<p>
</details>

---