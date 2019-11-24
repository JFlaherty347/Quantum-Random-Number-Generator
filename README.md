# Quantum-Random-Number-Generator
### What is this Repository?
This code is written in IBM's [OpenQASM](https://en.wikipedia.org/wiki/OpenQASM) on their IBM Q Experience platform for quantum 
computing. It also contains results from running on a simuated quantum computer as well as an real cloud computer. The scope of
this project is relatively small and instead seeks to investigate a unique property of an emerging technology.

### What does this Code do?
This code aims to randomly generate numbers that are in the set B = {2 + 4n | n >= 0}, in this case doing so up to the limitation 
of four-bit numbers. In other words, this code randomly generates either 2, 6, 10, and 14 when restricted to 4 bits. This 
restriction is placed on the number in order to reduce the required amount of quantum computing power. It does so by first creating 
a superposition, via a Hadamard gate, on every bit except the least significant bit, resulting in only even numbers. To further 
restrict even numbers to set B, a Ry gate is used on the second least significant bit with an angle of pi/2 radians, thus rotating 
the qubit around the y-axis by pi/2. 

### Inspiration
I was inspired to create this code because quantum computers offer truly random number generation as opposed to the pseudo-random 
number generation employed by classical computers. Furthermore, through bit manipulation, it was possible to restrict the 
generation so I was interested to see if I could get the code to generate a more complex set than integers, even numbers, or odd 
numbers. I thought that this could be especially valuable for cases in which a random value within a certain set of restrictions was required.

### Analysis

The histogram below details the equal probabilities of producing each number as output
![Probability Hist](https://github.com/JFlaherty347/Quantum-Random-Number-Generator/blob/master/Images/Outcome%20Probability.png)

When running on a quantum computer simulation with a sample size of 1024, a notable fluctation occured in the case of
1010 and 1110.

![Simulation Bar Graph](https://github.com/JFlaherty347/Quantum-Random-Number-Generator/blob/master/Images/Simulator%20Output.png)

In the output ran on a quantum computer, numbers in set B are the most common, each occurring more than 20% of the 
time. In this run instead of 25% there was 20%, 21%, 21%, and 24% which is a concerning distance away for something 
that is intended to be random. In the case of all four 4-bit numbers in B, each had a corresponding 2-3% number one 
bit off from being in B. This, in comparison to the less than 1% errors, is a significant source of inaccurate output, 
totaling to over a 10% chance of getting unintended results.

Below is a visual representation of the code and the results of a sample size of 1024 ran on an IBM quantum computer.

![Quantum Bar Graph](https://github.com/JFlaherty347/Quantum-Random-Number-Generator/blob/master/Images/Quantum%20Output.png)

### Conclusion
This project was a great exercise in learning in an unfamiliar enviornment. With the immense amount of fluctuation 
from all expected outputs, it would seem that this has occurred completely out of chance. That being said, quantum 
computing with reduced error and improved developer tools could prove to be excellent at several specific areas that classical computers struggle. 
