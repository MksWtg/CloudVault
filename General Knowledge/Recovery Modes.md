In sql sever, every data changing query starts a transaction even if you dont explicitly write one

E.g.

`UPDATE Users SET Name = 'Alice' WHERE Id = 1;`

becomes

```SQL
BEGIN TRANSACTION;
UPDATE Users SET Name = 'Alice' WHERE Id = 1;
COMMIT;
```

So 