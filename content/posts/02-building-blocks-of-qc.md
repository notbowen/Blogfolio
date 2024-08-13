---
title: "The Building Blocks of Quantum Computing"
date: 2023-12-04
---

[NOTE] This is currently a work in progress article!

Recently, I picked up a book by Chris Bernhardt, titled [Quantum Computing for Everyone](https://mitpress.mit.edu/9780262539531/quantum-computing-for-everyone/).
It does a great explanation for the principles of quantum computing, and at the time of writing, I'm currently reading up on the section on linear algebra.

This blog post is meant to serve as a avenue for me to dump my notes and consolidate my learning as I progress further down the book, and should not be treated as proper reference material or a comprehensive guide.

Now with that clarified, please allow me to try and string together a barely coherent explanation on my interpretation of the linear algebra concepts from the book.

## Bras and Kets

Though the name sounds interesting and cryptic, Bras and Kets simply refer to n-dimensional vectors arranged horizontally and vertically respectively.
A Bra denoted as `A` would be represented as \\(\left< A \right|\\), and a Ket denoted as `B` would be represented as \\(\left|B\right>\\).

2 dimensional Bra (horizontal):
$$\left< A \right| = \begin{bmatrix}
    a & b
\end{bmatrix}$$

2 dimensional Ket (vertical):
$$\left| B \right> = \begin{bmatrix}
 a \\\ b
\end{bmatrix}$$

## Magnitude of Kets

Secondary school math has taught us that the length of a vector can be calculated using Pythagoras' theorem.
For example, given a vector `A` with values \\(\begin{bmatrix}a \\\ b\end{bmatrix}\\), we can apply the Pythagoras' theorem and deduce it's magnitude using \\(\sqrt{a^2 + b^2}\\).

However, there is another way to calculate the magnitude of a vector using bras and kets!
Observe what happens when we multiply the bra of `A` to the ket of `A`:

$$\begin{aligned}
    \left<A\right| \left|A\right> &= \begin{bmatrix}
        a & b
    \end{bmatrix}
    \begin{bmatrix}
        a \\\ b
    \end{bmatrix} \\\\
    &= (a)(a) + (b)(b) \\\\
    &= a^2 + b^2 \\\\
    \therefore \sqrt{\left<A|A\right>} &= \sqrt{a^2 + b^2}
\end{aligned}$$

Wow! We can thus conclude that the square root of the bra-ket product would give us the length of the vector.

## Orthogonal Vectors

Orthogonal vectors are perpendicular to each other.
2 vectors are considered orthogonal to each other if \\(\left<A|B\right> = 0\\).
Why? Lets try to prove it by building off the previous section.

If 2 vectors, a and b, are orthogonal, their resultant vector's magnitude, c, should satisfy the following equation:

$$|a|^2 + |b|^2 = |c|^2$$

![Orthogonal vectors](/images/building-blocks-of-quantum-computing/orthogonal_vectors.png)

Hence, if 2 vectors are orthogonal to each other, \\(|\left|A\right>|^2 + |\left|B\right>|^2\\) should be equal to \\(|\left|A\right> + \left|B\right>|^2\\)

By rewriting \\(|\left|A\right> + \left|B\right>|^2\\), we get:

$$\begin{aligned}
    |\left|A\right> + \left|B\right>|^2 &= \left<A+B|A+B\right> \\\\
    &= \begin{bmatrix}
        a_1 + b_1 & a_2 + b_2
    \end{bmatrix}
    \begin{bmatrix}
        a_1 + b_1 \\\ a_2 + b_2
    \end{bmatrix} \\\\
    &= (a_1 + b_1)^2 + (a_2 + b_2)^2 \\\\
    &= ({a_1}^2 + 2a_1b_1 + {b_1}^2) + ({a_2}^2 + 2a_2b_2 + {b_2}^2) \\\\
    &= {a_1}^2 + {a_2}^2 + {b_1}^2 + {b_2}^2 + 2(a_1b_1 + a_2b_2) \\\\
    &= |\left|A\right>|^2 + |\left|B\right>|^2 + 2\left<A|B\right>
\end{aligned}$$

The equation above shows that if \\(2\left<A|B\right> = \left<A|B\right> = 0\\), \\(\left|A\right>$ and $\left|B\right>\\) are orthogonal.