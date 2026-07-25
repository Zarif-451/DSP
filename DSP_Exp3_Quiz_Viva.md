# CSE-224 DSP Lab – Experiment 3 Master Quiz & Viva

> **Experiment:** Signal Manipulation and Basic Operations on Discrete-Time Signals Using Python

---

# Part A – Theory

## Q1. What is Signal Manipulation?

**Answer:**

Signal manipulation is the process of modifying a signal without changing its original information. Common operations include time shifting, time reversal, time scaling, amplitude scaling, and convolution. These operations are fundamental in Digital Signal Processing (DSP).

---

## Q2. What is Time Shifting?

**Answer:**

Time shifting moves a signal along the time axis without changing its shape or amplitude. A shift to the right is called **delay**, while a shift to the left is called **advance**.

### Delay

$$
y[n]=x[n-k]
$$

### Advance

$$
y[n]=x[n+k]
$$

---

## Q3. What is Time Reversal (Reflection)?

**Answer:**

Time reversal flips a signal about the vertical axis. Every sample at index `n` moves to `-n`. Reflection is widely used in convolution and correlation.

### Formula

$$
y[n]=x[-n]
$$

---

## Q4. What is Time Scaling?

**Answer:**

Time scaling changes the duration of a signal. Stretching makes the signal wider, while compression makes it narrower.

### Stretching

$$
y[n]=x(n/a),\qquad a>1
$$

### Compression

$$
y[n]=x(an),\qquad a>1
$$

---

## Q5. What is Amplitude Scaling?

**Answer:**

Amplitude scaling changes only the magnitude of a signal while keeping the time axis unchanged.

### Formula

$$
y[n]=A\,x[n]
$$

- `A > 1` → Amplification
- `0 < A < 1` → Attenuation
- `A < 0` → Inversion

---

## Q6. What is Convolution?

**Answer:**

Convolution combines two discrete-time signals to determine the output of an LTI (Linear Time-Invariant) system. It describes how a system responds to an input signal.

### Formula

$$
y[n]=x[n]*h[n]
$$

---

# Part B – Differences

## Delay vs Advance

| **Delay** | **Advance** |
|-----------|-------------|
| Signal shifts right | Signal shifts left |
| Formula: `x[n-k]` | Formula: `x[n+k]` |
| Output occurs later | Output occurs earlier |

---

## Reflection vs Time Shifting

| **Reflection** | **Time Shifting** |
|----------------|-------------------|
| Flips the signal | Moves the signal |
| Formula: `x[-n]` | Formula: `x[n±k]` |
| Changes time direction | Time direction remains the same |

---

## Stretching vs Compression

| **Stretching** | **Compression** |
|----------------|-----------------|
| Expands the signal | Compresses the signal |
| Signal becomes wider | Signal becomes narrower |
| `x(n/a)` | `x(an)` |

---

## Amplitude Scaling vs Time Scaling

| **Amplitude Scaling** | **Time Scaling** |
|-----------------------|------------------|
| Changes amplitude | Changes time axis |
| Time remains unchanged | Duration changes |
| Formula: `A*x[n]` | Formula: `x(an)` or `x(n/a)` |

---

## `plt.plot()` vs `plt.stem()`

| **`plt.plot()`** | **`plt.stem()`** |
|------------------|------------------|
| Used for continuous signals | Used for discrete signals |
| Connects adjacent points | Draws stems and markers |
| Produces smooth curves | Shows individual samples |

---

## `np.arange()` vs `np.linspace()`

| **`np.arange()`** | **`np.linspace()`** |
|-------------------|---------------------|
| Uses step size | Uses number of points |
| Stop value excluded | Endpoint included by default |

---

# Part C – Python Viva

## Why is `np.arange()` used?

It generates discrete sample indices or time values using a fixed step size.

## Why is `np.linspace()` used?

It generates a specified number of evenly spaced values over an interval.

## Why is `plt.subplot()` used?

It divides a figure into multiple plots so different signal operations can be compared together.

## Why is `plt.stem()` used?

It represents discrete-time signals using stems and markers instead of connected lines.

## What does `plt.tight_layout()` do?

It automatically adjusts spacing between subplots to prevent overlapping titles and labels.

## What does `plt.figure(figsize=(12,12))` do?

It creates a new figure and specifies its width and height in inches.

---

# Part D – Code Viva

## Why is `origin` used?

It specifies the reference index corresponding to `n = 0`.

## Why is `time = np.arange(...)` created?

It generates the sample indices used on the horizontal axis.

## Why is `delay = 4` used?

To delay the signal by four samples.

## Why is `advance = 4` used?

To advance the signal by four samples.

## Why is `reflected_time = -time` used?

To perform time reversal (reflection).

## Why is `scale = 4` used?

To stretch the signal in time.

## Why is `scale = 0.25` used?

To compress the signal in time.

## Why is `scaled_signal = scale * signal` used?

To scale the signal amplitude.

---

# Part E – Frequently Asked Viva Questions

1. What is signal manipulation?
2. Define time shifting.
3. Difference between delay and advance.
4. What is reflection?
5. Why is reflection used in convolution?
6. Define time scaling.
7. Difference between stretching and compression.
8. Define amplitude scaling.
9. What happens when `A < 0`?
10. Define convolution.
11. Why is convolution important?
12. What is an LTI system?
13. What is a kernel in convolution?
14. Why use `plt.stem()`?
15. Why use `plt.subplot()`?
16. Why use `plt.tight_layout()`?
17. Difference between amplitude scaling and time scaling.
18. Difference between delay and reflection.
19. Explain `x[n-k]`.
20. Explain `x[-n]`.

---

# Part F – Observation Summary

| **Operation** | **Mathematical Form** | **Effect** |
|---------------|-----------------------|------------|
| Delay | `x[n-k]` | Shift Right |
| Advance | `x[n+k]` | Shift Left |
| Reflection | `x[-n]` | Time Reversal |
| Stretching | `x(n/a)` | Signal Expansion |
| Compression | `x(an)` | Signal Compression |
| Amplitude Scaling | `A*x[n]` | Amplitude Change |
| Convolution | `x[n] * h[n]` | System Response |
