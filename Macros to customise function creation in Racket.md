Homioconicity serves as one of the most cardinal features of any Lisp. The disruption of the barrier between code and data by virtue by providing a unified means of representing both within the language allows the programmer to extend syntax as they need - to, in effect, craft an internal DSL to adequately express their computational ideas. When I first delved into the the seemingly arcane world of what I deemed at the time to be "esoteric" programming languages, it is this property of homioconicity and the concept of macros used to leverage homioconicity that drew me to the languages of the Lisp family. 

Racket, the descendent of the august language Scheme, has facilities for manipulating syntax using programmer-defined rules just like any other Lisp. However, macros in Racket were a bit more difficult to grasp than macros in Clojure. I still feel rather uncertain while writing macros in Racket, at least when compared to writing macros in Clojure.

Sometimes, when writing code in a Lisp, I miss the syntax for defining anonymous functions from the functional languages in the ML family. To practice macros in Racket, I thought it might be a fun idea to emulate something of that syntax in Racket to be to create simple functions using syntax like this:

<script src="https://gist.github.com/InzamamRahaman/d2b15b78004f61f44e54.js"></script>

    


For my first attempt, I came up with this:
<script src="https://gist.github.com/InzamamRahaman/c222983f0bb659f14b72.js"></script>

Since our macro in this case has only a single valid pattern, we can use *define-syntax-rule* to allow us to define said macro. Right after *define-syntax-rule* we need to specify the pattern for the macro. This pattern is supposed to provide the name for the macro, as well as to provide a name for the various "arguments" to our macro for us to describe the code to be generated in its stead. 



In our above case, *define-mapping* is the name for our macro, and the rest describe and assign names to other pieces of our pattern. The ~~> acts as a literal to demarcate our parameter list and the operations to be performed. The ellipses is like the star operation of regular expressions, matching 0 or more of the item specified. Below, we can see usage

<script src="https://gist.github.com/InzamamRahaman/300d5098d57c1dcc0f27.js"></script>

However, suppose that we want to capable of assigning a name to the function generated without having to wrap the macro application in a separate *define* expression. We can improve on our macro above to accomplish this. Should we want to maintain the ability to define anonymous functions this way, while keeping the macro name, we need to use a *syntax-rule*.




