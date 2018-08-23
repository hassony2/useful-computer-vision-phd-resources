# Run faster, better, reproducible Python experiments

## Tools

### Configure, organize and reproduce

<details> <summary> <a href="https://github.com/IDSIA/sacred"><b>Sacred </b>: The key to reproducible experiments </a> </summary> 

- Saves all parameters, commit, source code for your experiment

- Sets and saves random seeds

- Saves output and logs 

</details>


<details> <summary> <a href="https://github.com/chovanecm/sacredboard"><b>Sacredboard </b>: Keep track of your experiments, in your browser </a> </summary> 

- Visualize experiment status, parameters, logs from your sacred experiments

</details>


### Profile 
<details> <summary> <a href="https://github.com/rkern/line_profiler"><b>line_profiler </b>: efficient line-by-line profiling of your code </a> </summary> 

- Efficient summaries of time taken to run each line of code in a given function (number of hits, time per hits, percentage of total time, ...)

- Doesn't work when multiprocessing is used, when profiling multiprocessed code (for instance data loading code), use only one thread at profiling time

</details>
