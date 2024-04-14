# PooQ-Bears

## Theory

### Sparse States

A key point of many quantum algorithms is encoding a classical state into a quantum state. Doing this for most wave functions is difficult, but gets significantly easier for sparse states which are states where most probability amplitudes $c_i$ in $\phi$ are equal to zero.
$$\phi = \sum_{x \in S} c_x |x\rangle$$

An algorithm by Gleinig and Hoefler takes advantage of sparse states in order to encode a quantum state onto a circuit. If implemented correctly, then inputting the state $\phi$ into the algortihm will return a circuit such that when $|0^{\otimes n}\rangle$ is inputted, the state $\phi$ is prepared.

## Our Implementation

 In our stencil we are provided an algorithm similar to that designed by Gleinig and Hoefler with unknown operations ops 1 through 5. In this stencil we were given an example state 

 $$\psi =  \frac{1}{2}|000\rangle + \frac{1}{\sqrt{2}}|001\rangle + \frac{1}{2}|111\rangle $$

as an input to the algorithm. To figure out what ops 1-5 were we applied the algorithm by hand and saw clear patterns emerge between ops 2-5 and the gates in the algorithm. We determined that ops1 gave the position of the the gates in the circuit and ops 2-5 corresponded to certain gates. Ops 2 corresponded to not gates, ops 3 corresponded to cnot gates, ops 4 corresponded to the G matrix in the paper, and ops 5 relates to the not gates in algorithm 2 of the paper. The algorithm implemented in the stencil code gave us the gates needed to turn $\psi$ into $|0^{\otimes n}\rangle$. This means that to get a circuit that returns $\psi$ from the input $|0^{\otimes n}\rangle$, we need to apply the inverse of these gates in reverse order. We did this by hand for the given $\psi$ above, and then generalized the code to work for all $\psi$.



## Analysis