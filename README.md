# Hadoop
This repository consists of some basis commands of Hadoop distribution on Cloudera and codes to upload files to HDFS and analyze them by using wordcount and wordmedian.

1-Let's start with opening a new file on your HDFS:
**hdfs dfs -mkdir
*hdfs dfs -mkdir /examples** (I've just created a file named examples on our HDFS.)

2-Next step is to copy the file(s) to HDFS (Hadoop Distributed File System) to use Hadoop ecosystem. There are two ways to do this :
2.1 You can go to the directory which you want to copy to HDFS:
**hdfs dfs -copyFromLocal /the_name_of_your_file_to_copy**
**hdfs dfs -copyFromLocal alice.txt**
2.2 You can also copy your file without going to the directory or the address of your file below :
**hdfs dfs -copyFromLocal /source /destination**
**hdfs dfs -copyFromLocal /home/cloudera/Desktop/ratings.csv /examples**

