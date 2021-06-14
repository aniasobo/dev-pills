# Algorithms

## Big O notation

Notation representing how long an algorithm takes to run. Used to compare the efficiency of different solutions to a problem.

Runtime measured in **how quickly it grows relative to the input as the input gets larger**.

From [this article](https://www.interviewcake.com/article/python/big-o-notation-time-and-space-complexity):

Let's break that down:

1. **how quickly the runtime grows** — It's hard to pin down the exact runtime of an algorithm. It depends on the speed of the processor, what else the computer is running, etc. So instead of talking about the runtime directly, we use big O notation to talk about **how quickly the runtime grows**.
2. **relative to the input** — If we were measuring our runtime directly, we could express our speed in seconds. Since we're measuring **how quickly our runtime grows**, we need to express our speed in terms of...something else. With Big O notation, we use the size of the input, which we call `n`. So we can say things like the runtime grows "on the order of the size of the input" `(O(n))` or "on the order of the square of the size of the input" `(O(n^2))`.
3. **as the input gets arbitrarily large** — Our algorithm may have steps that seem expensive when `n` is small but are eclipsed eventually by other steps as `n` gets huge. For big O analysis, we care most about the stuff that grows fastest as the input grows, because everything else is quickly eclipsed as `n` gets very large. (If you know what an asymptote is, you might see why "big O analysis" is sometimes called "asymptotic analysis.")

---

## Notes from the Green Book:

### Multi-part algorithms: Add vs Multiply

- if your algorithm is in the form of `do this, then, once done, do that` then you add the runtimes `O(A + B)`
- if your algorithm is in the form of `do this for each time you do that` then you multiply the runtimes `O(A * B)`
