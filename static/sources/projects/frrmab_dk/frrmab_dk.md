layout: true
<div class="remark-header"><span><a href="" class="remark-quit-cross"><i class="fas fa-times fa-2x"></i></a></span></div>
<div class="remark-footer"><span>Photo album project
<a href="https://github.com/jbuisine/FRRMAB_DK.git" class="remark-icon-bottom"><i class="fab fa-github fa-1x"></i></a>
</span></div>

---
class: center, middle
# FRRMAB directions knowledge

<hr>
**Description** : Adaptive Operator Selection into the MOEA/D algorithm. This AOS called FRRMAB_DK is based on MAB algorithm for each sub problem with shares of information.

---
## Description

This project wants to introduce a new approach in use of UCB Multi Armed Bandits algorithm into the  ***Multiobjective Evolutionnary Algorithm based on Decomposition*** (MOEA/D).
This MAB algorithm brings an automatic selection of an operator (mutation/crossover ) used to generate new solution (offspring) in order to reduce time consuming and lead to best solutions of the search space.
The MOEA/D algorithm proposes scalar decomposition of multi objectives problem into ***n*** mono-objective problems.
The final approach of this project is to introduce a new way of using MAB algorithm on each sub problem with information shares based on affinity of sub problems. FRRMAB_DK is based on FRRMAB which have been proposed **[[1]](https://doi.org/10.1109/TEVC.2013.2239648)**.

---

## Installation

It's a cmake project, so you only need to :

```
mkdir build
```

```
cd build
```

And then :
```
cmake
```

---

## MOEA/D

For MOEA/D algorithm, QAP instances are generated following this available [generator](http://www.cs.bham.ac.uk/~jdk/mQAP/).

---

## Licence

[CeCILL](http://www.cecill.info/index.en.html)
