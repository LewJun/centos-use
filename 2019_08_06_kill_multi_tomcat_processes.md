# kill多个tomcat进程
-bash-4.1# ps -ef|grep tomcat |grep -v grep |awk '{print $2}'
24578
24634
24693
24747
-bash-4.1# echo `ps -ef|grep tomcat |grep -v grep |awk '{print $2}'`
24578 24634 24693 24747
-bash-4.1# kill -9 24578 24634 24693 24747
