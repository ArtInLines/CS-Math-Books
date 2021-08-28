## Proving the correctnes of algorithms

**Loop Invariants** help prove the correctness of algorithms, as they are statements about a specific loop, that always have to be fulfilled for the algorithm to be correct.

1. **Initialization:** It is true prior to the first iteration of the loop.
2. **Maintenance:** If it is true before an iteration of the loop, it remains true before the next iteration.
3. **Termination:** When the loop terminates, the invariant gives us a useful property that helps show that the algorithm is correct.
