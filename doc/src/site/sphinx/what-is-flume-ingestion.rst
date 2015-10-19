FLUME-INGESTION
***************

Flume Ingestion is a fork of Apache Flume (1.6), where you can find:

**Several bug fixes**

-  Some of them really important, such as unicode support

**Several enhancements of Flume’s sources & sinks**

-  ElasticSearch mapper, for example

**Custom sources and sinks, developed by Stratio**

-  SNMP (v1, v2c and 3)
-  redis, Kafka (0.8.1.1)
-  MongoDB, Druid, JDBC and Cassandra
-  Stratio Streaming (Complex Event Processing engine)
-  REST client, Flume agents stats

Flume Ingestion components
==========================

-  Data transporter and collector: `Apache Flume`_
-  Data extractor and transformer: `Morphlines`_
-  Custom sources to read data from:

   -  REST
   -  FlumeStats
   -  SNMPTraps
   -  IRC

-  Custom sinks to write the data to:

   -  Cassandra
   -  MongoDB
   -  Druid
   -  `Stratio Streaming`_
   -  JDBC
   -  Kafka

What is Apache Flume?
=====================

Apache Flume is a distributed, reliable, and available system for
efficiently collecting, aggregating and moving large amounts of log data
from many different sources to a centralized data store.

Its use is not only designed for logs, in fact you can find a myriad of
sources, sinks and transformations.

In addition, a sink could be a big data storage but also another
real-time system (Apache Kafka, Spark Streaming).

Interesting facts about Flume-Ingestion
=======================================

-  Flume Ingestion is Apache Flume “on steroids” :)

-  We are extensively using Kite SDK (morphlines) in order to do a
   better T from ETL, and so we have also developed a bunch of custom
   transformations.

-  Stratio ingestion is fully open source and we work very close to the Flume community.

Ingestion Architecture
======================

Each agent consists of three major components:

-   Sources are active components that receive data for some other application producing that data.

-   Channels are passive components that buffer data received by the agent, behaving like queues.

-   Sinks poll their respective channels continuously to read and remove events.

 .. image:: images/ingestion_architecture.jpg
    :width: 70%
    :align: center


Flume Ingestion FAQ
===================

**Can I use Flume Ingestion for aggregating data (time-based rollups,
for example)?**

*This is not a good idea from our experience, we use to combine Flume +
Spark Streaming in order to do that (custom development)*

**Is Flume Ingestion multipersistence?**

*Yes, you can write data to JDBC sources, mongoDB, Apache Cassandra,
ElasticSearch, Apache Kafka, among others.*

**Can I send data to streaming-cep-engine?**

*Of course, we have developed a sink in order to send events from Flume
to an existing stream in our CEP engine. The sink will create the stream
if it does not exist in the engine.*

.. _Apache Flume: http://flume.apache.org/
.. _Morphlines: http://kitesdk.org/docs/current/kite-morphlines/index.html
.. _Stratio Streaming: https://github.com/Stratio/stratio-streaming



Release Notes
=============

The project is actively developed and repository is available on Github. You can get the last version and release
notes from the `project page on Github <https://github.com/Stratio/Ingestion/releases>`_.

Where to go from here
=====================

To explore and play with Stratio Ingestion, we recommend to visit the following:

-   :ref:`wikipedia-pagecounts-demo`: Execute one of the existing demos to understand better how to use Ingestion
agent
-   :ref:`configuration`: Check some configuration details to understand how to setup your first Ingestion agent