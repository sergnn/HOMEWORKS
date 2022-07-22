[![N|Solid](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRUEqQLS3O85FLB-K8jA0f2K8p7fWGUrzq1qQ&usqp=CAU)](https://sql-ex.ru/)

## SQL-ex.ru Exercises

#### **[Схема базы данных](https://sql-ex.ru/help/select13.php#db_1)**

Схема БД состоит из четырех таблиц:
**Product(maker, model, type)**
**PC(code, model, speed, ram, hd, cd, price)**
**Laptop(code, model, speed, ram, hd, price, screen)**
**Printer(code, model, color, type, price)**
Таблица **Product** представляет производителя (maker), номер модели (model) и тип ('PC' - ПК, 'Laptop' - ПК-блокнот или 'Printer' - принтер). Предполагается, что номера моделей в таблице **Product** уникальны для всех производителей и типов продуктов. В таблице **PC** для каждого ПК, однозначно определяемого уникальным кодом – code, указаны модель – model (внешний ключ к таблице **Product**), скорость - speed (процессора в мегагерцах), объем памяти - ram (в мегабайтах), размер диска - hd (в гигабайтах), скорость считывающего устройства - cd (например, '4x') и цена - price (в долларах). Таблица **Laptop** аналогична таблице **РС** за исключением того, что вместо скорости CD содержит размер экрана -screen (в дюймах). В таблице **Printer** для каждой модели принтера указывается, является ли он цветным - color ('y', если цветной), тип принтера - type (лазерный – 'Laser', струйный – 'Jet' или матричный – 'Matrix') и цена - price.






**Задание 15: Найдите размеры жестких дисков, совпадающих у двух и более PC. Вывести: HD** 
```sql
select hd from pc group by hd having count(model) >= 2;
```

**Задание 16: Найдите пары моделей PC, имеющих одинаковые скорость и RAM. В результате каждая пара указывается только один раз, т.е. (i,j), но не (j,i), Порядок вывода: модель с большим номером, модель с меньшим номером, скорость и RAM.**
```sql
select distinct a.model, b.model, a.speed, a.ram from pc a, pc b
where a.ram = b.ram and a.speed = b.speed and a.model > b.model;
```

**Задание 17: Найдите модели ПК-блокнотов, скорость которых меньше скорости каждого из ПК. Вывести: type, model, speed**
```sql
select distinct type, laptop.model, speed from laptop join product on laptop.model = product.model where speed < (select MIN(speed) from pc);
```

**Задание 18: Найдите производителей самых дешевых цветных принтеров. Вывести: maker, price**
```sql
select distinct maker, price from product join printer on product.model = printer.model where color = 'y' and price = (select min(price) from printer where color = 'y');
```

**Задание 19: Для каждого производителя, имеющего модели в таблице Laptop, найдите средний размер экрана выпускаемых им ПК-блокнотов. Вывести: maker, средний размер экрана.**
```sql
select maker, AVG(screen) AS Avg_screen from product join laptop on product.model = laptop.model group by maker;
```

**Задание 20: Найдите производителей, выпускающих по меньшей мере три различных модели ПК. Вывести: Maker, число моделей ПК.**
```sql
select maker, COUNT(model) AS count_model from product where type = 'PC' group by maker having count(model) >=3
```

**Задание 21: Найдите максимальную цену ПК, выпускаемых каждым производителем, у которого есть модели в таблице PC. Вывести: maker, максимальная цена.**

```sql
select maker, MAX(price) AS max_price from product join PC on product.model = pc.model group by maker
```

**Задание 22: Для каждого значения скорости ПК, превышающего 600 МГц, определите среднюю цену ПК с такой же скоростью. Вывести: speed, средняя цена.**
```sql
select speed, AVG(price) AS avg_price from pc where speed > 600 group by speed
```

**Задание 23: Найдите производителей, которые производили бы как ПК
со скоростью не менее 750 МГц, так и ПК-блокноты со скоростью не менее 750 МГц. Вывести: Maker**

```sql
select distinct maker from product join pc on product.model = pc.model where speed >= 750 and maker in (select distinct maker from product join laptop on product.model = laptop.model where speed >= 750)
```





