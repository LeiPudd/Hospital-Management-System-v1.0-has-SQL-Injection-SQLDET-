# Hospital-Management-System-v1.0-has-SQL-Injection-SQLDET-
Hospital Management  In PHP With Source Code has SQL Injection(sqldet).

Vul_Author: LeiPudd

vendors: https://itsourcecode.com/free-projects/php-project/hospital-management-system-in-php-with-source-code/

Vulnerability File: /HMS/patient.php

Vulnerability location: POST /hms/patient.php HTTP/1.1\r\n

[+] Payload: 

```sql
123456' AND EXTRACTVALUE(1, CONCAT('~', VERSION())) AND '
```

Tested on Windows 10, phpStudy

There is an example with sql Injection

When you enter the system, click 'LOG IN', and then choose 'Admin'

The login credentials are admin/123456789.

![image-20240928173224466](https://github.com/user-attachments/assets/c5d79258-854f-4a84-8c4d-28904d9735a4)

Then click on "Patients" in the left-hand list, and after that click on "Add Patient".

![image-20240928174043782](https://github.com/user-attachments/assets/a62f53d1-babb-4561-9797-a8891d16b496)

Then enter the corresponding information based on the type. In the "PIN code" field, input an SQL injection script，such as
```sql
123456' AND EXTRACTVALUE(1, CONCAT('~', VERSION())) AND '
```
The rest of the information can be fabricated. Click "submit" to retrieve the version of the MySQL server.

![4](https://github.com/user-attachments/assets/c21b126c-f9c6-4c5c-85bd-f2dd8a70ca83)

So, we can see that the version of the MySQL server is 8.0.12, which matches the version I tested locally.

![image-20240928174911605](https://github.com/user-attachments/assets/d2700d0b-ba0d-473b-9efb-6ae3d2fba407)
