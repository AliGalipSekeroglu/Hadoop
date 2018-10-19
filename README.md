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

5-You can see how many files under a file or on your HDFS by using commands below:
**hdfs dfs -count /examples
hdfs dfs -count /var
hdfs dfs -count / **
