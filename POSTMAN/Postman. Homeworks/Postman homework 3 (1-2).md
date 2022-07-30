# POSTMAN
## _HOMEWORK 3, AUTOTESTS & SNIPPETS_

##### **REQUEST №1** 

***1) необходимо залогиниться
POST
http://162.55.220.72:5005/login
login : str (кроме /)
password : str
Приходящий токен необходимо передать во все остальные запросы.
дальше все запросы требуют наличие токена***

***POST*** http://162.55.220.72:5005/login 
Body - form data - login : "sergey", password : "qwerty"
##### **RESPONCE №1**
```sh
{
    "token": "/s34lfgbj/sergey/jjd909/79379kjkWpqc3843qwerty76450evny"
}
```

##### **REQUEST №2** 

2) http://162.55.220.72:5005/user_info
req. (RAW JSON)
POST
age: int
salary: int
name: str
auth_token

```sh
{
    "age" : "{{age}}",
    "salary" : "{{salary}}",
    "name" : "{{name}}",
    "auth_token" : "{{token}}"
}
```


resp.
{'start_qa_salary':salary,
 'qa_salary_after_6_months': salary * 2,
 'qa_salary_after_12_months': salary * 2.9,
 'person': {'u_name':[user_name, salary, age],
                                'u_age':age,
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

***// 3) В ответе указаны коэффициенты умножения salary, напишите тесты по проверке правильности результата перемножения на коэффициент.***

```sh
var resp = pm.response.json();
var request = JSON.parse(request.data);

pm.test("check salary1", function () {
    pm.expect(resp.start_qa_salary).to.eql(1000);
});

pm.test("check salary2", function () {
    pm.expect(resp.qa_salary_after_6_months).to.eql(+request.salary*2);
});

pm.test("check salary3", function () {
    pm.expect(resp.qa_salary_after_12_months).to.eql(+request.salary*2.9);
});

pm.test("check salary4", function () {
    pm.expect(resp.person.u_salary_1_5_year).to.eql(+request.salary*4);
});
});
```

***// 4. Достать значение из поля 'u_salary_1.5_year' и передать в поле salary запроса http://162.55.220.72:5005/get_test_user***

```sh
pm.environment.set("secondsalary", resp.person.u_salary_1_5_year);
```












