## How Does Spark’s Lazy Evaluation Work?

### Transformations are Lazy:

Transformations like map(), filter(), select(), etc., don’t immediately compute results. Instead, they build up a logical plan for how the data should be processed. This logical plan is represented internally as a Directed Acyclic Graph (DAG).
These transformations are "recorded" but not executed until an action is called.

### Actions Trigger Execution:

An action like collect(), count(), save(), or show() triggers the execution of the transformations. At this point, Spark takes the DAG and optimizes it, generating a physical plan that is executed across the cluster.
Only when an action is called does Spark begin to process the data by executing the transformations in a lazy manner.
