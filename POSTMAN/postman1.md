# POSTMAN
## _HOMEWORK 1, GET & POST_

- Protocol: http
- IP: 162.55.220.72
- Port: 5005

##### **REQUEST №1** 
Method: GET
EndPoint: /get_method
request url params: 
 name: sergio
 age: 28
##### **RESPONSE №1**
```sh
[
    "sergio",
    "28"
]
```

##### **REQUEST №2** 
Method: POST
EndPoint: /user_info_3
request form data: 
 name: sergio
 age: 28
 salary: 1000
 ##### **RESPONSE №2**
 ```sh
{
    "age": "28",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "u_salary_1_5_year": 4000
    },
    "name": "sergio",
    "salary": 1000
}
```

##### **REQUEST №3** 
Method: GET
EndPoint: /object_info_1
request url params: 
 name: sergio
 age: 28
 weight: 75
##### **RESPONSE №3**
 ```sh
{
    "age": 28,
    "daily_food": 0.9,
    "daily_sleep": 187.5,
    "name": "sergio"
}
```

##### **REQUEST №4**
Method: GET
EndPoint: /object_info_2
request url params: 
 name: sergio
 age: 28
 salary: 1000
##### **RESPONSE №4**
 ```sh
{
    "person": {
        "u_age": 28,
        "u_name": [
            "sergio",
            1000,
            28
        ],
        "u_salary_5_years": 4200.0
    },
    "qa_salary_after_1.5_year": 3300.0,
    "qa_salary_after_12_months": 2700.0,
    "qa_salary_after_3.5_years": 3800.0,
    "qa_salary_after_6_months": 2000,
    "start_qa_salary": 1000
}
```
##### **REQUEST №5**
Method: GET
EndPoint: /object_info_3
request url params: 
 name: sergio
 age: 28
 salary: 1000
##### **RESPONSE №5**
 ```sh
{
    "age": "28",
    "family": {
        "children": [
            [
                "Alex",
                24
            ],
            [
                "Kate",
                12
            ]
        ],
        "pets": {
            "cat": {
                "age": 3,
                "name": "Sunny"
            },
            "dog": {
                "age": 4,
                "name": "Luky"
            }
        },
        "u_salary_1_5_year": 4000
    },
    "name": "sergio",
    "salary": 1000
}
```

##### **REQUEST №6**
Method: GET
EndPoint: /object_info_4
request url params: 
 name: sergio
 age: 28
 salary: 1000
##### **RESPONSE №6**
 ```sh
{
    "age": 28,
    "name": "sergio",
    "salary": [
        1000,
        "2000",
        "3000"
    ]
}
```

##### **REQUEST №7**
Method: POST
EndPoint: /user_info_2
request form data: 
 name: sergio
 age: 28
 salary: 1000
 
##### **RESPONSE №7**
 ```sh
{
    "person": {
        "u_age": 28,
        "u_name": [
            "sergio",
            1000,
            28
        ],
        "u_salary_5_years": 4200.0
    },
    "qa_salary_after_1.5_year": 3300.0,
    "qa_salary_after_12_months": 2700.0,
    "qa_salary_after_3.5_years": 3800.0,
    "qa_salary_after_6_months": 2000,
    "start_qa_salary": 1000
}
```














