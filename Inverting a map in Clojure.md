
While working on a solution to another Rosalind problem, I encountered a situation where I needed to invert the key-value relationships in a map \(m\) such that \\(\forall k\_1, k\_2, …, k\_n, v \\) such that \\((k\_1, v), (k\_2, v), …,(k\_n, v) \in m\\) we would have \\((v, [k\_1, k\_2, …, k\_n]) \in m’ \\) where \\(m’\\) is the inverted map.  I couldn’t find something in Clojure that did exactly what I wanted, so I wrote a simple function to do it for me.

<div class="gist-for-robots"><script src="http://gist.github.com/da702d41a112ec51d723.js"></script></div>At the heart of this solution lies a nifty function in the standard library called [merge-with](https://clojuredocs.org/clojure.core/merge-with) that merges a variable number of maps  while allowing the caller to specify how to handle collisions.

First we can divide our larger map comprising of key-value pairs, \\((k\_i, v\_i) \\) into smaller maps \\(m\_1, m\_2, …, m\_i \\) comprising of \\((v\_i, [k\_i])\\). We then use *merge-with*, specifying *concat* as our function to resolve collisions.


