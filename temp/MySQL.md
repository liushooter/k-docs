
utf8_bin将字符串中的每一个字符用二进制数据存储，区分大小写。

utf8_genera_ci不区分大小写，ci为case insensitive的缩写，即大小写不敏感。

utf8_general_cs区分大小写，cs为case sensitive的缩写，即大小写敏感。


[mysql-case-sensitive-query](http://stackoverflow.com/questions/7857669/mysql-case-sensitive-query)

```
select * from users where BINARY user_name = 'cgrant' limit 8;

```
***

[Mysql2::Error: Incorrect string value](http://stackoverflow.com/questions/22464011/mysql2error-incorrect-string-value)

```ALTER DATABASE knewcoin_production  CHARACTER SET utf8 COLLATE utf8_general_ci;```

```ALTER TABLE your_database_name.your_table CONVERT TO CHARACTER SET utf8```