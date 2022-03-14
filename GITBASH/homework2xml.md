# HOMEWORK 2

## _Linux terminal (GitHub) commands_

| TASK | SOLUTION |
| ------ | ------ |
| 1. Создать внешний репозиторий c названием XML | GitHub -> Create New Repository XML |
| 2. Клонировать репозиторий XML на локальный компьютер | git clone https://github.com/sergnn/XML.git |
| 3. Внутри локального XML создать файл “new.xml” | cd XML && touch new.xml |
| 4. Добавить файл под гит | git add new.xml |
| 5. Закоммитить файл | git commit -m "newfile" |
| 6. Отправить файл на внешний GitHub репозиторий | git push |

***7. Отредактировать содержание файла “new.xml” - написать информацию о себе (ФИО, возраст, количество домашних животных, будущая желаемая зарплата). Всё написать в формате XML***
```sh
vim new.xml
    <?xml version="1.0"?>
     <INFO>
        <NAME>Nabokin Sergey</NAME>
        <AGE>6</AGE>
        <PETS>0</PETS>
        <SALARY>1000</SALARY>
    </INFO>
```

| TASK | SOLUTION |
| ------ | ------ |
| 8. Отправить изменения на внешний репозиторий | git commit -am "change xml" && git push |
| 9. Создать файл preferences.xml | touch preferences.xml |

***10. В файл preferences.xml добавить информацию о своих предпочтениях (Любимый фильм, любимый сериал, любимая еда, любимое время года, сторона которую хотели бы посетить) в формате XML***

```sh
vim preferences.xml
    <?xml version="1.0"?>
    <INFO>
        <FILM>Harry Potter</FILM>
        <SERIES>University</SERIES>
        <FOOD>Cheeseburger</FOOD>
        <SEASON>Summer</SEASON>
        <COUNTRY>USA</COUNTRY>
    </INFO>
```

***11. Создать файл sklls.xml добавить информацию о скиллах которые будут изучены на курсе в формате XML***

```sh
vim skills.txt
    <?xml version="1.0"?>
    <INFO>
        <SKILLS>The best skills</SKILLS>
    </INFO>
```

| TASK | SOLUTION |
| ------ | ------ |
| 12. Отправить сразу 2 файла на внешний репозиторий  | git add . && git commit -m "preferences and skill" && git push |
| 13. На веб интерфейсе создать файл bug_report.xml | GitHub -> add file -> create new file -> bug_report.xml |
| 14. Сделать Commit changes (сохранить) изменения на веб интефейсе | GitHub -> Commit changes |
| 15. На веб интерфейсе модифицировать файл bug_report.xml, добавить баг репорт в формате XML | GitHub -> bug_report.xml -> edit this file |

> **<?xml version="1.0"?>
    <INFO> 
        <SUMMARY>In CTR (Click through ratio) ‘Total’ row calculation is wrong</SUMMARY>
        <PRODUCT>Example product</PRODUCT>
        <VERSION>1.0</VERSION>
        <PLATFORM>PC</PLATFORM>
    <SYSTEM>Windows 2000</SYSTEM>
    <STATUS>NEW</STATUS>
    <SEVERITY>Major</SEVERITY>
    <PRIORITY>P1</PRIORITY>
    <COMPONENT>Publisher stats</COMPONENT>
    <STR>1</STR>
    <ER>wow</ER>
    </INFO>**

| TASK | SOLUTION |
| ------ | ------ |
| 16. Сделать Commit changes (сохранить) изменения на веб интерфейсе.  | GitHub -> commit changes |
| 17. Синхронизировать внешний и локальный репозиторий XML  | git pull |


