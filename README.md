#HOW TO RUN ON DOCKER

1. Create a directory for the tweet file 
` hdfs dfs -mkdir /user/root/data`
2. Put the file into created directory name. Insert folder name inside {foldername}
`hdfs dfs -put "/mnt/{foldername}/tweets2009-06.txt" /user/root/data`
3. Compile java file (for question 2 just use TweetAnalysis2.java and so on )
`hadoop com.sun.tools.javac.Main TweetAnalysis1.java`
4. Make a jar file
`jar cf TweetAnalysis1.jar TweetAnalysis1*.class`
5. Run the hadoop map reduce job
`hadoop jar TweetAnalysis1.jar TweetAnalysis1 /user/root/data /user/root/output`
(note that the output file needs to change name evertime you run this command so /user root/output1 /user/root/output2 etc..)
6. View the output 
`hadoop fs -cat /user/root/output/part-r-00000`
