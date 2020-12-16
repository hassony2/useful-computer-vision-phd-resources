# Code profiling

- [line_profiler](https://github.com/rkern/line_profiler) to profile python code line by line
   - typical usage involves adding a `@profile` decorator to the function you want to profile
   - launch your usual script with `CUDA_LAUNCH_BLOCKING=1 kernprof -lv main.py --flag1 VALUE1 ...`
   - Ctrl+C to interupt after some time
   - investigate results !
   - (CUDA_LAUNCH_BLOCKING=1 prevents laze execution of CUDA functions, non-blocking mode improves execution times but is less interpretable (e.g. code for a line is actually later, and therefore contribute to the execution line of some other line)
