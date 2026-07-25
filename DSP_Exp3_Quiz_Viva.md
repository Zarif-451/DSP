# CSE-224 DSP Lab – Experiment 3 Master Quiz & Viva

> **Experiment:** Signal Manipulation and Basic Operations on Discrete-Time Signals Using Python

---

# Part A – Theory

## Q1. What is signal manipulation?

**Answer:**

Signal manipulation is the process of modifying a signal without changing its fundamental meaning. Common operations include time shifting, time reversal, time scaling, amplitude scaling, and convolution. These operations are widely used in Digital Signal Processing (DSP). 

---

## Q2. What is time shifting?

**Answer:**

Time shifting moves a signal along the time axis without changing its shape or amplitude. A right shift is called **delay**, while a left shift is called **advance**.

### Formula

- Delay:

\[
y[n]=x[n-k]
\]

- Advance:

\[
y[n]=x[n+k]
\]

---

## Q3. What is time reversal (reflection)?

**Answer:**

Time reversal flips the signal about the vertical axis. Every sample at index \(n\) moves to index \(-n\). This operation is commonly used in convolution and correlation.

### Formula

\[
y[n]=x[-n]
\]

---

## Q4. What is time scaling?

**Answer:**

Time scaling changes the duration of a signal. Stretching expands the signal in time, while compression reduces its duration.

### Formula

Stretching:

\[
y[n]=x(n/a),\quad a>1
\]

Compression:

\[
y[n]=x(an),\quad a>1
\]

---

## Q5. What is amplitude scaling?

**Answer:**

Amplitude scaling changes only the magnitude of the signal while keeping the time axis unchanged.

### Formula

\[
y[n]=Ax[n]
\]

- \(A>1\): Amplification
- \(0<A<1\): Attenuation
- \(A<0\): Inversion

---

## Q6. What is convolution?

**Answer:**

Convolution combines two discrete-time signals to determine the output of an LTI system. It is one of the most important operations in DSP because it describes how systems respond to inputs.

### Formula

\[
y[n]=x[n]*h[n]
\]

---

# Part B – Differences

## Delay vs Advance

| Delay | Advance |
|-------|---------|
| Signal shifts right | Signal shifts left |
| Formula: `x[n-k]` | Formula: `x[n+k]` |
| Output occurs later | Output occurs earlier |

---

## Reflection vs Time Shifting

| Reflection | Time Shifting |
|------------|---------------|
| Flips the signal | Moves the signal |
| Formula: `x[-n]` | Formula: `x[n±k]` |
| Changes time direction | Keeps time direction unchanged |

---

## Stretching vs Compression

| Stretching | Compression |
|------------|-------------|
| Expands signal | Compresses signal |
| Signal becomes wider | Signal becomes narrower |
| `x(n/a)` | `x(an)` |

---

## Amplitude Scaling vs Time Scaling

| Amplitude Scaling | Time Scaling |
|-------------------|--------------|
| Changes amplitude | Changes time axis |
| Shape unchanged in time | Duration changes |
| Formula: `Ax[n]` | Formula: `x(an)` or `x(n/a)` |

---

## plot() vs stem()

| `plot()` | `stem()` |
|-----------|----------|
| Continuous signals | Discrete signals |
| Connects points | Draws stems |
| Smooth curve | Individual samples |

---

## np.arange() vs np.linspace()

| `np.arange()` | `np.linspace()` |
|---------------|-----------------|
| Uses step size | Uses number of points |
| Stop excluded | Endpoint included |

---

# Part C – Python Viva

### Why is `np.arange()` used?

To generate discrete time indices for the signal.

### Why is `np.linspace()` used?

To generate evenly spaced values over a specified interval, especially for stretching/compression visualization.

### Why is `plt.subplot()` used?

It divides one figure into multiple smaller graphs so different signal operations can be compared side by side.

### Why is `plt.stem()` used?

It represents discrete-time signals using vertical stems and markers.

### What does `plt.tight_layout()` do?

It automatically adjusts spacing between subplots so titles, labels, and axes do not overlap.

### What does `plt.figure(figsize=(12,12))` do?

It creates a new figure and sets its width and height in inches.

---

# Part D – Code Viva

### Why is `origin` used?

It sets the reference index (n = 0) for the discrete-time signal.

### Why is `time = np.arange(...)` created?

It generates the sample indices used on the x-axis.

### Why is `delay = 4` used?

To shift the signal four samples to the right.

### Why is `advance = 4` used?

To shift the signal four samples to the left.

### Why is `reflected_time = -time` used?

To reverse the signal in time.

### Why is `scale = 4` used?

To stretch the signal.

### Why is `scale = 0.25` used?

To compress the signal.

### Why is `scaled_signal = scale * signal` used?

To multiply every amplitude by the scaling factor.

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
9. What happens when A < 0?
10. Define convolution.
11. Why is convolution important?
12. What is an LTI system?
13. What is a kernel in convolution?
14. Why use `stem()` for discrete signals?
15. Why use `subplot()`?
16. Why use `tight_layout()`?
17. Difference between amplitude scaling and time scaling.
18. Difference between delay and reflection.
19. Explain `x[n-k]`.
20. Explain `x[-n]`.

---

# Part F – Observation Summary

| Operation | Mathematical Form | Effect |
|-----------|-------------------|--------|
| Delay | `x[n-k]` | Shift Right |
| Advance | `x[n+k]` | Shift Left |
| Reflection | `x[-n]` | Time Reversal |
| Stretching | `x(n/a)` | Signal Expansion |
| Compression | `x(an)` | Signal Compression |
| Amplitude Scaling | `Ax[n]` | Amplitude Change |
| Convolution | `x[n]*h[n]` | System Response |
