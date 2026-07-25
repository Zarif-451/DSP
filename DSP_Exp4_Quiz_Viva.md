# CSE-224 DSP Lab – Experiment 4 Master Quiz & Viva

> **Experiment:** Study and Implementation of Z-Transformation Using Python

---

# Part A – Theory

## Q1. What is the Z-Transform?

**Answer:**

The Z-Transform converts a discrete-time signal into its complex frequency-domain representation. It is widely used for analyzing discrete-time systems, digital filters, and DSP algorithms.

### General Formula

\[
X(z)=\sum_{n=-\infty}^{\infty}x[n]z^{-n}
\]

For causal signals,

\[
X(z)=\sum_{n=0}^{\infty}x[n]z^{-n}
\]

---

## Q2. Why is the Z-Transform important?

**Answer:**

It simplifies the analysis of discrete-time systems, converts difference equations into algebraic equations, and is widely used in digital filter design and control systems.

---

## Q3. What is a causal signal?

**Answer:**

A causal signal exists only for \(n \ge 0\). Most practical DSP systems are causal because they do not depend on future values.

---

## Q4. What is the inverse Z-Transform?

**Answer:**

The inverse Z-Transform converts a frequency-domain expression \(X(z)\) back into the original discrete-time signal \(x[n]\).

---

# Part B – Standard Z-Transforms

| **Signal** | **Mathematical Form** | **Z-Transform** |
|------------|-----------------------|-----------------|
| Unit Step | \(u[n]\) | \(\frac{z}{z-1}\) |
| Exponential | \(a^n u[n]\) | \(\frac{z}{z-a}\) |
| Ramp | \(nu[n]\) | \(\frac{z}{(z-1)^2}\) |
| Delayed Impulse | \(\delta[n-k]\) | \(z^{-k}\) |

---

# Part C – Differences

## Z-Transform vs Fourier Transform

| **Z-Transform** | **Fourier Transform** |
|-----------------|-----------------------|
| Uses complex variable \(z\) | Uses frequency \(\omega\) |
| More general | Special case of Z-transform |
| Used for stability analysis | Used for frequency analysis |

---

## Forward Z-Transform vs Inverse Z-Transform

| **Forward** | **Inverse** |
|-------------|-------------|
| Time → Z-domain | Z-domain → Time |
| Computes \(X(z)\) | Computes \(x[n]\) |
| Analysis | Signal reconstruction |

---

## Unit Step vs Ramp

| **Unit Step** | **Ramp** |
|---------------|----------|
| Constant amplitude | Linearly increasing |
| \(u[n]\) | \(nu[n]\) |
| \(z/(z-1)\) | \(z/(z-1)^2\) |

---

## Unit Step vs Exponential

| **Unit Step** | **Exponential** |
|---------------|-----------------|
| Constant value | Changes exponentially |
| \(u[n]\) | \(a^n u[n]\) |
| No parameter \(a\) | Depends on \(a\) |

---

# Part D – Python Viva

## Why is SymPy used?

SymPy performs symbolic mathematics such as summation, simplification, and symbolic Z-Transforms.

## What does `sp.symbols()` do?

Creates symbolic mathematical variables like `n`, `z`, and `a`.

## What does `sp.summation()` do?

Computes symbolic summations according to the mathematical formula.

## What is `sp.oo`?

Represents mathematical infinity (\(\infty\)).

## Why is `z**(-n)` used?

Because the definition of the Z-Transform contains the factor \(z^{-n}\).

## Why use `sp.pprint()`?

It displays mathematical expressions in a readable textbook-style format.

---

# Part E – Code Viva

### Why do we write

```python
n, z = sp.symbols('n z')
```

To declare symbolic variables used in mathematical expressions.

### Why is

```python
X = sp.summation(z**(-n), (n,0,sp.oo))
```

used?

It directly implements the Z-Transform formula for the unit-step signal.

### Why does the summation start from 0?

Because the signal is causal (\(n \ge 0\)).

### Why is `inverse_z_transform()` unavailable in some versions?

Older SymPy versions do not implement this function.

---

# Part F – Formula-Based Viva

## General Z-Transform

\[
X(z)=\sum_{n=-\infty}^{\infty}x[n]z^{-n}
\]

## Causal Z-Transform

\[
X(z)=\sum_{n=0}^{\infty}x[n]z^{-n}
\]

## Unit Step

Given:

\[
x[n]=u[n]
\]

Expected:

\[
X(z)=\frac{z}{z-1}
\]

---

## Exponential

Given:

\[
x[n]=a^n u[n]
\]

Expected:

\[
X(z)=\frac{z}{z-a}
\]

---

## Ramp

Given:

\[
x[n]=nu[n]
\]

Expected:

\[
X(z)=\frac{z}{(z-1)^2}
\]

---

## Inverse Z-Transform

Given:

\[
X(z)=\frac{z}{z-a}
\]

Expected:

\[
x[n]=a^n u[n]
\]

---

# Part G – Frequently Asked Viva Questions

1. Define Z-Transform.
2. Why is Z-Transform used?
3. State the general Z-Transform formula.
4. What is a causal signal?
5. What is the inverse Z-Transform?
6. What is SymPy?
7. Why use symbolic computation?
8. What does `sp.symbols()` do?
9. What does `sp.summation()` do?
10. What is `sp.oo`?
11. Why use `z^{-n}`?
12. Why does the summation start from zero?
13. State the Z-Transform of a unit-step signal.
14. State the Z-Transform of an exponential signal.
15. State the Z-Transform of a ramp signal.
16. What is the Z-Transform of a delayed impulse?
17. Difference between forward and inverse Z-Transform.
18. Difference between Z-Transform and Fourier Transform.
19. Why use `sp.pprint()`?
20. Why might `inverse_z_transform()` not work in older SymPy versions?
