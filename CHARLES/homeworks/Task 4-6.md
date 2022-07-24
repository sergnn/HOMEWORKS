# Charles
![](https://cdn-laravel.vapor.cloud/image/nstack/translate_values/charles_IPjFgz7Fvv.png)
## _Homework. Traffic capture_

```sql
Protocol: http
IP: 162.55.220.72
Port: 5005
```

**4. Сделать и в Rewrite, и в BreakPoint (можно отключить чтобы не стопило на каждом запросе)
-Сделать через Charles так, чтобы сервер вернул 500 код.
-Сделать через Charles так, чтобы сервер вернул 405 код.**

```sql
Method: GET
EndPoint: /object_info_3
request url params: 
 name: str
 age: int
 salary: int

response: 
{'name': name,
          'age': age,
          'salary': salary,
          'family': {'children': [['Alex', 24], ['Kate', 12]],
                     'pets': {'cat':{'name':'Sunny',
                                     'age': 3},
                              'dog':{'name':'Luky',
                                     'age': 4}},
                     'u_salary_1_5_year': salary * 4}
          }
```
## ***[Link here. Task 4 completion](https://drive.google.com/file/d/1gHcipFlkGOvFiHbhBbyZN0ky-QgMcstL/view?usp=sharing)***


***5. Сделать и в Rewrite, и в BreakPoint (можно отключить чтобы не стопило на каждом запросе)
 ⁃ Сделать через Charles так, чтобы сервер вернул 405 ошибку.
 ⁃ Подменить salary в request
 ⁃ Подменить (salary * 2) в response***

```sql
Method: GET
EndPoint: /object_info_4
request url params: 
 name: str
 age: int
 salary: int

response: 
{'name': name,
          'age': int(age),
          'salary': [salary, str(salary * 2), str(salary * 3)]}
```
## ***[Link here. Task 5 completion](https://drive.google.com/file/d/186LPg67Ajh-nA6O7uNxmoMeOg0CMdRgN/view?usp=sharing)***

***6. Сделать и в Rewrite, и в BreakPoint (можно отключить чтобы не стопило на каждом запросе)
 ⁃ Сделать через Charles так, чтобы в Postman вернулся ответ, в котором qa_salary_after_1.5_year переименовано в qa_salary_after_1.5_month
 ⁃ Сделать так чтобы qa_salary_after_3.5_years было меньше qa_salary_after_12_months в response.***

```sql
Ex_6:
Method: POST
EndPoint: /user_info_2
request form data: 
 name: str
 age: int
 salary: int

response: 
{'start_qa_salary': salary,
          'qa_salary_after_6_months': salary * 2,
          'qa_salary_after_12_months': salary * 2.7,
          'qa_salary_after_1.5_year': salary * 3.3,
          'qa_salary_after_3.5_years': salary * 3.8,
          'person': {'u_name': [user_name, salary, age],
                     'u_age': age,
                     'u_salary_5_years': salary * 4.2}
          }

```
## ***[Link here. Task 6 completion](https://drive.google.com/file/d/1Y8dfaDjO5kj7myOzoMGDDOPDaKwYW7K_/view?usp=sharing)***
























