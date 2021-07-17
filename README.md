# quantum
To demonstrate how much power quantum computers can have over regular computers, we’re going to be looking at an algorithm which has been implemented called the Bernstein-Vazirani Algorithm.
#Secret number:
The Bernstein-Vazirani Algorithm specializes in finding a secret number.
So, let's say we put a secret number in a box, say it’s 1001 (the number 9 in binary), how many steps will it take us to find that secret number?
This problem seems very trivial, and it’s actually something classical computers can already do.

#The Classical approach:

The way a classical algorithm would go about approaching this problem, is by going through a series of AND operations, to find our secret number.
So, using the number 1001, the classical approach will make its first “guess” as to what the number might be. It’s first guess is always going to be leading zeros, followed by a 1.
So in our case, it’s first guess is going to be 0001. Now the algorithm is going to query the oracle, and use an AND comparison to see if there’s a 1 in the same spot.
Comparing these two numbers:
1001
0001
We can see that they both have a 1 as the last bit, so this means that the algorithm has found a 1 in that place. (Since AND(1,1) = 1)
This series of guesses is repeated for every bit in the secret bitstring. So our next guesses are going to be 0010, then 0100, and so forth. Our algorithm just keeps performing these AND operations to see if there is a 1 in that place.
Now this seems pretty efficient; better than just guessing and checking. But the thing is this algorithm will have to perform as many steps as there are bits in our secret bitstring. So if we had a bitstring with 1 million bits, we would have to query the black box 1 million times!
This is where quantum computers can come to the rescue.

#The Quantum approach:

Quantum computers can take this problem, and find the secret number with just one step.
Using IBM’s Qiskit, I implemented this algorithm, along with circuit visualizations with a step by step process.

First we create a quantum circuit for as many qubits or bits we want by taking one extra qubit to fulfill the need of algorithm.Then we apply Hadamard Gate to all the qubits and apply bit flip gate to the last qubit.Then we enumerate for qubits those are ones and apply controlled not gate to them.Then we again apply Hadamard gate to all qubits to make them out of superposition.At last we measure our circuit by using measure() function and then draw our circuit.
Then we take our simulator from Aer.get_backend from "qasm_simulator".Then we execute the result by importing histogram from qiskit visualization library.
Then we just plot the histogram and can see the results.

Comparing time complexities of BERNSTEIN-VAZIRANI algorithm by running the same on multiple quantum computers which is available to access for developers.
The Bernstein-Vazirani algorithm deals with finding secret numbers.
While running it on classical computers our finding states that time complexity was O(n).
Similarly we accessed multiple quantum computers (IBM and DWave)which available to use, our finding states that Bernstein-Vazirani(BV) algorithm take a constant time irrespective
of the length of the secret number. Hence complex algorithms like BV take constant time which demonstrate the power of quantum computers. 
