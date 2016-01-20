One of the features I miss when I am not using an ML-dialect or member of the Haskell "family" of languages is the creation of functions that are curried by default. In these languages, when you create a function that accepts multiple arguments, you are really creating a function that accepts a single argument and returns another function. Using currying, I can define a general version of a function, and then specialise it with minimal effort by simply supplying the first argument, such as in the below example.

<script src="https://gist.github.com/InzamamRahaman/c166ba8c8252f5f52025.js"></script>

Most functional languages have the ability to partially apply a function to achieve the same effect 





