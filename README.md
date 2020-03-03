# tweetscanner

Bike Share Batch Analytics

1. Project Background:
Local Governments are now on a quest of improving quality of life of its cities and towns by making them smarter. This quest towards smarter cities, involves creating a better sustainable urban environment for its citizens. The Bike Share Program was proposed to help cities become smarter, it would help relief traffic congestions, reduce air pollution in the city as well as having the side benefit of promoting a healthier lifestyle. The Bike Share program has been largely successfully in its objective as 500,000 bicycles are now available all around the world for people to use in over 500 different bike share programs.
In this report we will analyse one of these bike Share programs. Specifically, the dataset collected from a Bike share program in Washington DC, USA will be analysed. The dataset has 1000 records of rental data of bikes between the years of 2011-2013. The aim of this analysis is to understand the most popular rental season across the year.
2. Middleware Configuration:
The configuration that has been selected for this report is the Hadoop standalone configuration. This configuration runs on a single node on the local machine. It is typically used for developing and debugging. Hadoop runs on completely on the local machine and does not use any Hadoop daemons, because of this it uses the local file system instead of HDFS. Hadoop Standalone is setup as soon as you have properly installed Hadoop. It is configured by leaving the configuration block of code in the xml documents empty.
The reason Hadoop standalone has been picked over Pseudo Distributed for this report is because of simplicity. In this report we are dealing with a small amount of data, it’s is better to use the local file system for such small data rather than HDFS. This is because the power of HDFS and Hadoop daemons would not be used to its full potential. It would be faster to use the local file system to process a small amount of data than the HDFS because the HDFS has to put the data in to the Hadoop File System before processing.
3. Data Analytics Design:
The Bike Share data has data entries that will show the success of the Bike Share in various locations around the US. In order to calculate where the Bike Share program is having the most success, we would have to implement a Map Reduce Framework. Map Reduce is a program that splits huge amounts of data into smaller more easily processed chunks. Programs are executed in two major phases. The mapping phase and the reducing phase. However, before Mapping the splitting phase is implemented and before the reducing phase the Shuffling phase is also implemented. In the Mapping phase, the input data is fed into the mapper. In the reducing phase, all the outputs from the mapper is processed by the reduced and is set as the final result. The input in Map reduce programs are set as a list key Value pairs, the list is the broken up and each individual key value pair (K1, V1) is process by the mapper. The output of the mapper then aggregates into a larger (K2, V2) pairs. All the Keys that are the same are now paired into a new list of (K2, List(V2)) pairs. The reducer then processes each of the new key value pairs and aggregates their value into a new (K3, V3) pair. This new set of pairs is then written to file. See Fig.1.
 
This map Reduce program could be used with any input file. For example, say you wanted to count the amount of times people have used the word “Brexit” in a data set gotten from a United Kingdom subreddit on the online social forum reddit. Provided the proper data is acquired MapReduce could find the number of times Brexit has been said in terabytes worth of data and more.
 MapReduce Diagram of BikeShare Data fig.1
 4. Results:

 Image of Results Fig.2
 5. Discussion of Results:
As can be seen from the result above, the most popular season for biking is the Fall. The fall has about 329. That means Bike sharers in Washington Dc are about 32.22 percent more likely to bike in the summer than any other season. This data is sensible due to the fact that fall seasons in Washington DC has less rain and are warmer than Spring and Winter Respectively. The fall season is also cooler than the Summer, hence the perfect weather for biking as the data proves. See fig 3. And fig 4

 Annual Temperature in Washington DC Fig.3
  Annual Rainfall in Washington DC Fig.4
6. Conclusions and Recommendations:
In conclusion, the bike share program is most popular during warmer and drier seasons, especially during the fall. This data is very limited however, only containing a thousand data entries in a year. A thousand data entries could easily be supported by the current map reduce program. Map Reduce is a framework designed to be scalable. It can work 10 times the amount of time and far more than 1 terabyte of data. However, this cannot be run easily on Hadoop standalone, the configuration of the project would have to be modified and changed into Hadoop fully Distributed. With Hadoop fully distributed, the map reduce program can run each mapper and reducer on a different node, this would tremendously increase the scalability of the map reduce program.
