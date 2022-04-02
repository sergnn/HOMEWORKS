# POSTMAN
## _HOMEWORK 2, AUTOTESTS & SNIPPETS_

- Protocol: http
- IP: 162.55.220.72
- Port: 5005

##### **REQUEST №1** 
***GET*** http://162.55.220.72:5005/first
1. Отправить запрос.
2. Статус код 200
3. Проверить, что в body приходит правильный string.
##### **RESPONSE №1**
```sh
This is the first responce from server!
```

##### **REQUEST №2** 
 ***// 1. Отправить запрос***
***POST*** http://162.55.220.72:5005/user_info_3
***// 2. Статус код 200***
```sh
    pm.test("Verify that Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

***// 3. Спарсить response body в json.***
```sh
var response_body = JSON.parse;
```

***// 4. Проверить, что name в ответе равно name s request (name вбить руками.)***
```sh   
var response = pm.response.json(); 

pm.test("name=name s request", function () {
    pm.expect(response.name).to.eql("serg");
});
```

***// 5. Проверить, что age в ответе равно age s request (age вбить руками.)***
```sh
    pm.test("age=age s request", function () {
    pm.expect(response.age).to.eql("28");
});
```

***// 6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)***
```sh
    pm.test("salary=salary s request", function () {
    pm.expect(response.salary).to.eql(1000);
});
```

***// 7. Спарсить request.***
```sh
var request = request.data;
console.log(request)
```
***// 8. Проверить, что name в ответе равно name s request (name забрать из request.)***

```sh
    pm.test("name=name s request", function () {
    pm.expect(response.name).to.eql(request.name);
});
```

***// 9. Проверить, что age в ответе равно age s request (age забрать из request.)***

```sh
    pm.test("age=age s request", function () {
    pm.expect(response.age).to.eql(request.age);
});
```

***// 10. Проверить, что salary в ответе равно salary s request (salary забрать из request***

```sh 
    pm.test("salary=salary s request", function () {
    pm.expect(response.salary).to.eql(+request.salary);
});
```

***// 11. Вывести в консоль параметр family из response.***

```sh
console.log(response.family)
```

**// 12. Проверить что u_salary_1_5_year в ответе равно salary * 4 (salary забрать из request)**

```sh
    pm.test("Verify about salary", function() {
    pm.expect(response.family.u_salary_1_5_year).to.eql(request.salary*4);
});
```
