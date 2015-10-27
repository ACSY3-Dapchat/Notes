#Questions and Answers
*In lecture 3, we were given a list of questions to answer before the next lecture*

##1. How Do You Describe A Hypothesis?

A hypothesis is described by a conjunction of constraints on the attributes.

The constraints may be:
* *?* - Any value is acceptable
* *0* - No value is acceptable
* Or a specific value

##2. Why is it necessary to define the *more-general-or-equal-to* relationship between different hypotheses?

To make it possible to design algorithms that exhaustivel search even infinite hypothesis spaces without explicitly enumerating every hypothesis.

##3. What does "an instance satisfies a hypothesis" mean?

That all of the attributes of the instance satisfy all of the constraints of the hypothesis.

##4. What does "a hypothesis is consistent with training examples" mean?

That all of the positive training examples satisfy the hypothesis, while none of the negative ones do.

##5. What is the rote learner?

**Need to re-do this one**

##6. What is the Find-S algorithm?

```
    Initialise h to the most specific hypothesis in H
    For each positive training instance x
        For each attribute constraint ai in h
            If the constraint ai is satisfied by x
            Then do nothing
            Else replace ai in h by the next more general constraint that is satisfied by x
    Output hypothesis h
```

##7. What is the List-Then-Eliminate algorithm?

List all hypotheses in H
Eliminate any hypothesis found inconsistent with any training examples

##What is inductive bias?
