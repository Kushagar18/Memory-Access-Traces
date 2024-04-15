# Memory-Access-Traces
I used these memory access traces for my col216 assignment 3 on cache properties.

<a name="br1"></a> 

### Cache Simulator README

#INTRODUCTION

The goal of this assignment was to determine the most effective

cache conﬁguration using memory traces and a cache simulator.

Cache conﬁguration plays a crucial role in system performance, and

understanding the impact of different conﬁgurations is essential for

optimising memory access. This program simulates a cache memory system using various 

configurations and processes memory access traces. It allows users to specify cache 

parameters such as the number of sets, blocks per set, block size, write policy, and 

eviction policy via command-line arguments.

### Usage

To compile the program, use the following command:

```
g++ -o cache_simulator cache_simulator.cpp
```

To run the program, execute the compiled binary along with the required command-line arguments:

```
./cache_simulator <num_sets> <blocks_per_set> <block_size> <write-allocate|no-write-allocate> <write-back|write-through> <eviction_policy>
```

- `<num_sets>`: Number of sets in the cache.
- `<blocks_per_set>`: Number of blocks per set in the cache.
- `<block_size>`: Size of each block in bytes.
- `<write-allocate|no-write-allocate>`: Write policy specifying whether to allocate a block on a write miss.
- `<write-back|write-through>`: Write policy specifying whether to write data back to memory on a write miss.
- `<eviction_policy>`: Eviction policy specifying how to select a block for replacement (LRU/FIFO).

### Example

```
./cache_simulator 64 4 64 write-allocate write-back lru < memory_trace.txt
```

### Input Format

The program expects memory access traces from standard input in the following format:

```
<store_op> <address> <skip>
```

- `<store_op>`: Operation type, either 's' for store or 'l' for load.
- `<address>`: Memory address accessed.
- `<skip>`: Integer value used as a delimiter between memory access traces. It is ignored by the program and can be set to any value.

### Output

The program prints statistics about cache performance to the standard output, including:

- Total loads: Total number of load operations.
- Total stores: Total number of store operations.
- Load hits: Number of load operations that hit in the cache.
- Load misses: Number of load operations that missed in the cache.
- Store hits: Number of store operations that hit in the cache.
- Store misses: Number of store operations that missed in the cache.
- Total cycles: Total number of cycles taken by the cache simulation.

### Error Handling

The program performs basic error checking for command-line arguments and input validation. It will display usage instructions if incorrect arguments are provided.


<a name="br2"></a> 

###MEMORY ACCESS TRACES USED

[https://github.com/Kushagar18/Memory-Access-Traces/blob/main/](https://github.com/Kushagar18/Memory-Access-Traces/blob/main/Trace%20File%20used%20for%20testing%5C)

[Trace%20File%20used%20for%20testing\](https://github.com/Kushagar18/Memory-Access-Traces/blob/main/Trace%20File%20used%20for%20testing%5C)ꢀ

This is the link to my GitHub repository containing the test case of

memory accesses I used to ﬁnd the Best Cache Conﬁguration.ꢀ

###METRICS CONSIDERED

In my analysis, I examined the hit rates, miss penalties and the total

cache size for each cache conﬁguration. I compared the

performance metrics across conﬁgurations to identify trends and

assess the effectiveness of different cache setups.


##BEST CACHE CONFIGURATION

Based on my analysis, I identiﬁed the cache conﬁguration with a

moderate cache size, a balanced number of sets and blocks per

set, and a write-allocate, write-back policy with LRU eviction as the

most effective. This conﬁguration gives us a good balance between

hit rates, miss penalties, and total cache size, making it suitable for

a wide range of applications and workloads.

##CONCLUSION

In conclusion, I think that cache conﬁguration signiﬁcantly impacts

system performance and therefore, selecting the right conﬁguration

is crucial in order to optimise the memory access. My study

provides valuable insights into the performance of different cache

conﬁgurations and highlights the importance of considering various

factors such as cache size, block size, and eviction policy.



### Dependencies

The program requires a C++ compiler with support for C++11 features.

### Author

Kushagar Garg

### License

My assignment is licensed under the [MIT License](https://opensource.org/licenses/MIT). See the `LICENSE` file for details.
