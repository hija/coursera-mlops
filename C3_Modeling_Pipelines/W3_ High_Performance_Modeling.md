# High Performance Modeling

## Distributed training
* Data parallelism: Models are replicated onto different accelerators (GPU/TPU) and data is split between them
* Model parallelism: A model is divided into partitions, assigning different partitions to different accelerators. This is often used if one model becomes too big to be trained on one accelerator

--> Optimized pipeline, e.g. using tf.interleave + caching

## Teacher and Student Networks

* Train a big NN, a "teacher"
* Then train a smaller NN, a student, which tries to match the probability-distribution of the teacher’s predictions to form ‘soft targets’ --> "Distilling" the knowledge from the teacher in a student NN