# HOMEWORK 1
## _Linux terminal (Git Bash) commands_

| TASK | SOLUTION |
| ------ | ------ |
| Посмотреть где я | pwd |
| Cоздать папку | mkdir hw1 |
| Зайти в папку | cd hw1 |
| Создать 3 папки | mkdir hw2 hw3 hw4 |
| Зайти в любоую папку | cd hw2 |
| Создать 5 файлов (3 txt, 2 json) | touch file1.txt file2.txt file3.txt file4.json file5.json |
| Создать 3 папки | mkdir hw5 hw6 hw7 |
| Вывести список содержимого папки  | ls -la |
| + Открыть любой txt файл | vim file1.txt |
| + написать туда что-нибудь, любой текст. | {"name":"Serg"} |
| + сохранить и выйти. | esc :wq |
| Выйти из папки на уровень выше | cd .. |
| переместить любые 2 файла, которые вы создали, в любую другую папку. | mv file1.txt file2.txt hw6/ |
| скопировать любые 2 файла, которые вы создали, в любую другую папку. | cp file4.json file5.json hw6/ |
| Найти файл по имени | find . -name "file1.txt" |
| просмотреть содержимое в реальном времени (команда grep) изучите как она работает. | grep "" file1.txt |
| вывести несколько первых строк из текстового файла | head file1.txt -n 3 |
| вывести несколько последних строк из текстового файла | tail file1.txt -n 3 |
| просмотреть содержимое длинного файла (команда less) изучите как она работает. | less file1.txt |
| вывести дату и время   | date или date + "%A %d %B" (полное наименование дня/месяца) |

## _Задание *_
***Отправить http запрос на сервер http://162.55.220.72:5005/terminal-hw-request***
```sh
curl http://162.55.220.72:5005/terminal-hw-request
curl "http://162.55.220.72:5005/get_method?name=sergio&age=28"
```
## _Задание **_
***Написать скрипт который выполнит автоматически пункты 3, 4, 5, 6, 7, 8, 13***

```sh
vim firstscript
#!/bin/bash
cd hw1
mkdir hw2 hw3 hw4
cd hw2
touch file1.txt file2.txt file3.txt file4.json file5.json
mkdir hw5 hw6 hw7
ls -la
mv file1.txt file2.txt hw6/
esq: wq
./firstscript
```
