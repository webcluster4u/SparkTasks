# Spark Tasks
This aplication best run a a MapR platform (5.2) with Saprk 2.0. and MapRDB (HBase)
-First, copy sample files to HDFS. 
//go to root project at CSVLoader
$ Hadoop fs -put src/main/resources/*.csv /files

-For task 1, first run the CSV laoder, it simply load the CSV sample file to a HBase tale
/opt/mapr/spark/spark-2.0.1/bin/spark-submit --class "CSVLoader" --master local[2] target/scala-2.11/sparktasks_2.11-1.0.jar

-Second , run wordCounter which loads data from HBase, do wordcount and save data to a seprate HBase table
/opt/mapr/spark/spark-2.0.1/bin/spark-submit --class "WordCounter" --master local[2] target/scala-2.11/sparktasks_2.11-1.0.jar

For the second task run the application
/opt/mapr/spark/spark-2.0.1/bin/spark-submit --class "AirportHandler" --master local[2] target/scala-2.11/sparktasks_2.11-1.0.jar