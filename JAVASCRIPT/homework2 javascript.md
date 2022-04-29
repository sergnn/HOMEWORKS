# JAVASCRIPT
## _HOMEWORK 2_

## _Напишите валидационный скрипт используя функции_

***//  1. Скрипт должен на вход принимать строку.
//  2. После проверки строки выводить в консоль сообщение где будет конкретно написано, что не так в ведённой строке.
//  3. Минимум 5 символов в строке
//  4. Максимум 64 символа в строке
//  5. В строке должны быть буквы
//  6. Должна быть хотя бы одна буква в верхнем регистре
//  7. Должна быть хотя бы одна цифра
//  8. Должна быть хотя бы одна @
//  9. Строка не должна быть пустой***

```sh
let letter = /[a-zA-Zа-яА-Я]/;
let bigletters = /[A-ZА-Я]/;
let numbers = /[0-9]/;
var password = "12345aA@";


if (typeof password !== 'string') {
console.log ("Тип данных - ", typeof password);
    } else if (password.length == 0) {
console.log('Строка не должна быть пустой');
    } else if (!letter.test(password)) {
console.log("Необходима хотя бы 1 буква");
    } else if (password.length < 5) {
console.log("Меньше 5");
    } else if (password.length > 64) {
console.log ("Больше 64");
    } else if (!bigletters.test(password)) {
console.log("Хотя бы одна заглавная буква");
    } else if (!numbers.test(password)) {
console.log("Должна быть хотя бы одна цифра");
    } else if (!password.includes("@")) {
console.log('Должна быть хотя бы одна @');
    };
```






