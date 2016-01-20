
There are a lot of entities that we would like the model that can’t be described using primitive types such as integers or characters. However, we can usually describe some property of said entities using such primitive types. To make modelling and working with representations of complex entities easier, most programming languages allow us to bundle a bunch of primitive types that describe the properties of complex entities together into a whole that is a lot easier to work with and reason about than disconnected variables and values. In the C programming language, that is facilitated by structs.

To declare a struct, we use the struct keyword as show  below:

<div style="text-align: left;"><div class="gist-for-robots"><script src="http://gist.github.com/c954ff035d20251ec8f6.js"></script></div></div>In our example above, we have created a struct to represent complex numbers. After the **struct **keyword, we give the struct its name : complex_t. Inside of the curly braces, we describe the properties – the fields – our complex_t struct. Complex numbers comprise two components – a real component and an imaginary component.

In order for our structs to be of any use to us, we need to be able to set and get their fields. This is usually achieved using the dot-operator in C as shown below.

<div class="gist-for-robots"><script src="http://gist.github.com/c68e863030d6681567ab.js"></script></div>We declare the struct on line 4, and begin to set the values of its fields in lines 5 and 6. Since we would be initializing instances of our complex_t struct, it would be useful to have a function that abstracts this away for us.

<div class="gist-for-robots"><script src="http://gist.github.com/38a11a78c71483d1668e.js"></script></div>In the above, we also demonstrate that we can write functions that return instances of structs simply by letting the return type be struct struct_name. What about accepted structs as arguments ? This is done similarly.

<div class="gist-for-robots"><script src="http://gist.github.com/ffd2dcadde53103887c6.js"></script></div> 

 


