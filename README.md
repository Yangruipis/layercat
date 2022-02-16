# Layercat

cat your layeres in terminal.

## install

```bash
git clone https://github.com/Yangruipis/layercat.git && cd layercat

python setup.py install
```


## examples

### 1. TCP four layer

```bash
$ layercat --layers 'Application,Transport,Internet,Network Access' --desc '应用层(比如HTTP),传输层(比如TCP、UDF),网络层（IP协议）,数据链路层'
+--------------------+
|    Application     |--------> 应用层(比如HTTP)
+--------------------+
|     Transport      |--------> 传输层(比如TCP、UDP)
+--------------------+
|      Internet      |--------> 网络层（IP协议）
+--------------------+
|   Network Access   |--------> 数据链路层
+--------------------+
```

### 2. OSI seven layer


```bash
layercat --layers 'Application,Presentation,Session,Transport,Internet,Data Link,Physical' --desc '应用层,-,-,传输层,网络层,数据 链路 层,-'
+------------------+
|   Application    |----+
+------------------+    |
|   Presentation   |----+---> 应用层
+------------------+    |
|     Session      |----+
+------------------+
|    Transport     |--------> 传输层
+------------------+
|     Internet     |--------> 网络层
+------------------+
|    Data Link     |----+
+------------------+    |---> 数据链路层
|     Physical     |----+
+------------------+
```

### 3. Complicated cases


```bash
layercat --layers 'Application|Presentation|Session,Transport,Internet,Data Link,Physical' --desc '应用层,传输层,网络层,数据链路层,-'
+----------------------------------------------+
|   Application  |  Presentation  |  Session   |--------> 应用层
+----------------------------------------------+
|                  Transport                   |--------> 传输层
+----------------------------------------------+
|                   Internet                   |--------> 网络层
+----------------------------------------------+
|                  Data Link                   |----+
+----------------------------------------------+    |---> 数据链路层
|                   Physical                   |----+
+----------------------------------------------+
```

```bash
layercat --layers 'Application\nLayer|Presentation\nLayer|Session\nLayer\n(*),Transport,Internet,Data Link,Physical' --desc '应用层,传输层,网络层,数据链路层,-'
+------------------------------------------------------------------------+
|      Application      |      Presentation     |        Session         |
|         Layer         |         Layer         |         Layer          |
|                       |                       |          (*)           |--------> 应用层
+------------------------------------------------------------------------+
|                               Transport                                |--------> 传输层
+------------------------------------------------------------------------+
|                                Internet                                |--------> 网络层
+------------------------------------------------------------------------+
|                               Data Link                                |----+
+------------------------------------------------------------------------+    |---> 数据链路层
|                                Physical                                |----+
+------------------------------------------------------------------------+
```
