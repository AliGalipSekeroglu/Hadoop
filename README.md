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

3-You can also copy your files back to your own Cloudera distribution which you've already copied to HDFS:

**hdfs dfs -copyToLocal words2.txt**

4-You can re-copy your files on HDFS. (The file which you're going to copy must be already copied into HDFS before.)

**hdfs dfs -cp words.txt words2.txt** (I copied words.txt as words2.txt one more time.)
**hdfs dfs -cp /source /destination**
**hdfs dfs -cp /examples/ratings.csv /var** (I copied ratings.csv file from examples to var file under HDFS.)

5-You can see how many files under a file or on your HDFS by using commands below:

**hdfs dfs -count /examples
hdfs dfs -count /var
hdfs dfs -count / **

6-In order to see which files under a file, (text file for instance) use this command :

**hdfs dfs -cat /examples/ratings.csv** (You will see what ratings.csv contains on terminal.)

7-You can delete any files from HDFS :

**hdfs dfs -rm /examples** (I've deleted examples files from HDFS.)

8-You can move a file from somewhere to somewhere:

**hdfs dfs -mv /var/ratings.csv /user**

9-You can give/retake(retrieve) permissions such as copying,deleting or more.+ means permissions that you give,- means permissions that you retrieve:

**hdfs dfs -chmod +x /user/ratings.csv
hdfs dfs -chmod -w /user/ratings.csv**
