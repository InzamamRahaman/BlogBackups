As many other undergrads in Computer Science would've done at least once, I've written parsers and interpreters for toy languages. Previously, most of my mini-projects involving toy languages used either hand-written recursive descent parsers or (if done in F#, Haskell, Scala) parser combinators. 

Due to being easier to write and, in my opinion, debug, I tended to write my parsers using parser combinators when possible. However, parsers using parser combinators tend to be very inefficient. For toy purposes, this isn't really an issue, but it would be nice if I could leverage a technology that is as easy to use as parser combinators but more efficient for my projects. In fact such a technology exists! 

Parsing Expression Grammars (also called PEGs) allow for a degree of flexibility on par with parsing combinators, but is several times more efficient. I first came across them while reading a book a lecturer lent me on creating a custom programming language in Ruby (How To Create Your Own Freaking Awesome Programming Language by Marc-André Cournoyer). At the time, I was considering do a PL project for my final year thesis/project. In the end, I opted to implement the work of some of my lecturers on an FPGA. Nonetheless, my interest in PEGs was stirred. 



