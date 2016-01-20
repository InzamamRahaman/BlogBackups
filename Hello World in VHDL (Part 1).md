
For my final year project, I’ve been adapting some work done by some of our lectures in DCIT to work on an FPGA board. Aside from a Computer Architecture class two years ago and some toying around with a Raspberry Pi, this is the first time I’m doing anything really hardware-oriented. I must say that describing hardware in VHDL is different from crafting software in other languages that I’ve been exposed to – especially since I’ve been spoiled by the massive flexibility and modularity functional programming provides! With every construct I type, I bit of worry bubbles up in my mind that I’ll write something that is not synthesizible  or won’t be synthesize to an efficient design for the Xillinx Spartan 3E housed in the Diligent Basys board I’m using.

I’d figure that quite a few of us from a non-hardware oriented background might find the paradigm shift difficult at first. I’ve got a lot to learn about VHDL and hardware design, but maybe noting my experiences might help another beginner along – or at least remind them they are not alone in being a little shocked and flummoxed when they first start.  For now, I’ll just handle some basics. So with that said, let’s get to the fun – the code !

 

**Introduction**

The most fundamental idea in digital design is the concept of a bit – a value that may be a ‘0’ representing a low voltage or a ‘1’ representing a high voltage. In VHDL, we model the concept of a bit with the std_logic type. Sometimes we need to model a collection of bits under a similar label. In most programming languages, we would represent a collection like that using an array or list. In the hardware-description language of VHDL, we have access to a similar concept of an array, and in the particular case of std_logic, we have an array type called std_logic_vector.

We model designs using entity-architecture pairs. The entity is used to describe the data being read into the design and sent out by virtue of ports, and the architecture is used to describe the logic of what should happen in the circuit. In some ways, these entity-architecture pairs can be likened to the interface-concrete implementation pairs of object oriented programming languages such as Java. With these ideas in mind, we can now consider an example that is likely to be familiar to those of you who did Physics in high school: an AND Gate.

**Implementing an AND Gate**

An AND gate is simple circuit that implements the AND boolean operation, which may be described by the following truth table

<table class="tg"><tbody><tr><th class="tg-031e">input 1</th><th class="tg-031e">input 2</th><th class="tg-031e">output</th></tr><tr><td class="tg-oopb">0</td><td class="tg-oopb">0</td><td class="tg-oopb">0</td></tr><tr><td class="tg-oopb">0</td><td class="tg-oopb">1</td><td class="tg-oopb">0</td></tr><tr><td class="tg-oopb">1</td><td class="tg-oopb">0</td><td class="tg-oopb">0</td></tr><tr><td class="tg-usb5">1</td><td class="tg-usb5">1</td><td class="tg-usb5">1</td></tr></tbody></table>With the above in mind, we can start to implement our AND Gate.

*Entity*

Looking at our truth-table, we see that we have two inputs and one output. We may describe this using VHDL as follows:

<div class="gist-for-robots"><script src="http://gist.github.com/f437a0273e8466ba9fde.js"></script></div> As we discussed above, the input and output sources are our ports. In VHDL we need to annotate our ports with both the types associated with their content and if they are to be used as a source of input (in), output (out) or input and output (inout) as show in lines 3 through 5.

*Architecture*

If our entity is our interface, our architecture acts as a concrete implementation of our described entity.


