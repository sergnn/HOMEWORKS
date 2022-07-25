# HOMEWORK 2

## _Linux terminal (GitHub) commands_

| TASK | SOLUTION |
| ------ | ------ |
| 1. Создать внешний репозиторий c названием JSON | GitHub -> Create New Repository JSON |
| 2. Клонировать репозиторий JSON на локальный компьютер | git clone https://github.com/sergnn/JSON.git |
| 3. Внутри локального JSON создать файл “new.json” | cd JSON && touch new.json |
| 4. Добавить файл под гит | git add new.json |
| 5. Закоммитить файл | git commit -m "newfile" |
| 6. Отправить файл на внешний GitHub репозиторий | git push |

***7. Отредактировать содержание файла “new.json” - написать информацию о себе (ФИО, возраст, количество домашних животных, будущая желаемая зарплата). Всё написать в формате JSON***
```sh
vim new.json
{
    "name" : "Nabokin Sergey",
    "age" : 28,
    "pets" : 0,
    "future salary" : 1000
}
```

| TASK | SOLUTION |
| ------ | ------ |
| 8. Отправить изменения на внешний репозиторий | git commit -am "change json" && git push |
| 9. Создать файл preferences.json | touch preferences.json |

***10. В файл preferences.json добавить информацию о своих предпочтениях (Любимый фильм, любимый сериал, любимая еда, любимое время года, сторона которую хотели бы посетить) в формате JSON***

```sh
{
    "Film" : "Harry Potter",
    "TV series" : "University",
    "Food" : "dumplings",
    "Season" : "summer",
    "Country" : "USA"
}
```

***11. Создать файл sklls.json добавить информацию о скиллах которые будут изучены на курсе в формате JSON***

```sh
vim skills.json
{
    "Skills" : "Hard and soft skills"
}
```

| TASK | SOLUTION |
| ------ | ------ |
| 12. Отправить сразу 2 файла на внешний репозиторий  | git add . && git commit -m "preferences and skill" && git push |
| 13. На веб интерфейсе создать файл bug_report.json | GitHub -> add file -> create new file -> bug_report.json |
| 14. Сделать Commit changes (сохранить) изменения на веб интефейсе | GitHub -> Commit changes |
| 15. На веб интерфейсе модифицировать файл bug_report.json, добавить баг репорт в формате JSON | GitHub -> bug_report.json -> edit this file |

> **{ 
        "Summary" : "In CTR (Click through ratio) ‘Total’ row calculation is wrong",
        "Product" : "Example product",
"Version" : 1.0,
         "Platform" : "PC",
          "Version" : "Windows 2000",
          "Status" : "NEW",
         "Severity" : "Major",
         "Priority" : "P1",
         "Component" : "Publisher stats",
        "Steps to reproduce" : 1,
          "Expected result" : "wow"
         }**

| TASK | SOLUTION |
| ------ | ------ |
| 16. Сделать Commit changes (сохранить) изменения на веб интерфейсе.  | GitHub -> commit changes |
| 17. Синхронизировать внешний и локальный репозиторий JSON  | git pull |


