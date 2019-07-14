# Danh sách những câu hỏi trong phỏng vấn Javascript

Những lý thuyết này cung cấp cho bạn danh sách các câu hỏi phỏng vấn JavaScript thường được hỏi với câu trả lời cho người mới bắt đầu. Các câu hỏi không sắp xếp theo thứ tự khó dần lên bạn có thể lướt hết qua mọi thứ để thử thách bản thân mình.

Nếu bạn có câu hỏi phỏng vấn JavaScript nào hay thì chia sẻ cho mọi người bằng cách bằng cách tạo **issue** hoặc **pull request** cho mình :rocket:.

Danh sách các ngôn ngữ khác:
* [English](./README_EN.md)

Let's go !!!


## Câu 0: Javascript là gì?

__JavaScript__, theo phiên bản hiện hành, là một ngôn ngữ lập trình thông dịch được phát triển từ các ý niệm nguyên mẫu. Ngôn ngữ này được dùng rộng rãi cho các trang web (phía người dùng) cũng như phía máy chủ (với __Nodejs__).

---

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

## Câu 11: Closure trong Javascript là gì?

Dể hiểu, closure là 1 hàm nội truy cập đến các biến bên ngoài phạm vi của nó. Closure có thể được sử dụng để __implement privacy__ và tạo ra các __function factory__.

#### Ví dụ:

```javascript
const arr = [1, 2, 3, 4];

for (var i = 0; i < arr.length; i++) {
  setTimeout(function() {
    console.log(i);
  }, 10);
}
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>4</code><br />
<code>4</code><br />
<code>4</code><br />
<code>4</code><br />

Lý do là bởi vì hàm setTimeout sẽ tạo ra 1 function (closure) có thể truy cập phạm vi bên ngoài nó, vòng loop sẽ chứa index i. Sau 10ms, hàm được thực thi và nó sẽ log ra giá trị của i, là giá trị cuối cùng của vòng lặp (4).
<p>
</details>

---

## Câu 12: Hàm encodeURI() là gì?

Hàm này mã hóa các ký tự đặc biệt, ngoại trừ :, /? : @ & = + $ #

Để mã hóa ngược chuỗi đó lại mình sử dụng hàm __decodeURI()__.

#### Ví dụ:

```javascript
var uri = "my test.asp?name=ståle&car=saab";
var res = encodeURI(uri);

console.log(res)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>my%20test.asp?name=st%C3%A5le&car=saab</code><br />
<p>
</details>

---

## Câu 13: Array() khác với [] như nào trong khi tạo ra một array trong JavaScript?

Nếu sử dụng cách tạo array initializer nó sẽ tạo ra danh sách các phần tử trong mảng và được ngăn cách bởi dấu phẩy.

#### Ví dụ:

```javascript
var arr1 = [5]
var arr2 = new Array(5)

console.log(arr1)
console.log(arr2)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>[ 5 ]</code><br />
<code>[ <5 empty items> ]</code>
<p>
</details>

---

## Câu 14: Strict mode trong JavaScript là gì?

Strict theo nghĩa tiếng Việt là "nghiêm khắc". Strict Mode là một quy mẫu nghiêm khắc trong Javascript. Nếu như việc viết code bình thường là Normal mode, thì Strict Mode sẽ có thêm các quy định khác so với Normal mode. 

#### Ví dụ:

```javascript
"use strict";

function foo(){
  var bar = 0;
  return bar;
}

bar = 1;
```

<details><summary><b>Đáp án:</b></summary>
<p>
Xảy ra lỗi:
<code>ReferenceError: bar is not defined</code><br />
<p>
</details>

---

## Câu 15: Variable typing trong JavaScript là gì?

JavaScript là một ngôn ngữ rất lỏng lẻo. Biến chỉ được xác định khi giá trị được gán và có thể thay đổi khi biến xuất hiện trong các ngữ cảnh khác nhau. Lên đơn giản nó là kiểu dữ liệu của biến đó.

Để kiểm tra kiểu dữ liệu của biến đó ta dùng __typeof__ trong Javascript.

#### Ví dụ:

```javascript
var length = 16;
var lastName = "Johnson";
var x = { firstName: "John", lastName: "Doe" };

console.log(typeof length)
console.log(typeof lastName)
console.log(typeof x)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>number</code><br />
<code>string</code><br />
<code>object</code>
<p>
</details>

---

## Câu 16: Các kiểu dữ liệu trong Javascript là gì?

Javascript có những kiểu dữ liệu sau:

- Number
- String
- Boolean
- Object
- Undefined

#### Ví dụ:

```javascript
var a = 5;
var b = "Hello";
var c = true;
var d = { id: 1, name: "Lyly" };

console.log(typeof a)
console.log(typeof b)
console.log(typeof c)
console.log(typeof d)
console.log(typeof e)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>number</code><br />
<code>string</code><br />
<code>boolean</code><br />
<code>object</code><br />
<code>undefined</code>
<p>
</details>

---

## Câu 17: `this` trong Javascript là gì?

Từ khóa __this__ dùng để chỉ đối tượng từ nơi nó được gọi.

#### Ví dụ:

```javascript
var Student = {
  name: "Lyly",
  age: 20,
  getName: function(){
      return this.name;
  }
};

console.log(Student.getName())
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>Lyly</code><br />
<p>
</details>

---

## Câu 18: Khác nhau giữa ViewState và SessionState là gì?

- __ViewState__ là dành riêng cho một trang trong phiên.

- __SessionState__ dành riêng cho dữ liệu cụ thể của người dùng có thể được truy cập trên tất cả các trang trong ứng dụng web.

---

## Câu 19: Làm sao để thay đổi style/class của element?

Có thể sử dụng document để thay đổi style/class.

#### Ví dụ:

```javascript
document.getElementById("myId").style.fontSize = "20px";

// or

document.getElementById("myId").className = "newclass";
```

---

## Câu 20: Các cấu trúc lặp trong Javascript là gì?

Có các vòng lặp sau:

- for
- while
- do-while loops

#### Ví dụ:

```javascript
var arr = ["apple", "banana", "mango", "cherry"]

// Sử dụng for
for (let i = 0; i < arr.length; i++) {
  console.log(arr[i]);
}

// Sử dụng while
let j = 0;
while (j < arr.length) {
  console.log(arr[j]);
  j++;
}

// Sử dụng do-while loops
let k = 0;
do {
  console.log(arr[k]);
  k++;
} while (k < arr.length)

```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>cherry</code><br />
<code>apple</code><br />
<code>banana</code><br />
<code>mango</code><br />
<p>
</details>

---

## Câu 21: Kết quả của `5 + 2 + "7"` là gì?

Vì 3 và 2 là số nguyên, chúng sẽ cộng vào với nhau và kết quả là số. Còn 7 là một chuỗi, nên Javascipt sẽ hiểu thành nối chuỗi. Vì vậy, kết quả sẽ là 77.

#### Ví dụ:

```javascript
console.log(5 + 2 + "7");
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>77</code><br />
<p>
</details>

---

## Câu 22: Chức năng của `delete` là gì?

__delete__ dùng để xóa các property cũng như các giá trị.

#### Ví dụ:

```javascript
var student = { name: 'Lyly', age: 20 };

delete student.age;

console.log(student)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>{ name: 'Lyly' }</code><br />
<p>
</details>

---

## Câu 23: Hàm `pop()` trong Javascript để làm gì?

__pop()__ trong Javascript dùng để lấy phần tử cuối cùng trong mảng. Điều này thì trái ngược với hàm __shift()__.

#### Ví dụ:

```javascript
var number = ["one", "two", "three", "four"]

console.log(number.pop())
console.log(number.shift())
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>four</code><br />
<code>one</code>
<p>
</details>

---

## Câu 24: Kết quả in ra là gì?

#### Ví dụ:

```javascript
var myArray = [[[]]];

console.log(myArray)
```

<details><summary><b>Đáp án:</b></summary>
<p>
Là một mảng 3 chiều
<code>[ [ [] ] ]</code><br />
<p>
</details>

---

## Câu 25: `let` và `const` trong Javascript là gì?

Từ khóa __let__ & __const__ được giới thiệu trong phiên bản ES6 với tầm nhìn tạo ra hai loại biến khác nhau trong javascript, một loại là bất biến và loại khác là có thể thay đổi.

- __const__: Nó được sử dụng để tạo ra một biến bất biến. Biến không thay đổi là các biến có giá trị không bao giờ thay đổi trong vòng đời hoàn chỉnh của chương trình.

- __let__: let được sử dụng để tạo một biến có thể thay đổi. Các biến có thể thay đổi là các biến bình thường như var có thể thay đổi bất kỳ số lượng thời gian nào.

#### Ví dụ:

```javascript
let name  = "Lyly";

const age = 18;

name = "John";
age = 20;

console.log(name)
console.log(age)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>John</code><br />
<code>TypeError: Assignment to constant variable.</code>
<p>
</details>

---

## Câu 26: Làm sao để thêm hoặc xóa sửa trong object Javascript?

Ta có thể thêm một thuộc tính vào một đối tượng bằng __object.property_name = value__, __delete object.property_name__ để xóa một thuộc tính.

#### Ví dụ:

```javascript
let user = new Object();

user.name = 'Lyly';
user.age = 20;

console.log(user);

delete user.age;

console.log(user);
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>{ name: 'Lyly', age: 20 }</code><br />
<code>{ name: 'Lyly' }</code>
<p>
</details>

---

## Câu 27: Cách để xóa các phần tử giống nhau trong mảng sử dụng ES6?

Dưới đây là một số cách:

#### Ví dụ:

```javascript
var array = [1, 2, 6, 5, 3, 2, 6];

// Sử dụng Set
console.log(...new Set(array))

// Sử dụng filter
console.log(
  array.filter((item , index ) => 
    array.indexOf(item) === index 
  )
)

// Sử dụng reduce
console.log(
  array.reduce((uniq, item) => 
    uniq.includes(item) ? uniq : [...uniq, item], [] 
  )
)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code></code><br />
<code>1 2 6 5 3</code><br />
<code>[ 1, 2, 6, 5, 3 ]</code><br />
<code>[ 1, 2, 6, 5, 3 ]</code>
<p>
</details>

---

## Câu 28: Khác nhau giữa từ khóa `undefined` và `null` là gì?

Khi bạn khởi tạo ra một biến nhưng không gán giá trị cho nó thì sẽ là __undefined__. Còn __null__ là một __object__.

#### Ví dụ:

```javascript
var a;

console.log(typeof a)
console.log(typeof null)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>undefined</code><br />
<code>object</code>
<p>
</details>

---

## Câu 29: Một số Framework để test Javascript là gì?

Các framework phổ biến nhất hiện nay:

- Unit.js
- Jasmine
- Karma
- Chai
- AVA
- Mocha
- JSUnit
- QUnit
- Jest

#### Ví dụ:

```javascript
// Sử dụng Chai
var answer = 43;

expect(answer).to.equal(42);
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>AssertionError: expected 43 to equal 42.</code><br />
<p>
</details>

---

## Câu 30: `export` và `import` là gì?

__export__ hay __import__ là cách để ta tạo ra các module trong Javascript. Bằng cách đó, ta có thể chia các phần nhỏ trong dự án để dễ quản lý. __import__ cho phép ta lấy một số biến hoặc một phương thức nào đó của file. Còn __export__ là biến một file thành một module. Xem ví dụ để hiểu hơn.

#### Ví dụ:

```javascript
// person.js

let name = 'Lyly', occupation = 'developer', age = 20;

export {
  name,
  age,
}; 

//index.js

import { name, age } from './person';

console.log(name);
console.log(age);
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>Lyly</code><br />
<code>20</code>
<p>
</details>

---

## Câu 31: Làm sao để chuyển đổi ngày trong Javascript thành tiêu chuẩn ISO?

Hàm __toISOString()__ được sử dụng để chuyển đổi ngày javascript thành tiêu chuẩn ISO. Nó chuyển đổi đối tượng Ngày JavaScript thành một chuỗi, sử dụng tiêu chuẩn ISO.

#### Ví dụ:

```javascript
var date = new Date();
var n = date.toISOString();

console.log(n);
// YYYY-MM-DDTHH:mm:ss.sssZ
```

---

## Câu 32: Cách đẻ clone một object trong Javascript?

Hàm Object.assign() được sử dụng để clone một đối tượng trong Javascript. Ngoài ra bạn cũng có thể sử dụng clone của __lodash__. Lodash là một framework sử lý mạnh mẽ mảng và object. Xem thêm tại [Lodash](https://lodash.com/)

#### Ví dụ:

```javascript
var x = { name: "Lyly" };
var y = Object.assign({}, x); 

console.log(y)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>{ name: 'Lyly' }</code><br />
<p>
</details>

---

## Câu 33: Cách để tạo mảng trong Javascript?

Có 3 cách khác nhau để tạo mảng trong Javascript. Xem ví dụ

#### Ví dụ:

```javascript
var arr1 = [1, 2, 3, 4];

var arr2 = new Array();

var arr3 = new Array(1, 2, 3, 4);

console.log(arr1)
console.log(arr2)
console.log(arr3)
```

<details><summary><b>Đáp án:</b></summary>
<p>
<code>[ 1, 2, 3, 4 ]</code><br />
<code>[]</code><br />
<code>[ 1, 2, 3, 4 ]</code>
<p>
</details>

---