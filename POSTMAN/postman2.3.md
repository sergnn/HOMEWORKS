# POSTMAN
## _HOMEWORK 1, AUTOTESTS & SNIPPETS_

##### **REQUEST №4** 

***// 1. Отправить запрос***
***GET*** http://162.55.220.72:5005/object_info_4?name=serg&age=28&salary=1000

***// 2. Статус код 200***

```sh
    pm.test("Verify status 200", function() {
    pm.response.to.have.status(200);
});
```

***// 3. Спарсить response body в json.***

```sh
var response_body = JSON.parse;
```

***// 4. Спарсить request.***

```sh
var request = request.data;
```

***// 5. Проверить, что name в ответе равно name s request (name забрать из request.)***
```sh
var response = pm.response.json();

    pm.test("name=name s request", function () {
    pm.expect(response.name).to.eql(request.name);
});
```
***// 6. Проверить, что age в ответе равно age из request (age забрать из request.)***

```sh
    pm.test("age=age s request", function () {
    pm.expect(response.age).to.eql(+request.age);
});
```
***// 7. Вывести в консоль параметр salary из request.***

```sh
console.log(request.salary);
```
***// 8. Вывести в консоль параметр salary из response.***

```sh
console.log(response.salary);
```
***// 9. Вывести в консоль 0-й элемент параметра salary из response.***

```sh
console.log(response.salary[0]);
```
***// 10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.***

```sh
console.log(response.salary[1]);
```
***// 11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.***

```sh
console.log(response.salary[2]);
```
***// 12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)***

```sh
    pm.test("salary0=salary s request", function () {
    pm.expect(response.salary[0]).to.eql(+request.salary);
});
```
***// 13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)***

```sh
    pm.test("salary2=salary s request", function () {
    pm.expect(+response.salary[1]).to.eql(request.salary*2);
});
```
***// 14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из из request.)***

```sh
    pm.test("salary3=salary s request", function () {
    pm.expect(+response.salary[2]).to.eql(request.salary*3);
});
```

***// 15. Создать в окружении переменную name***
***// 16. Создать в окружении переменную age***
***// 17. Создать в окружении переменную salary***

```sh
var name = response.name;
var age = response.age;
var salary = response.salary;
```
***// 18. Передать в окружение переменную name***
***// 19. Передать в окружение переменную age***
***// 20. Передать в окружение переменную salary***

```sh
pm.environment.set("name", "serg");
pm.environment.set("age", 28);
pm.environment.set("salary", 1000);
```
***// 21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.***

```sh
var step = 0;
while (step < 1) {
    postman.setNextRequest(response.salary);
    console.log(+response.salary[0]);
    console.log(+response.salary[1]);
    console.log(+response.salary[2]);
    step++;
}  
```