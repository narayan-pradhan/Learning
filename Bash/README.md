## Bash Tips and Trics with sample code

#### how to get exit status of command run using pipe in bash shell
```sh
ls -ltr ~/ | tee /tmp/test.log ; ( exit ${PIPESTATUS[0]} )
exit_stat=$?
name=$(whoami)
echo "Exit Status :  $exit_stat"
```
#### Calling perl script from Shell script
```sh
export EXIT_STAT=$?
export USERID=$(whoami)
export SCRIPT=$0
export DOBVALIDATE_PARAM=$@

perl <<'EOF'
    use lib "/sdev/devbench/sdev/user/lib/site_asml/";
    use lib "/sdev/lib/";
    use MqttSplunkLogger;
    my $mqttlog = $VERBOSE?new MqttSplunkLogger(MqttSplunkLogger::DEBUG):new MqttSplunkLogger();
    $mqttlog->setData('mqtt_channel', 'euv_actions');
    $mqttlog->setData('arguments' , $ENV{DOBVALIDATE_PARAM});
    $mqttlog->setData('action' , $ENV{SCRIPT});
    $mqttlog->setData('exit_status' ,$ENV{EXIT_STAT});
    $mqttlog->setData('user' , $ENV{USERID});
    $mqttlog->publish();
EOF
```
