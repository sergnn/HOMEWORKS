# POSTMAN
## _HOMEWORK 3, AUTOTESTS & SNIPPETS_

##### **REQUEST №5** 

3) http://162.55.220.72:5005/new_data
req.
POST
age: int
salary: int
name: str
auth_token

Resp.
{'name':name,
  'age': int(age),
  'salary': [salary, str(salary*2), str(salary*3)]}
  
***// 1) Статус код 200***
```sh
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

***// 2) Проверка структуры json в ответе.***

```sh
var schema = {here is a long schema, u can look at her}

[here](https://github.com/sergnn/HOMEWORKS/blob/main/POSTMAN/hw3.postman_collection) 

var result = tv4.validateResult(pm.response.json(), schema);
pm.test('Schema is valid', function () {
    pm.expect(result.valid).to.be.true;
});
```

***// 3) В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.***

```sh
var resp = pm.response.json();
var req = request.data;

pm.test("check salary0", function () {
    pm.expect(resp.salary[0]).to.eql(1000);
});

pm.test("check salary1", function () {
    pm.expect(+resp.salary[1]).to.eql(req.salary*2);
});

pm.test("check salary2", function () {
    pm.expect(+resp.salary[2]).to.eql(req.salary*3);
});
```

***// 4) проверить, что 2-й элемент массива salary больше 1-го и 0-го***

```sh
pm.test("check elements", function () {
    pm.expect(+resp.salary[2]).to.above(+resp.salary[1]);
    pm.expect(+resp.salary[2]).to.be.greaterThan(+resp.salary[0]);
});
```

##### **REQUEST №4** 

4) http://162.55.220.72:5005/test_pet_info
req.
POST
age: int
weight: int
name: str
auth_token


Resp.
{'name': name,
 'age': age,
 'daily_food':weight * 0.012,
 'daily_sleep': weight * 2.5}

***// 1) Статус код 200***
```sh
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

***// 2) Проверка структуры json в ответе.***

```sh
var schema = {here is a long schema, u can look at her}

[here](https://github.com/sergnn/HOMEWORKS/blob/main/POSTMAN/hw3.postman_collection) 

var result = tv4.validateResult(pm.response.json(), schema);
pm.test('Schema is valid', function () {
    pm.expect(result.valid).to.be.true;
});
```

***// 3) В ответе указаны коэффициенты умножения weight, напишите тесты по проверке правильности результата перемножения на коэффициент.***

```sh
var resp = pm.response.json();
var req = request.data;

pm.test("check weight", function () {
    pm.expect(resp.daily_sleep).to.eql(req.weight*2.5);
});

pm.test("check check weight2", function () {
    pm.expect(resp.daily_food).to.eql(req.weight*0.012);
});
```

##### **REQUEST №5** 

5) http://162.55.220.72:5005/get_test_user
req.
POST
age: int
salary: int
name: str
auth_token

Resp.
{'name': name,
 'age':age,
 'salary': salary,
 'family':{'children':[['Alex', 24],['Kate', 12]],
 'u_salary_1.5_year': salary * 4}
  }
  
***// 1) Статус код 200***
```sh
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

***// 2) Проверка структуры json в ответе.***

```sh
var schema = {here is a long schema, u can look at her}

[here](https://github.com/sergnn/HOMEWORKS/blob/main/POSTMAN/hw3.postman_collection) 

var result = tv4.validateResult(pm.response.json(), schema);
pm.test('Schema is valid', function () {
    pm.expect(result.valid).to.be.true;
});
```

***// 3) Проверить что значение поля name = значению переменной name из окружения***
```sh
var resp = pm.response.json();

pm.test("check var", function () {
    pm.expect(resp.name).to.eql(pm.environment.get("name"));
});
```
***// 4) Проверить что занчение поля age в ответе соответсвует отправленному в запросе значению поля age***

```sh
var req = request.data;

pm.test("check age", function () {
    pm.expect(resp.age).to.eql(req.age);
});
```


