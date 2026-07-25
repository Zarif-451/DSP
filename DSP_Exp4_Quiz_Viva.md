# CSE-224 DSP Lab – Experiment 4 Master Quiz & Viva

> **Experiment:** Study and Implementation of Z-Transformation Using Python

---

# Part A – Theory

## Q1. What is the Z-Transform?

**Answer:**

The Z-Transform converts a discrete-time signal into its complex frequency-domain representation. It is used to analyze discrete-time systems, digital filters, and DSP algorithms by transforming signals from the time domain into the Z-domain.

### General Z-Transform

$$
X(z)=\sum_{n=-\infty}^{\infty}x[n]z^{-n}
$$

### For Causal Signals

$$
X(z)=\sum_{n=0}^{\infty}x[n]z^{-n}
$$

---

## Q2. Why is the Z-Transform important?

**Answer:**

- Converts difference equations into algebraic equations.
- Simplifies analysis of discrete-time systems.
- Used in digital filter design and control systems.
- Helps determine stability and system behavior.

---

## Q3. What is a causal signal?

**Answer:**

A causal signal exists only for `n ≥ 0`. It does not depend on future values and is therefore physically realizable.

---

## Q4. What is the inverse Z-Transform?

**Answer:**

The inverse Z-Transform converts a Z-domain expression back into its original discrete-time signal.

---

# Part B – Standard Z-Transforms

| **Signal** | **Mathematical Form** | **Z-Transform** |
|------------|-----------------------|-----------------|
| Unit Step | `u[n]` | `z/(z-1)` |
| Exponential | `a^n u[n]` | `z/(z-a)` |
| Ramp | `n u[n]` | `z/(z-1)^2` |
| Delayed Impulse | `δ[n-k]` | `z^-k` |

---

# Part C – Differences

## Z-Transform vs Fourier Transform

| **Z-Transform** | **Fourier Transform** |
|-----------------|-----------------------|
| Uses complex variable `z` | Uses frequency `ω` |
| More general transform | Special case of Z-Transform |
| Used for stability analysis | Used for frequency analysis |
| Includes ROC | No ROC |

---

## Forward Z-Transform vs Inverse Z-Transform

| **Forward** | **Inverse** |
|-------------|-------------|
| Time Domain → Z Domain | Z Domain → Time Domain |
| Computes `X(z)` | Computes `x[n]` |
| Used for analysis | Used for reconstruction |

---

## Unit Step vs Ramp

| **Unit Step** | **Ramp** |
|---------------|----------|
| Constant value | Linearly increasing |
| `u[n]` | `n u[n]` |
| `z/(z-1)` | `z/(z-1)^2` |

---

## Unit Step vs Exponential

| **Unit Step** | **Exponential** |
|---------------|-----------------|
| Constant amplitude | Exponential growth/decay |
| `u[n]` | `a^n u[n]` |
| No parameter | Depends on `a` |

---

# Part D – Python Viva

## Why is SymPy used?

SymPy performs symbolic mathematics, including symbolic summation and algebraic simplification required for Z-Transforms.

## What does `sp.symbols()` do?

Creates symbolic variables such as `n`, `z`, and `a`.

## What does `sp.summation()` do?

Evaluates symbolic summations according to the Z-Transform definition.

## What is `sp.oo`?

Represents mathematical infinity.

## Why use `z**(-n)`?

Because the Z-Transform definition contains the term `z^{-n}`.

## Why use `sp.pprint()`?

It prints mathematical expressions in a readable textbook-style format.

---

# Part E – Code Viva

### Why write?

```python
n, z = sp.symbols("n z")
```

It declares symbolic variables used in symbolic mathematics.

### Why write?

```python
X = sp.summation(z**(-n), (n, 0, sp.oo))
```

It implements the Z-Transform of the unit-step signal directly from its mathematical definition.

### Why does the summation start at `0`?

Because the signal is causal (`n ≥ 0`).

### Why may `inverse_z_transform()` fail?

Some older SymPy versions do not implement this function.

---

# Part F – Formula Viva

## General Formula

$$
X(z)=\sum_{n=-\infty}^{\infty}x[n]z^{-n}
$$

## Causal Formula

$$
X(z)=\sum_{n=0}^{\infty}x[n]z^{-n}
$$

## Unit Step

Given:

`x[n] = u[n]`

Expected:

`X(z) = z/(z-1)`

## Exponential

Given:

`x[n] = a^n u[n]`

Expected:

`X(z) = z/(z-a)`

## Ramp

Given:

`x[n] = n u[n]`

Expected:

`X(z) = z/(z-1)^2`

## Delayed Impulse

Given:

`x[n] = δ[n-k]`

Expected:

`X(z) = z^-k`

---

# Part G – Frequently Asked Viva Questions

1. Define the Z-Transform.
2. Why is the Z-Transform used?
3. State the general Z-Transform formula.
4. What is a causal signal?
5. What is an inverse Z-Transform?
6. Why is SymPy used?
7. What does `sp.symbols()` do?
8. What does `sp.summation()` do?
9. What is `sp.oo`?
10. Why is `z**(-n)` used?
11. State the Z-Transform of a unit-step signal.
12. State the Z-Transform of an exponential signal.
13. State the Z-Transform of a ramp signal.
14. State the Z-Transform of a delayed impulse.
15. Difference between Z-Transform and Fourier Transform.
16. Difference between Forward and Inverse Z-Transform.
17. Why does the summation begin at zero for causal signals?
18. What is ROC (Region of Convergence)?
19. Why is the Z-Transform useful in DSP?
20. Where is the Z-Transform used in real life?
