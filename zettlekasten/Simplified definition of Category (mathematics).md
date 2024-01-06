2023-12-27 05:12:30
Status: #reference 
Tags: [[Category Theory]], [[Mathematics]]
# Simplified definition of Category (mathematics)

## Categories have objects
Every category has a collection of objects. Objects can be anything. We can generally specify the objects of a category using a set.

```ad-note
This fits within the pardigm of object oriented programming and logically maps to traditional data storage in RDBMS.
```

## Categories have morphisms
For any two objects, $A$ and $B$, a category $\mathcal{C}$ has a set of morphisms $\{f, g, ...\}$
$$\mathcal{C}(A,B)=\{f, g, ...\}$$

A morphism is denoted by $f:A\rightarrow B$, meaning that $f$ maps $A$ to $B$; or $A$ is related to $B$ through $f$. 

The set of morphisms in $\mathcal{C}$ can be an empty set, which would mean that $A$ is not related to $B$.

## Categories have composition

If there is are two morphisms $f: A\rightarrow B$ and $g:B \rightarrow C$ then there is a morphism $h:A \rightarrow C$ where $h = g\circ f$

$$
\def\diaguparrow#1{\smash{\raise.6em\rlap{\ \ \scriptstyle #1}
   \lower.6em{\cancelto{}{\Space{2em}{1.7em}{0px}}}}}
\begin{CD}
&& B \\
& \diaguparrow{f} @VVgV \\
A @>>h> C
\end{CD}$$

## Categories have identities
Categories must have special morphisms called identities, denoted as $1_A : A \rightarrow A$. This implies that the set of morphisms for any category to itself is non-empty, $\mathcal{C}(A, A) = \{1_A ...\}$. 

## Compositions are subject to the Identity Law
Composing any morphism with an identity will result in the original morphism. $f\circ 1_A = f$ and $1_B \circ f = f$.

## Compositions are subject to the Associativity Law
We are able to map objects through compositions in any order of operation. If $f:A\rightarrow B$, $g:B\rightarrow C$ , and $h:C\rightarrow D$  then $(h\circ g)\circ f = h \circ (g \circ f) = h \circ g \circ f$. 

---

## References
[[@oliverluggSensibleIntroductionCategory2022]]