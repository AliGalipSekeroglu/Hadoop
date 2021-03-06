# Hadoop
This repository consists of some basis commands of Hadoop distribution on Cloudera and codes to upload files to HDFS and analyze them by using *wordcount* and *wordmedian*.

1-Let's start with opening a new file on your HDFS:                                                                   
**hdfs dfs -mkdir**                       
**hdfs dfs -mkdir /examples** (I've just created a file named examples on our HDFS.)

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
**hdfs dfs -count /examples**                                                       
**hdfs dfs -count /var**                                                
**hdfs dfs -count /**                                                            
  
6-In order to see which files under a file, (text file for instance) use this command :                                 
**hdfs dfs -cat /examples/ratings.csv** (You will see what ratings.csv contains on terminal.)                           

7-You can delete any files from HDFS :                                                    
**hdfs dfs -rm /examples** (I've deleted examples files from HDFS.)                                     
    
8-You can move a file from somewhere to somewhere:                                          
**hdfs dfs -mv /var/ratings.csv /user**                                                   
  
9-You can give/retake(retrieve) permissions such as copying,deleting or more.+ means permissions that you give,- means permissions that you retrieve:                                                                                 
**hdfs dfs -chmod +x /user/ratings.csv                                                                
hdfs dfs -chmod -w /user/ratings.csv**             




                                        Commands to use WORDCOUNT and WORDMEAN

**[cloudera@quickstart ~]$ hadoop jar /usr/share/doc/hadoop-0.20-mapreduce/examples/hadoop-examples.jar wordcount**                 
Usage: wordcount <in> [<in>...] <out>                                             
**[cloudera@quickstart ~]$ hadoop jar /usr/share/doc/hadoop-0.20-mapreduce/examples/hadoop-examples.jar wordcount words.txt out**       
*"out" is the name of the file that HDFS will extract the results,you can change its name.*               

**[cloudera@quickstart ~]$ hdfs dfs -ls out**                                                                    
Found 2 items                                                                                                    
-rw-r--r--   1 cloudera cloudera          0 2018-10-15 09:59 out/_SUCCESS (*this shows your process is finished successfully.*)         
-rw-r--r--   1 cloudera cloudera     717768 2018-10-15 09:59 out/part-r-00000                                               

**[cloudera@quickstart ~]$ hdfs dfs -copyToLocal out/part-r-00000 results.txt**                                      
*I've copied the results to my local Cloudera system with the file name results.txt*       



**[cloudera@quickstart ~]$ hadoop jar /usr/share/doc/hadoop-0.20-mapreduce/examples/hadoop-examples.jar wordmedian**                  
**[cloudera@quickstart ~]$ hadoop jar /usr/share/doc/hadoop-0.20-mapreduce/examples/hadoop-examples.jar wordmedian words.txt out3**     
*(I've given a name "out3" as the file for result because I've already use "out" name has already exists. You can change the name.)*     
*You will get the result on Terminal,not in a different file,keep tracking the terminal for the result.*                   
