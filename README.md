# Welcome to WebGraph!


[WebGraph](http://webgraph.di.unimi.it/) is a framework for graph
compression aimed at studying web graphs. It provides simple ways to
manage very large graphs, exploiting modern compression techniques.

This version of WebGraph is limited to graphs with at most 2^31 nodes. For
larger graphs, have a look at the [big
version](https://github.com/vigna/webgraph-big).

# Setup on Ubuntu
<!-- You need [Ant](https://ant.apache.org/) and [Ivy](https://ant.apache.org/ivy/). -->
Requirements:
* openjdk-21
* [Ant](https://ant.apache.org/)
* [Ivy](https://ant.apache.org/ivy/)

<!-- Required packages `openjdk-21-jre ant` both can be installed by -->
Install Java 21 and Ant 
```
sudo apt update && sudo apt install openjdk-21-jre-headless ant 
```
Verify that java and ant were installed correctly:
```
java --version
``` 

```
ant -version
```
If ant was not installed re-try by running:
```
sudo apt install ant
```

In order to install ivy, we must download first the jar file and then copy it to the path where ant is installed

```
wget -O ant-ivy https://dlcdn.apache.org//ant/ivy/2.5.2/apache-ivy-2.5.2-bin.tar.gz
tar -xf ant-ivy
```
This should create a directory named `apache-ivy-2.5.2`

Copy the `apache-ivy-2.5.2/ivy-2.5.2.jar` file into `/usr/share/ant/lib/`


# Building 



Build the `jar` by first `cd` into the `webgraph` repo and run:  
```
ant ivy-setupjars jar
```
Set the `CLASSPATH` by 
```
source setcp.sh
```
Finally to test that everything works you can try the following command:
```
java it.unimi.dsi.webgraph.BVGraph -g ArcListASCIIGraph example.arcs bvexample
```

seba (<mailto:sebastiano.vigna@unimi.it>)
