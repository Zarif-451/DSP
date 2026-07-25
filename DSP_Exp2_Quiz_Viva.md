# CSE-224 DSP Lab – Experiment 2 Master Quiz & Viva

> **Topic:** Sampling of Continuous-Time Signals

---

# Part A – Theory

## Q1. What is sampling?

**Answer:**

Sampling is the process of converting a continuous-time (analog) signal into a discrete-time signal by measuring its amplitude at regular intervals. The sampled signal can then be processed by a computer.

---

## Q2. Why is sampling required?

**Answer:**

Computers cannot directly process analog signals because they are continuous. Sampling converts the analog signal into digital data so it can be stored, analyzed, and transmitted.

---

## Q3. What is a continuous-time signal?

**Answer:**

A continuous-time signal exists at every instant of time and is represented as x(t). Examples include speech, ECG, voltage, and temperature signals.

---

## Q4. What is a discrete-time signal?

**Answer:**

A discrete-time signal exists only at specific sampling instants and is represented as x[n]. It is obtained after sampling a continuous signal.

---

## Q5. What is a sample?

**Answer:**

A sample is a single measured value of a signal taken at a particular instant of time.

---

## Q6. What is sampling frequency?

**Answer:**

Sampling frequency (fs) is the number of samples taken from a signal in one second. Its unit is Hertz (Hz).

---

## Q7. What is signal frequency?

**Answer:**

Signal frequency (f_signal) is the number of complete cycles the signal completes in one second.

---

## Q8. What is sampling period?

**Answer:**

Sampling period is the time between two consecutive samples.

$$
T_s=\frac{1}{f_s}
$$

---

## Q9. State the Nyquist Sampling Theorem.

**Answer:**

The Nyquist theorem states that the sampling frequency must be at least twice the signal frequency.

$$
f_s \ge 2f_{signal}
$$

This prevents aliasing.

---

## Q10. What is aliasing?

**Answer:**

Aliasing occurs when a signal is sampled below the Nyquist rate, causing the reconstructed signal to appear distorted or as a different frequency.

---

# Part B – Differences

## Analog Signal vs Digital Signal

| Analog Signal | Digital Signal |
|---|---|
| Continuous | Discrete |
| x(t) | x[n] |
| Infinite values | Sampled values |
| More noise sensitive | Less noise sensitive |

---

## Signal Frequency vs Sampling Frequency

| Signal Frequency | Sampling Frequency |
|---|---|
| Number of cycles/sec | Number of samples/sec |
| Property of signal | Property of sampling |
| Symbol: f_signal | Symbol: fs |

---

## Continuous Signal vs Sampled Signal

| Continuous | Sampled |
|---|---|
| plot() | stem() |
| Smooth | Discrete |
| Infinite instants | Sample instants only |

---

## plot() vs stem()

| plot() | stem() |
|---|---|
| Continuous signals | Discrete signals |
| Connected points | Vertical stems |
| Smooth graph | Sample graph |

---

## plot() vs scatter()

| plot() | scatter() |
|---|---|
| Connects points | Only markers |
| Continuous graph | Displays samples |

---

## arange() vs linspace()

| arange() | linspace() |
|---|---|
| Uses step size | Uses number of points |
| Stop excluded | Endpoint included by default |

---

# Part C – Python Viva

## Why is NumPy used?

Used for arrays, mathematical operations and signal generation.

## Why is Matplotlib used?

Used for plotting and visualizing signals.

## What does np.arange() do?

Creates equally spaced values using a fixed step size.

## What does np.sin() do?

Calculates sine values for every element.

## What does plt.figure() do?

Creates a new plotting canvas.

## What does figsize do?

Controls figure width and height.

## What does plt.plot() do?

Plots continuous signals.

## What does plt.scatter() do?

Plots individual points without joining them.

## What does plt.stem() do?

Displays sampled (discrete) signals using stems.

## What does plt.grid() do?

Displays grid lines.

## What does plt.legend() do?

Displays labels assigned to graphs.

## What does plt.show() do?

Displays the figure.

---

# Part D – Code Viva

## Why do we use

```python
signal=np.sin(2*np.pi*f_signal*t)
```

Because it is the mathematical equation of a sine wave.

---

## Why is t used?

It contains the time values where the signal is evaluated.

---

## Why is t_sampled used?

It contains the sampled time instants according to the sampling frequency.

---

## Why does fs change inside the loop?

The experiment compares different sampling frequencies automatically.

---

## Why use

```python
for fs in sampling_rates:
```

To avoid writing the same code multiple times.

---

## Why use

```python
1/fs
```

Because the sampling period is

$$
T_s=\frac1{f_s}
$$

---

## Why use plot() before sampling?

Because the original signal is continuous.

---

## Why use stem() after sampling?

Because sampled signals are discrete.

---

## Why use scatter()?

To show only sample locations without connecting them.

---

# Part E – Numerical Questions

## If

f_signal = 10 Hz

Find the minimum sampling frequency.

Answer:

$$
f_s\ge2\times10=20Hz
$$

---

## If

fs=50Hz

Find the sampling period.

$$
T_s=\frac1{50}=0.02s
$$

---

# Part F – Frequently Asked Viva Questions

1. What is sampling?
2. Why is sampling necessary?
3. Define signal frequency.
4. Define sampling frequency.
5. Define sampling period.
6. State Nyquist theorem.
7. What is aliasing?
8. Why is plot() used?
9. Why is stem() used?
10. Why is scatter() used?
11. Difference between plot() and stem().
12. Difference between signal frequency and sampling frequency.
13. Difference between arange() and linspace().
14. Explain the sine wave equation.
15. Why is 2*pi used?
16. Why are labels added?
17. Why are legends added?
18. Why is grid used?
19. Why does a high-frequency graph appear dense?
20. How can aliasing be avoided?
