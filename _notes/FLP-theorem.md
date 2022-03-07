---
---

The [article](https://groups.csail.mit.edu/tds/papers/Lynch/jacm85.pdf)

- Async model
- Deterministic algo
- $f\leq1$

![04-lec-flp-model](img/04-lec-flp-model.png)

**Binary [[consensus-problem]]:** {0, 1}
- Bivalent: has not chosen 0 or 1
- Univalent: in any continuation will choose 1 or 0

> To prove, that we can travel through only bivalent confighs

#### L1. Bivalent starting configuration exists

![04-lec-flp-l1](img/04-lec-flp-l1.png)

#### L2. Bivalent $\longrightarrow$ Bivalent

![04-lec-flp-l2-model](img/04-lec-flp-l2-model.png)

![04-lec-flp-l2-proof](img/04-lec-flp-l2-proof.png)

* So, we **need** assumptions about Time
