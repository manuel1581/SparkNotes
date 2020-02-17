# Data Skew

This happens when we have partitions with more data to process than others. We want an equally distributed amount of data in every
partition in order to parallelize our workloads.

Joins are made by join key, i.e., data from the two tables being joined will be in the same task.
If you have many rows with the same key, then the tasks related to that key will take much longer.[1]

Partitions size shouldn´t be larger than 200MB<br>
For example:
* Your dataset: 10GB x 1024 = 10240
* 10240 / 200 ~= 52 partitions


References: 
[1] https://www.davidmcginnis.net/post/spark-job-optimization-dealing-with-data-skew <br>
[2] https://kontext.tech/column/spark/296/data-partitioning-in-spark-pyspark-in-depth-walkthrough<br>
[3] https://towardsdatascience.com/the-art-of-joining-in-spark-dcbd33d693c<br>
[4] https://unraveldata.com/common-failures-slowdowns-part-ii/<br>
[5] https://stackoverflow.com/questions/40373577/skewed-dataset-join-in-spark<br>
[6] https://datarus.wordpress.com/2015/05/04/fighting-the-skew-in-spark/<br>
[7] https://forums.databricks.com/questions/10266/how-to-decide-on-the-number-of-partitions-while-re.html<br>
