Database Authentication
=======================

## Access the database with minimal privilege



If your Go web application only needs to read data and doesn't need to write
information, create a database user whose permissions are `read`. 
Always adjust the database user according to your web applications needs.

### MongoDB

MongoDB uses role based access control (RBAC) to authorize database users.

MongoDB provides a set of [built-in roles](https://docs.mongodb.com/manual/reference/built-in-roles/#built-in-roles)
which contain common levels of accesses. You can use these roles, or create 
[User-Defined roles](https://docs.mongodb.com/manual/core/security-user-defined-roles/), to ensure the absolute
minimum privilege level for your applications users.

MongoDB allows users to be scoped to databases and even 
[collections](https://docs.mongodb.com/manual/core/collection-level-access-control) for further granularity in database
user access control.


## Use a strong password

When creating your database access, choose a strong password. You can use
password managers to generate a strong password.


### MongoDB

MongoDB supports using [X.509 Certificates to authenticate clients](https://docs.mongodb.com/manual/tutorial/configure-x509-client-authentication/). 
This can provide a more secure manner of authentication when comparted to username/password combinations.



## Remove default admin passwords

Most DBS have default accounts and most of them have no passwords on their
highest privilege user.

For example, MariaDB, and MongoDB use `root` with no password,

Which means that if there is no password, the attacker could gain access to
everything.

Also, don't forget to remove your credentials and/or private key(s) if you're
going to post your code on a publicly accessible repository in Github.

[1]: https://strongpasswordgenerator.com/
