# POSTMAN
## _HOMEWORK 1, AUTOTESTS & SNIPPETS_

##### **REQUEST №3** 

***// 1. Отправить запрос***
***GET*** http://162.55.220.72:5005/object_info_3?name=serg&age=28&salary=1000

***// 2. Статус код 200***

```sh
    pm.test("Verify status 200", function () {
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

***// 6. Проверить, что age в ответе равно age s request (age забрать из request.)***

```sh
    pm.test("age=age s request", function () {
    pm.expect(response.age).to.eql(request.age);
});
```

***// 7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)***

```sh
    pm.test("salary=salary s request", function () {
    pm.expect(response.salary).to.eql(+request.salary);
});
```

***// 8. Вывести в консоль параметр family из response.***

```sh
console.log(response.family)
```

***// 9. Проверить, что у параметра dog есть параметры name.***

```sh
    pm.test("dog has name", function () {
    pm.expect(response.family.pets.dog).to.have.property('name');
});
```

***// 10. Проверить, что у параметра dog есть параметры age.***

```sh
    pm.test("dog has age", function () {
    pm.expect(response.family.pets.dog).to.have.property('age');
});
```

***// 11. Проверить, что параметр name имеет значение Luky.***

```sh
    pm.test("dog has name", function () {
    pm.expect(response.family.pets.dog.name).to.have.eql('Luky');
});
```

***// 12. Проверить, что параметр age имеет значение 4.***

```sh
    pm.test("age is 4", function () {
    pm.expect(response.family.pets.dog.age).to.have.eql(4);
});
```