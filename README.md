Coms Manager
============
H1. prerequisites
	1. Putty
	2. Java-8
	
Kafka Steps. 
	1. Open putty and connect 10.150.18.210
	2. credential root/sapient@123
	3. Go to : /usr/hdp/2.3.6.0-3796/kafka
	4. open producer by using below command
		bin/kafka-console-producer.sh --broker-list bangvmplnode1.sapient.com:6667 --topic ProcessedUserTransactions
	5. input message in below format once * Notification Steps * are done (check below)
		{"CardNumber" : "00001","TrnDate" : "11/1/2015","FirstName" : "Shailendra","LastName" : "Shail","Email" : "sshail@sapient.com","Mobile" : "9000000001","Merchant" : "M1","Amount" : 50,"NetAmount" : 150}
		
Notification Steps:
	1. Clone code
		git clone http://gerrit.sandbox.extranet.group/pas-coms-mgr 
	2. set JAVA_HOME to jdk 1.7 or later
	3. goto pas-coms-mgr directory and build
		mvn install
	3. goto target directory and run comsMgr
		java -jar ComsMgr-1.0-SNAPSHOT-jar-with-dependencies.jar>out.log
		or
		./ComsMgr>out.log (only applicable for bash)
	4. follow * kafka step 5 *
	5. Check your mailBox
	
Ambari console 
	http://10.150.18.211:8080/
	admin/admin
	
enjoy :)