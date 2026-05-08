A clustered index sorts and stores the table rows physically based on the indexed column.

Without:
```
Random storage:
104
2
87
15
```

With:
```
Physically ordered:
2
15
87
104
```

Use it for PKs

A nonclustered index is a separate structure that stores:

- Indexed column values
- Pointers to the actual rows

E.g. for a table like:
```
EmployeeID | LastName
1          | Smith
2          | Jones
3          | Brown
```

The index will look like:

```
Brown -> Row 3
Jones -> Row 2
Smith -> Row 1
```

There can only be one clustered index (one way of physically storing the real data) but multiple unclustered indexes (extra data).

