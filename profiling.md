# Profiling on Linux

Simple tips for software profiling using Linux.

## Simple steps on using gprof:

[gprof](http://www.cs.utah.edu/dept/old/texinfo/as/gprof.html) is a really efficient prototyping tool designed by Richard Stallman

It is a total graal to exactly know where your bottlenecks are, and which parts of your software have to be optimized first!

- Simply install gprof on your computer (for debian based distros).
```bash
$ sudo apt-get install gprof
```
- Compile your C code with the -pg option
- Execute your program, just as usual

You will see that a **gmon.out** file was created during the execution
You can retrieve the results of profiling by running gprof:
```bash
$ gprof your_binary gmon.out >> saved_report
```

and then read the result
```bash
$ vim saved_report
```
