# Scheduling with Inter-layer Optimization in Spark

**Abstract**

We explore the job scheduling policies of Spark and implement a new self-designed one. In the evaluation section, we analyze each scheduling policy and compare the differences between them.

**Introduction**

As data volumes that requiring processing grow dra- matically, researchers have come up with different big data frameworks to provide efficient data processing solutions, including Hadoop, Dryad and MapReduce.

Among big data systems, Spark is a distributed processing program widely used in both industry and research environments. A Spark cluster runs user-submitted programs as jobs; each user job is further broken down into tasks. The tasks are submitted to a single cluster-wide TaskManager that is responsible for allocating these tasks to JVM execution units (executors).

One main theme of big data system optimization focuses on scheduling algorithms. Intuitively, a good scheduling algorithm focused on productivity will ensure a high usage rate of the CPU. Many previous works try to achieve this, such as the decentralized solution Sparrow, and Google’s Borg system.

There are two main scheduling schemes within Spark on the task level - FIFO and FAIR. FIFO is straightforward in that the task that is submitted first will be run first. On the other hand, FAIR will keep switching between tasks to achieve fair resource allocations. However, in our view, both scheduling schemes are somewhat myopic in that neither utilizes enough information from the task itself. Therefore, our work considers different attributes of the tasks and provides a harmonic scheduling solution that aims to achieve a balance between the default FIFO and FAIR scheduling schemes in Spark.

Slides: https://docs.google.com/presentation/d/1d5rue509T-yS69s47fzm_kdjGrngs6fpwXaBm4r35V8/edit#slide=id.p