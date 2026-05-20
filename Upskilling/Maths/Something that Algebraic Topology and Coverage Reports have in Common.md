
To calculate how much code is covered, we need to see how many execution paths there are in the code. This can be computed by turning the code into a graph, where branches such as loops and conditionals become nodes and continuations (or at least flow of logic) become edges.

We can calculate the number of paths via the formula $M = E - N + P$ (there are some variants) where $M$ is known as the cyclomatic complexity. This formula yields a Betti number. which exists in AT.