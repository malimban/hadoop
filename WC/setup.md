# Environment Setup

### Verify javac location
which javac
ls -la /usr/bin/javac
ls -la /etc/alternatives/javac

## Env export
export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
export PATH=${JAVA_HOME}/bin:${PATH}
export HADOOP_CLASSPATH=${JAVA_HOME}/lib/tools.jar

## Compilation

hadoop com.sun.tools.javac.Main WordCount.java
jar cf wc.jar WordCount*.class

## Input Loading

hadoop fs -mkdir /user/[username]/input
hadoop fs -put [input-files, input*.txt] /user/[username]/input (repeat this step as necessary)

Verify files loaded with
- hadoop fs -ls /user/[username]/input

## Running

hadoop jar wc.jar WordCount /user/[username]/input /user/[username]/output
 (note: output folder must not exist before running)

## Collecting Output

hadoop fs -get /user/[username]/output/* [destination]
