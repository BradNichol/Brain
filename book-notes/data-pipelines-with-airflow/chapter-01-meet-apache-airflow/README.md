# Chapter 1. Meet Apache Airflow

This chapter explores the concepts of data pipelines.

To handle the ever-increasing volumes of data, companies can use a variety of tools, including Airflow, a batch-orientated framework for building
data pipelines.

Airflow sits in the middle of data processors to coordinate work happening across different systems. Airflow does not process data itself, but
orchestrates the different tools involved in the processing.

## Introduction To Data Pipelines
A data pipeline typically consists of several tasks that execute in order, to move data from one representation/source
to another, and along the way combined with other data for a desired outcome.

### Pipelines As Graphs
To make dependencies between tasks more explicit, you can draw the pipeline as a graph, where individual tasks
are represented as nodes and dependencies between tasks are represented by directed edges.
This type of graph is known as a directed graph.

In regards to Airflow, this representation is known as a directed acyclic graph (DAG), as the tasks are directed
in a one-way order and do not contain any loops or cycles which prevent circular dependencies.

### Execution Algorithm
A DAG structure used a straightforward algorithm for execution:

1. For each uncompleted task:
   - check upstream task has completed
   - if true, add current task to execution queue
2. Execute tasks in queue, marking complete
3. Go back to step one and repeat for all tasks in the DAG.




