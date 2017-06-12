In order to produce these automata benchmarks, we run the follwing
* Termination analysis of Ultimate Automizer
* on the termination category benchmarks of SV-COMP 2017 but limited the number of C files per directory to 50 (randomly selected)
* using the SUNFLOWER settings (the SUNFLOWER settings deviate from the default SV-COMP settings in the strategy in which the BÜchi automata are build: we already allow nondeterministic automata in the first stage)
* using procedure inlining
* using a timeout of 300s 

Each .ats file corresponds to one interation of our cegar loop and contains two Büchi automata
1. the abstraction of this iteration
2. the "interpolant automaton" (called _module_ in our CAV 2014 paper) that was build in this iteration

These automata are interesting benchmarks for inclusion checks because at the end of the iteration we construct the language difference of both and at the beginning of the next iteration we check emptiness of the difference.

We omitted all iterations in which the interpolant automaton was deterministic.
We omitted all recursive programs (there the inlining fails, we have to use our interprocedural analysis and get Büchi nested word automata).

License: https://creativecommons.org/licenses/by-sa/4.0/

2017-06-11 Matthias Heizmann (heizmann@informatik.uni-freiburg.de)
