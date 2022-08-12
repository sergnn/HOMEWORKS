[![N|Solid](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTvkBQDBJAXIiKtCBSk-iMt0-hNcWsnVhrslb_zYrxp8vmmMENEoa71G6FBWOgl-M7FLw&usqp=CAU)](http://testingchallenges.thetestingmap.org/index.php)

# Web testing. Challenge 1

***What to do***
Identify all the test required for the scenario below. Based on the data you input in the First Name field the tests will be evaluated.
***What not to test for***
Different browsers, extremely big requests, "nasty words", browser zoom in and out. Do not use automation tools. The server will cut access at over 30 requests per second per IP.
***Specification***
The user has to fill in the required data in order to get access, as a standard user in a forum.
Only the First Name field can be tested right now. The field has a max length of 30.

##### 1. Other chars then alphabetic
```
First Name: 0
```

##### 2. Minimum value
```
First Name: 0
```

##### 3. Empty value
```
First Name: 
```

##### 4. Average value
```
First Name: serg
```

##### 5. Space
```
First Name: 
```

##### 6. Space values at the beginning
```
First Name:  serg
```

##### 7. Space in the middle
```
First Name:  se rg
```

##### 8. Space values at the end
```
First Name: serg  
```

##### 9. Non ASCII
```
First Name: серг
```

##### 10. Maximum values
```
First Name: sergnsergnsergnsergnsergnsergn
```

##### 11. More than maximum values
```
First Name: sergnsergnsergnsergnsergnsergnnnnn
```

##### 12. Basic Sql injection
```
First Name: 'sql injection'
```

##### 13. You used html tags
```
First Name: <b>serg</b>
```

##### 14. You made the user admin
```
Открыть консоль разработчика, найти в elements по строке ввода права админа, поменять на 1. Нажать submit
<input type="hidden" name="user_right_as_admin" value="1">
```

##### 15. You looked at the page source
```
Открыть консоль разработчика, вкладка sources, файл index.php, пролистать вниз: 
<!--add this value in the First Name to validate that you have looked at the page source : dfjwGGe82H43g3uRiy53h--></html>
First Name: dfjwGGe82H43g3uRiy53h
```

##### 16. Missing css
```
Открыть консоль разработчика, вкладка sources, пустой файл detailsoverviewnow.css 
First Name: detailsoverviewnow.css
```

##### 17. You looked at the cookie
```
Открыть консоль разработчика, вкладка application, cookies, testing challenge:
You_have_checked_the_cookie_content._Add_oi32jnxd42390slk345_in_the_First_Name_field_to_mark_this_case.
First Name: oi32jnxd42390slk345
```

##### 18. Basic XSS
```
First Name: <script>alert('xss');
```















