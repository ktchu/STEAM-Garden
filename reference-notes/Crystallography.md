Crystallography
===============

*Author(s)*: Kevin Chu `<kevin@velexi.com>`

__Last Updated__: 2023-07-15

--------------------------------------------------------------------------------------------

Table of Contents
-----------------

1. [Crystal Lattices][#1]

2. [Miscellaneous Notes][#2]

3. [References][#3]

--------------------------------------------------------------------------------------------

## 1. Crystal Lattices

### Notation and Conventions

* $\newcommand{\a}{\mathbf{a}}\newcommand{\b}{\mathbf{b}}\newcommand{\c}{\mathbf{c}}$
  The basis vectors a unit cell: $\a, \b, \c$

  * $\a, \b, \c$ form right-handed coordinate system.

* Lattice constants
  * The length lattice constants of a unit cell: $a, b, c$.
  * The angle lattice constants of a unit cell: $\alpha, \beta, \gamma$.
  * $\alpha$ is the angle between $\b$ and $\c$, $\beta$ is the angle between $\c$ and $\a$,
    and $\gamma$ is the angle between $\a$ and $\b$.

### Seven Crystal Systems

* In three dimensions, there are seven crystal systems characterized by their symmetry.

  | crystal system | edge constraints |                 angle constraints                 |
  |----------------|------------------|---------------------------------------------------|
  | triclinic      | none             | none                                              |
  | monoclinic     | none             | $\alpha = \gamma = 90^\circ$                      |
  | orthorhombic   | none             | $\alpha = \beta = \gamma = 90^\circ$              |
  | tetragonal     | $a = b$          | $\alpha = \beta = \gamma = 90^\circ$              |
  | trigonal       | $a = b$          | $\alpha = \beta = 90^\circ$, $\gamma = 120^\circ$ |
  | hexagonal      | $a = b$          | $\alpha = \beta = 90^\circ$, $\gamma = 120^\circ$ |
  | cubic          | $a = b = c$      | $\alpha = \beta = \gamma = 90^\circ$              |

* __Conventions__
  * monoclinic: $\b$-axis chosen as unique axis, $\beta > 90^\circ$
  * trigonal, hexagonal, tetragonal: $\c$-axis chosen as unique axis

* The crystal system can only be determined from the symmetry elements of the unit cell
  _after all atom positions have been determined_. Identification of a unit cell from
  experimental data (e.g., powder diffraction indexing) can only give an "indication" of
  the crystal system. Further analysis is necessary to make a final determination of the
  symmetry properties of the crystal and hence its crystal system.

### Fourteen Bravais Lattices

* The unit cell is of a lattice is selected to (1) have the highest symmetry and (2) the
  smallest volume with priority is given to higher symmetry.

  * If the crystal has inversion symmetry, the origin of the unit cell is located at an
    inversion center.

* Unit cells with the smallest possible volume are called _primitive_.

* For some crystals, all primitive unit cells are oblique, but larger cells with higher
  symmetry exist. In these cases, non-primitive unit cells are used because it is easier to
  describe the symmetry elements of the crystal with respect to the non-primitive unit cell.

  * Non-primitive unit cells contain additional lattice points. The additional lattice
    points reside on the faces or center of the unit cell. These non-primitive unit cells
    are called _centered_.

* The collection of possible lattice types for a crystal are the fourteen _Bravais lattices_
  consisting of

  * the six primitive unit cells and

  * the eight centered, non-primitive unit cells.

* __Lattice Centering Notation__

  * _P_: primitive lattice
  * _A_, _B_, _C_: base-centered lattice with additional lattice point on the A, B, or C
    face, respectively
  * _F_: face-centered lattice
  * _I_: body-centered lattice
  * _R_: rhombohedral-centered lattice (only for hexagonal crystal systems)

* __14 Bravais Lattices__

  * triclinic
    * _aP_: triclinic, primitive

  * monoclinic
    * _mP_: monoclinic, primitive
    * _mC_: monoclinic, base-centered

  * orthorhombic
    * _oP_: orthorhombic, primitive
    * _oA_: orthorhombic, base-centered
    * _oI_: orthorhombic, body-centered
    * _oF_: orthorhombic, face-centered

  * tetragonal
    * _tP_: tetragonal, primitive
    * _tI_: tetragonal, body-centered

  * hexagonal
    * _hP_: hexagonal, primitive
    * _hR_: hexagonal, rhomobohedral

  * cubic
    * _cP_: cubic, primitive
    * _cI_: cubic, body-centered
    * _cF_: cubic, face-centered

* Unit cells can be transformed to _standard reduced form_ where $a \le b \le c$ and
  $\alpha$, $\beta$, and $\gamma$, are all $\le 90^\circ$ or all $\ge 90^\circ$.
  * One algorithm for performing this transformation is the Delauney-reduction.

* The _Niggli-Matrix_ is a compact way to represent the _metric symmetry_ of the unit cell:

  $$
  \left[\begin{array}[ccc]
    a^2 & b^2 & c^2 \\
    bc \cos\alpha & ac \cos\beta & ab \cos\gamma \\
  \end{array}\right]
  $$

--------------------------------------------------------------------------------------------

## 2. Miscellaneous Notes

* Typical lattice constant lengths
  * Organic molecules: 3 to 40 angstroms
  * Inorganic molecules: 3 to 40 angstroms
  * Proteins: up to ~100 angstroms or more

--------------------------------------------------------------------------------------------

## 3. References

1. D. Sands. "Introduction to Crystallography" (1994).

2. W. Massa. "Crystal Structure Determination" (2016).

--------------------------------------------------------------------------------------------

[----------------------------------- INTERNAL LINKS -----------------------------------]: #

[#1]: #1-miscellaneous-notes

[#2]: #2-references

[----------------------------------- EXTERNAL LINKS -----------------------------------]: #
