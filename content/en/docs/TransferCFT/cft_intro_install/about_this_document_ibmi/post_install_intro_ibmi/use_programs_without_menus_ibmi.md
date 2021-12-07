{
    "title": "How to use programs without menus",
    "linkTitle": "How to use programs without menus",
    "weight": "210"
}This section describes ho to use programs such as CFTUTIL, CFTINIT, CFTMI, etc. For example, to migrate Transfer CFT you cannot use the standard Transfer CFT IBM i menus and require the following steps.

1.  Enter: `CALL `and press **F4.**
2.  In the **Program** field, enter the name of binary (`CFTUTIL `in the example).
3.  In the **Library** field, enter your program library (`*LIBL`by default, `CFTPROD ` in the example).
4.  In the **Parameters** field you can enter an argument.  CFTUTIL requires at least one argument (`CFTEXT `in the example).

 
