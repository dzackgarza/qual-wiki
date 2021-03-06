# Topics and Remarks

:::{.remark}
(DZG) on the structure of these notes: these are *extremely* disorganized at the moment, and only reflect some amalgamation of all of the random notes I made to myself while studying for qualifying exams.
As a result, things are bound to be out of order, and likely useless pedagogically unless you've seen most of the material before.
Moreover, this has been a long-running document (started in my undergrad years, so pre-2018), and since I've forgotten and rewritten certain things at various points, there may even be duplicated material (e.g. propositions stated/proved in multiple places, repeated exercises or statements, etc).

In any case, I'd love to hear if you do find it useful!
Readers are welcome to email me with any questions, comments, errors/typos, suggestions for improvement, or just to say hello! 😄
:::

:::{.remark}
Adapted from remark written by Roy Smith, August 2006:

"As a general rule, students are responsible for knowing both the theory (proofs) and practical
applications (e.g. **how to find the Jordan or rational canonical form** of a given matrix, **or the Galois group of a given polynomial**) of the topics mentioned."

:::

## General References

- David Dummit and Richard Foote, Abstract Algebra, Wiley, 2003. [@dummit_foote_2004]  

- Kenneth Hoffman and Ray Kunze, Linear Algebra, Prentice-Hall, 1971. [@hoffman_kunze_1981]

- Thomas W. Hungerford, Algebra, Springer, 1974. [@hungerford_2008]

- Roy Smith, Algebra Course Notes (843-1 through 845-3). [@smith]
  - Note: scroll down the page to find links to his course notes.

## Group Theory

> References: [@dummit_foote_2004], [@hungerford_2008], [@smith]
> "The first 6 chapters (220 pages) of Dummit and Foote are excellent.
All the definitions and proofs of these theorems on groups are given in Smith's web based lecture notes for math 843 part 1."

### Topics

Chapters 1-9 of Dummit and Foote

- **The first isomorphism theorem**,

- Fundamental theorem of finite abelian groups
- Left and right cosets
- Normalizer
- Lagrange's theorem
- Isomorphism theorems
- Lagrange's Theorem
- Group generated by a subset
- Subgroups and quotient groups
- Fundamental homomorphism theorems
- Direct and semi-direct products
	- Recognition of internal direct product
	- Recognition of semi-direct product
- Composite groups
- Structures of special types of groups such as:
  - p-groups
  - Dihedral,
	- Cyclic groups
	- Free groups
		- Generators and relations
  - Symmetric and Alternating groups
    - Cycle decompositions
- Group actions with applications to the structure of groups such as
	- **The Sylow Theorems**
		- Proof of Sylow theorems
	- Orbit stabilizer theorem
	- Orbits act on left cosets of subgroups
	- Action of $G$ on itself by conjugation
	- Class equation
	- Cayley's theorem
- The simple groups of order between 60 and 168 have prime order
- The simplicity of $A_n$, for $n \geq 5$
- Solvable groups
- Subgroups of index $p$, the smallest prime dividing $\size G$, are normal
- $p$-groups
- $p^2$ groups are abelian
- Automorphisms
  - Inner automorphisms
- $A_n$ is simple for $n\geq 5$
- Classification of groups of order $pq$
- Commutator subgroup
- Nilpotent groups
- Upper central series
- Lower central series
- Derived series
- Solvable groups
- Fratini's argument
 - The Jordan Holder theorem

  > The proof of Jordan-Holder is seldom tested on the qual, but proofs are always of interest.

## Linear Algebra

> References: [@dummit_foote_2004],[@hoffman_kunze_1981],[@smith]

### Topics

- Determinants
- Eigenvalues and eigenvectors
- Cayley-Hamilton Theorem
- Canonical forms for matrices
  - **Jordan canonical form**
  - **Rational canonical form**
- Linear groups ($\GL_n , \SL_n, \mathrm{O}_n, \mathrm{U}_n$)
- Duality
  - Dual spaces,
  - Dual bases,
  - Induced dual map,
  - Double duals
- Finite-dimensional spectral theorem

## Rings

> References: [@dummit_foote_2004],[@hungerford_2008],[@smith]

- DF chapters 13,14 (about 145 pages).

- Smith:
  - 843-2, sections 11,12, and 16-21 (39 pages)
  - 844-1, sections 7-9 (20 pages)
  - 844-2, sections 10-16, (37 pages)
- DF Chapters 7, 8, 9.

### Topics

- Properties of ideals and quotient rings
- The fundamental isomorphism theorems for rings 
- $I$ maximal iff $R/I$ is a field
- Zorn's lemma
  - Every vector space has a basis
  - Maximal ideals exist
  - Construct algebraic field closures
  - Why it is unnecessary in countable or noetherian rings.
  
  > Smith discusses extensively in 844-1.
- Chinese Remainder Theorem
- Euclidean algorithm
- Primes and irreducibles
- Gaussian integers
- Localization of a domain
- Field of fractions
- Factorization in domains
- Factorization in $Z[i]$
- Characterizations and properties of special rings such as:
  - Euclidean $\implies$ PID $\implies$ UFD
  - Domains
    - Primes are irreducible
  - UFDs
    - Have GCDs
    - Sometimes PIDs
  - PIDs
    - Noetherian
    - Irreducibles are prime
    - Are UFDs
    - Have GCDs
	- Results about PIDs *(DF Section 8.2)*
		- Example of a PID that is not a Euclidean domain
		*(DF p.277)*
		- Proof that a Euclidean domain is a PID and hence a UFD
		- Proof that $\ZZ$ and $k[x]$ are UFDs
		*(p.289 Smith, p.300 DF)*
		- A polynomial ring in infinitely many variables over a UFD is still a UFD 
		*(Easy, DF, p.305)*
  - Euclidean domains
    - Are PIDs
- Gauss's important theorem on unique factorization of polynomials:
  - $\ZZ[x]$ is a UFD
  - $R[x]$ is a UFD when $R$ is a UFD
- Polynomial rings
- Polynomials
	- Gauss' lemma
	- Remainder and factor theorem
	- Eisenstein's criterion
  	*(DF p.309)*
  > Stated only for monic polynomials -- proof of general case identical.
  > See Smith's notes for the  full version.
	- Reducibility
	- Rational root test
- Cyclic product structure of $(\ZZ/n\ZZ)\units$

  > Exercise in DF, Smith 844-2, section 18

- Gröbner bases and division algorithms for polynomials in several variables
  *(DF 9.6.)*


## Modules

> References: [@dummit_foote_2004],[@hungerford_2008],[@smith]

### Topics

- Fundamental homomorphism theorems for rings and modules

- Applications to the structure of:
  - Finitely generated abelian groups
  - Canonical forms of matrices

- Classification of finitely generated modules over PIDs
    *(with emphasis on Euclidean Domains)*

- Modules over PIDs and canonical forms of matrices.
  *DF sections 10.1, 10.2, 10.3, and 12.1, 12.2, 12.3.*

  - Constructive proof of decomposition: DF Exercises 12.1.16-19

  > Smith 845-1 and 845-2: Detailed discussion of the constructive proof.

## Field Theory

### Topics

> References: [@dummit_foote_2004],[@hungerford_2008],[@smith]

- Algebraic extensions of fields

- Properties of finite fields

- Separable extensions

- Fundamental theorem of Galois theory

- Computations of Galois groups 
	- of polynomials of small degree 
	- of cyclotomic polynomials

- Solvability of polynomials by radicals

