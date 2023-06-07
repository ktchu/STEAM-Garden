Computational Chemistry Notes
=============================

_Author(s)_: Kevin Chu `<kevin@velexi.com>`

_Last Updated_: 2023-02-03

--------------------------------------------------------------------------------------------

References
----------
* E.G. Lewars. "Computational Chemistry" (2016).

--------------------------------------------------------------------------------------------
### Notation

* $\newcommand{\mat}[1]{\mathbf{#1}}$
  A matrix: $\mat{A}$

* A vector: $\vec{v}$

--------------------------------------------------------------------------------------------

## Foundations

### Potential Energy Surfaces (PES)

* _Potential energy surfaces_ form the foundation of all structure calculations.

* Potential energy surfaces can be obtained from ab initio or DFT calculations.

--------------------------------------------------------------------------------------------

## Molecular Mechanics

* In _molecular mechanics_, the electrons are completely ignored.

### Forcefields

* The _forcefield_ is the potential energy of a molecule as a function of its geometric
  conformation (e.g., bond lengths, bond angles, etc.).

* Forcefields can be fit from experimental data, ab initio calculations, or DFT
  calculations.

### Common Uses of Molecular Mechanics

* Obtaining reasonable input geometries for more accurate computational chemistry
  calculations (e.g., ab initio, semiempirical, DFT).

* Calculating accurate geometries (and possibly energies) for small- to medium-sized
  molecules.

* Calculating geometries and energies for very large molecules (e.g., polymeric
  biomolecules)

* To provide the potential energy function that drives molecular motion in molecular
  dynamics or Monte Carlo simulations.

* To provide guidance on the feasibility of reactions in organic synthesis.

### Limitations of Molecular Mechanics

* TODO

--------------------------------------------------------------------------------------------

## Basic Quantum Mechanics

### Simple Huckel Method (SHM)

* __SHM Assumptions__

  * Molecular orbitals (i.e., wavefunctions for molecules) can be approximated by
    _linear combinations of atomic orbitals_ (LCAO).

  * The overlap between atomic orbitals is 0.

* In SHM, approximate energies and molecular orbital wavefunctions are computed by
  minimizing

  $$
  E = \frac{\int (\psi \hat{H} \psi) dv}{\int (\psi^2) dv}
  $$

  over the coefficients in the LCAO. The resulting matrix equation is a generalized
  eigenvalue equation of the form

  $$
  \left( \mat{H} - \mat{S} E \right) \vec{c} = \vec{0}
  $$

  where $E$ is the energy, $\vec{c}$ is the vector of LCAO coefficients, $\mat{H}$ is the
  Fock matrix with elements of the form

  $$
  H_{ij} = \int (\psi_i \hat{H} \psi_j) dv,
  $$

  and $S$ is the overlap matrix with elements of the form

  $$
  S_{ij} = \int (\psi_i \psi_j) dv.
  $$

* In SHM, $S_{ij}$ is assumed to be a Kronecker delta function - $S_{ij} = \delta_{ij}$,
  so $\mat{S} = \mat{I}$ and the equation for the energy $E$ and the LCAO coefficients
  $\vec{c}$ reduces to an ordinary eigenvalue equation:

  $$
  \mat{H} \vec{c} = E \vec{c}.
  $$


* Lewars - p. 150.

--------------------------------------------------------------------------------------------

## Acronyms

* DFT: Density Functional Theory

* LCAO: Linear Combination of Atomic Orbitals

* MO: Molecular Orbitals

* PES: Potential Energy Surface

* SHM: Simple Huckel Method

--------------------------------------------------------------------------------------------
