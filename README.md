# The Harmonic Transform

**A Recurrence-Defined Polynomial Basis**

**Author:** Carolina Johnson (CJ)  
**Date:** October 2026  
**DOI:** [10.5281/zenodo.18249048](https://doi.org/10.5281/zenodo.18249048)  
**ORCID:** [0009-0002-8819-3347](https://orcid.org/0009-0002-8819-3347)

---

## Overview

The Harmonic Transform (HT) defines a polynomial basis through a recurrence relation parameterized by a real sequence. It provides a coordinate map for representing polynomials within a specific function space, with the basis generated directly from the recurrence rather than from expanded polynomial coefficients.

The defining recurrence is:

```text
H₀(x) = 0
H₁(x) = x
Hₖ₊₁(x) = 2x·Hₖ(x) − Φₖ·Hₖ₋₁(x)
```

For every real parameter sequence, the polynomials H₁, …, H_K span the same space V_K: all polynomials of degree at most K that vanish at the origin. Changing the sequence changes the basis coordinates, but not the polynomial space itself.

The paper establishes the algebraic structure of this basis, its least-squares reconstruction properties, its relationship to orthogonal polynomials and Gaussian quadrature, and the numerical conditions governing its use.

---

## Key Results

- **Recurrence-Defined Basis:** Establishes the polynomial basis and its explicit coefficient structure directly from the recurrence.
- **Invariant Polynomial Space:** Proves that every real parameter sequence generates a basis for the same space V_K.
- **Coordinate Independence of Reconstruction:** Shows that, on a grid where the basis matrix has full column rank, the least-squares reconstruction is independent of the parameter sequence, even though the coordinates and conditioning may differ.
- **Leakage-Free Reconstruction:** Establishes exact recovery for signals in V_K, including zero coefficients on added basis functions when the extended fit satisfies the required rank condition.
- **Orthogonality and Quadrature:** Connects positive recurrence coefficients to orthogonal polynomial systems, explicit inner products, Jacobi matrices, and Gaussian quadrature.
- **Numerical Analysis:** Examines rank, condition numbers, solver precision, and the distinction between exact mathematical results and finite-precision computation.
- **Full Polynomial Space:** Shows that adjoining the constant function extends the basis from V_K to the complete polynomial space P_K.

---

## The Harmonic Basis

The parameter sequence determines the recurrence and therefore the coordinates used to represent a polynomial. The underlying space remains unchanged.

For the constant sequence Φₖ = 1, the basis has the closed form

```text
Hₖ(x) = x·Uₖ₋₁(x),
```

where Uₖ₋₁ is the Chebyshev polynomial of the second kind.

This case provides the harmonic angular representation studied in the paper. For other parameter sequences, the recurrence continues to define the basis without requiring the same angular form.

The term *harmonic* refers to the integer-multiple angular structure of the Φₖ = 1 case.

---

## Least-Squares Reconstruction

For sampled data, the basis polynomials form a matrix whose columns span the sampled values of V_K. When that matrix has full column rank, least-squares reconstruction is the orthogonal projection onto this space.

Because every admissible parameter sequence spans the same space, the projection is invariant under changes of basis. The coordinate vector changes, but the reconstructed signal does not.

The distinction between the represented space and its coordinates is central to the paper's analysis of reconstruction, leakage, and numerical conditioning.

The representable polynomial space is constrained by the value at the origin. For a signal on a general interval, normalization maps the interval midpoint to the origin. Adjoining the constant function removes this restriction and recovers the full degree-K polynomial space.

---

## Repository Contents

| File | Description |
|---|---|
| `README.md` | Overview of the Harmonic Transform and its mathematical results |
| `Harmonic Transform.pdf` | Full research paper |

---

## Citation

```text
Johnson, C. (2026). The Harmonic Transform: A Recurrence-Defined
Polynomial Basis. SemanticDrift.
https://doi.org/10.5281/zenodo.18249048
```

---

## License

© 2026 Carolina Johnson (CJ)

Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0). Attribution required.

https://creativecommons.org/licenses/by/4.0/
