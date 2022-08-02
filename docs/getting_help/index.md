# Getting Help

Before asking for help, it's very important for you to try to solve your own problems.

The most important thing you can do is read your log files, and look for things which are out
of the ordinary compared to rest of the pattern. A good place to start is at the end of the file,
however due to use of parallel processing, this is not always the where you'll find the problem.

Words to look for to isolate a problem:
- `segmentation fault`
- `killed`
- `error`
- `fail`
- `warning` -- sometimes

Be sure to check case.

You can use `less` to browse a log file and `/` inside `less` to search. Use the keyboard to move around.

When asking for help, it's important to fully explain the problem you're having, this means explaining
- what you're doing, including anything out of the ordinary
- where you're doing it (what computer, and how you're accessing it, i.e. locally/remotely, SSH, X2Go, wifi, ethernet, inside/outside Douglas network)
- what the error/problem/unexpected result you're getting
- the complete paths/access to the inputs, outputs, and logs
- what you tried to do to solve your problem (in detail) and the results

For more background on getting help, these documents are excellent in understanding how to communicate about this:
- https://www.chiark.greenend.org.uk/~sgtatham/bugs.html
- http://www.catb.org/~esr/faqs/smart-questions.html#beprecise
- https://en.wikipedia.org/wiki/XY_problem
- https://stackoverflow.com/help/minimal-reproducible-example
