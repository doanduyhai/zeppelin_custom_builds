# What is this ?
This project provides custom builds of **[Apache Zeppelin]** for **[Apache Spark]**, **[Apache Cassandra]** (or **[DSE]** )and **[Apache Zeppelin]** integration.

> **WARNING: all the binaries in this repository have been built using Scala 2.10. If you need a Scala 2.11 build, please contact me**


# Zeppelin custom build version matrix

All the zeppelin custom builds are located in the shared Google folder **[here]**.

The custom Maven pom file (`spark-dependencies-pon.xml`) used for building those versions is provided as a reference

<table>
  <thead>
    <tr>
      <th>Zeppelin version</th>
      <th>Spark version/DSE version</th>
      <th>Spark-Cassandra connector version</th>
      <th>Tarball</th>    
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0.6.0</td>
      <td>1.4.0</td>
      <td>1.4.4</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.4.0.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>1.4.1</td>
      <td>1.4.4</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.4.1.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>1.5.0</td>
      <td>1.5.1</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.5.0.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>1.5.1</td>
      <td>1.5.1</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.5.1.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>1.5.2</td>
      <td>1.5.1</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.5.2.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>1.6.0</td>
      <td>1.6.0</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.6.0.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>1.6.1</td>
      <td>1.6.0</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.6.1.tar.gz</td>
    </tr>                    
    <tr>
      <td>0.6.0</td>
      <td>1.6.2</td>
      <td>1.6.0</td>
      <td>zeppelin-0.6.0-cassandra-spark-1.6.2.tar.gz</td>
    </tr>    
    <tr>
      <td>0.6.0</td>
      <td>DSE 4.8.3, DSE 4.8.4 (Spark 1.4.1)</td>
      <td>1.4.1</td>
      <td>zeppelin-0.6.0-dse-4.8.3-4.8.4.tar.gz</td>
    </tr>    
    <tr>
      <td>0.6.0</td>
      <td>DSE 4.8.5, DSE 4.8.6 (Spark 1.4.1)</td>
      <td>1.4.2</td>
      <td>zeppelin-0.6.0-dse-4.8.5-4.8.6.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>DSE 4.8.7 (Spark 1.4.1)</td>
      <td>1.4.3</td>
      <td>zeppelin-0.6.0-dse-4.8.7.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>DSE 4.8.8, DSE 4.8.9 (Spark 1.4.1)</td>
      <td>1.4.4</td>
      <td>zeppelin-0.6.0-dse-4.8.8-4.8.9.tar.gz</td>
    </tr>
    <tr>
      <td>0.6.0</td>
      <td>DSE 5.0.0, DSE 5.0.1 (Spark 1.6.1)</td>
      <td>1.6.0</td>
      <td>zeppelin-0.6.0-dse-5.0.0-5.0.1.tar.gz</td>
    </tr>
  </tbody> 
</table>

> Please note that for **[DSE] 5.0.0** and **[DSE] 5.0.1**, you need to start the analytics mode with **`dse -x 2 cassandra -k`** to use **Hadoop2** mode otherwise the custom build, which has built with **Spark 1.6.x** will not work

# Spark-Cassandra connector assembly

If you are using open source **[Apache Cassandra]** you'll need to have the Spark-Cassandra connector and **all its transitive dependencies** in your Spark classpath.

For this, there are 2 solutions:

* either put `export SPARK_SUBMIT_OPTIONS = "--package com.datastax.spark:spark-cassandra-connector_<scala_version>:<connector_version>"` in the `$ZEPPELIN_HOME/conf/zeppelin-env.sh` file
* or download the appropriate **assembly** jar in the folder **`spark-cassandra-connector-assembly`** and add it to the Spark classpath (`export SPARK_CLASSPATH=<path_to_the_assembly_jar>` in the `$SPARK_HOME/conf/spark-env.sh` file)


[here]: https://drive.google.com/folderview?id=0B6wR2aj4Cb6wQ01aR3ItR0xUNms
[DSE]: http://docs.datastax.com/en/latest-dse/index.html      
[Apache Cassandra]: http://cassandra.apache.org
[Apache Spark]: http://spark.apache.org
[Apache Zeppelin]: http://zeppelin.apache.org