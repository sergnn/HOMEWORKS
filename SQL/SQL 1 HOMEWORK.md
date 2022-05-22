# SQL
## _Homework 1 in DBeaver_

***1. Вывести все поля и все строки***

```sql
select * from students;
```

***2. Вывести всех студентов в таблице***

```sql
select * from students;
```

***3. Вывести только Id пользователей***

```sql
select id from students;
```

***4. Вывести только имя пользователей***

```sql
select name from students;
```

***5. Вывести только email пользователей***

```sql
select email from students;
```

***6. Вывести имя и email пользователей***

```sql
select name, email from students;
```

***7. Вывести id, имя, email и дату создания пользователей***

```sql
select id, name, email, created_on from students;
```

***8. Вывести пользователей где password 12333***

```sql
select * from students where password = '12333';
```

***9. Вывести пользователей которые были созданы 2021-03-26 00:00:00***

```sql
select * from students where created_on = '2021-03-26 00:00:00.000';
```

***10. Вывести пользователей где в имени есть слово Анна***

```sql
select * from students where name like '%Anna%';
```

***11. Вывести пользователей где в имени в конце есть 8***

```sql
select * from students where name like '%8';
```

***12. Вывести пользователей где в имени в есть буква а***

```sql
select * from students where name like '%a%';
```

***13. Вывести пользователей которые были созданы 2021-07-12 00:00:00***

```sql
select * from students where created_on = '2021-07-12 00:00:00';
```

***14. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и имеют пароль 1m313***
```sql
select * from students where created_on = '2021-07-12 00:00:00' and password = '1m313';
```
***15. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть слово Andrey***
```sql
select * from students where created_on = '2021-07-12 00:00:00' and name like '%Andrey%';
```
***16. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть цифра 8***
```sql
select * from students where created_on = '2021-07-12 00:00:00' and name like '%8%';
```
***17. Вывести пользователя у которых id равен 110***
```sql
select * from students where id = 110;
```
***18. Вывести пользователя у которых id равен 153***
```sql
select * from students where id = 153;
```
***19. Вывести пользователя у которых id больше 140***
```sql
select * from students where id > 140;
```
***20. Вывести пользователя у которых id меньше 130***
```sql
select * from students where id < 130;
```
***21. Вывести пользователя у которых id меньше 127 или больше 188***
```sql
select * from students where id < 127 OR id > 188;
```
***22. Вывести пользователя у которых id меньше либо равно 137***
```sql
select * from students where id <= 137;
```
***23. Вывести пользователя у которых id больше либо равно 137***
```sql
select * from students where id >= 137;
```
***24. Вывести пользователя у которых id больше 180 но меньше 190***
```sql
select * from students where id > 180 and id < 190;
```
***25. Вывести пользователя у которых id между 180 и 190***
```sql
select * from students where id between 180 and 190;
```
***26. Вывести пользователей где password равен 12333, 1m313, 123313***
```sql
select * from students where password = '12333' or password = '1m313' or password = '123313';
```
***27. Вывести пользователей где created_on равен 2020-10-03 00:00:00, 2021-05-19 00:00:00, 2021-03-26 00:00:00***
```sql
select * from students where created_on = '2020-10-03 00:00:00' or created_on = '2021-05-19 00:00:00' or created_on = '2021-03-26 00:00:00';
```
***28. Вывести минимальный id***
```sql
select min(id) as min from students;
```
***29. Вывести максимальный***
```sql
select max(id) as max from students;
```
***30. Вывести количество пользователей***
```sql
select count(id) from students;
```
***31. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку возрастания даты добавления пользователя***
```sql
select id, name, created_on from students order by created_on asc;
```
***32. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку убывания даты добавления пользователя***
```sql
select id, name, created_on from students order by created_on desc;
```


