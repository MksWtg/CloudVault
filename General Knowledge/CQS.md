Command query separation is a principle of imperative software design. It says that every function/method should either be a command or a query, but never both.

Command: a function that does something, has some effect, e.g. write to console, create new security group in AD

Query: return some data, e.g. read from DB, `int square(int x)`, etc.

A method should not both have an effect and return a result.
