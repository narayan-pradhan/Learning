## Bash Tips and Trics with sample code

#### how to get exit status of command run using pipe in bash shell
```sh
ls -ltr ~/ | tee /tmp/test.log ; ( exit ${PIPESTATUS[0]} )
exit_stat=$?
name=$(whoami)
echo "Exit Status :  $exit_stat"
```
