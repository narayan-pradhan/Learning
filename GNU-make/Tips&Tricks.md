# Tips and Tricks 
shows all variables, useful for large projects with multiple makefiles.
Add at top of the makefile
```
$(foreach v, $(.VARIABLES), $(info $(v) = $($(v))))
```
