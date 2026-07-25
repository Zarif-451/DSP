# CSE-224 DSP Lab Master Quiz & Viva (Experiment 1)

> Covers theory, Python, plotting, signal operations, and common viva
> questions.

------------------------------------------------------------------------

# Part A -- Theory

## Q1. What is a signal?

**Answer:**\
A signal is a function that carries information about a physical
phenomenon. In DSP, signals represent quantities such as sound,
temperature, voltage, ECG, or images. Signals can be processed,
analyzed, and transformed to extract useful information.

## Q2. What is an analog signal?

**Answer:**\
An analog signal is continuous in both time and amplitude. It is
represented as **x(t)**, where **t** is continuous time. Real-world
electrical and audio signals are analog.

## Q3. What is a digital signal?

**Answer:**\
A digital signal is represented using discrete samples. It exists only
at specific sampling instants and is denoted by **x\[n\]**. Computers
process digital signals because they are easier to store and manipulate.

## Q4. What is sampling?

**Answer:**\
Sampling is the process of converting a continuous-time signal into a
discrete-time signal by measuring its value at regular time intervals.

## Q5. What is amplitude?

**Answer:**\
Amplitude is the magnitude or value of a signal at a particular instant.
For a normalized sine wave, the amplitude varies between **-1** and
**+1**.

## Q6. What is frequency?

**Answer:**\
Frequency is the number of complete cycles a signal completes in one
second. Its SI unit is Hertz (Hz).

## Q7. What is the period?

**Answer:**\
The period is the time required to complete one full cycle. It is
related to frequency by

$$
T=\frac{1}{f}
$$

------------------------------------------------------------------------

# Part B -- Differences (Very Common Viva)

## Analog Signal vs Digital Signal

  **Analog Signal**           **Digital Signal**
  --------------------------- --------------------------------
  Continuous in time          Discrete in time
  Represented as `x(t)`       Represented as `x[n]`
  Infinite number of values   Finite sampled values
  More sensitive to noise     Less sensitive to noise
  Harder to process           Easier to process by computers

------------------------------------------------------------------------

## x(t) vs x\[n\]

  **x(t)**                   **x\[n\]**
  -------------------------- ---------------------------------
  Continuous-time signal     Discrete-time signal
  Uses continuous time `t`   Uses sample index `n`
  Exists at every instant    Exists only at sampled instants
  Analog representation      Digital representation

------------------------------------------------------------------------

## Sample Point vs Sample Value

  -----------------------------------------------------------------------
  **Sample Point**                    **Sample Value**
  ----------------------------------- -----------------------------------
  Time/index where sampling occurs    Amplitude at that sampling instant

  Represents **when** the signal is   Represents **what value** the
  measured                            signal has

  Stored in the `time` array          Stored in the `signal` (or
                                      amplitude) array
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## Signal Frequency vs Sampling Frequency

  -----------------------------------------------------------------------
  **Signal Frequency (`f_signal`)**     **Sampling Frequency (`f_s`)**
  ------------------------------------- ---------------------------------
  Number of cycles per second           Number of samples taken per
                                        second

  Property of the signal                Property of the sampling process

  Determines how fast the wave          Determines how often the wave is
  oscillates                            measured

  Used inside `sin(2πft)`               Used to create the time vector
                                        (`1/f_s`)

  Unit: Hertz (Hz)                      Unit: Hertz (Hz)
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## `np.arange()` vs `np.linspace()`

  -----------------------------------------------------------------------
  **np.arange()**                   **np.linspace()**
  --------------------------------- -------------------------------------
  Uses a fixed step size            Uses a fixed number of points

  Stop value is usually excluded    Endpoint is included by default

  Good when spacing is known        Good when total samples are known

  Syntax:                           Syntax:
  `np.arange(start, stop, step)`    `np.linspace(start, stop, num)`
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## `plt.plot()` vs `plt.stem()`

  **plt.plot()**                       **plt.stem()**
  ------------------------------------ -----------------------------------
  Used for continuous signals          Used for discrete signals
  Connects adjacent points             Draws vertical stems with markers
  Produces a smooth curve              Shows individual samples clearly
  Best for analog-like visualization   Best for sampled signals

------------------------------------------------------------------------

## `plt.plot()` vs `plt.scatter()`

  -----------------------------------------------------------------------
  **plt.plot()**                   **plt.scatter()**
  -------------------------------- --------------------------------------
  Connects data points             Displays only individual points

  Suitable for continuous signals  Suitable for showing sample locations

  Creates a line graph             Creates a scatter plot
  -----------------------------------------------------------------------


------------------------------------------------------------------------

## Frequency vs Sampling Frequency

  Signal Frequency              Sampling Frequency
  ----------------------------- ----------------------------------
  Number of cycles per second   Number of samples per second
  Property of the signal        Property of the sampling process
  Used inside sin()             Used to create the time vector
  Symbol: f or f_signal         Symbol: fs

------------------------------------------------------------------------

## np.arange() vs np.linspace()

  np.arange()                   np.linspace()
  ----------------------------- -----------------------------------
  Uses step size                Uses number of points
  Stop value usually excluded   Endpoint included by default
  Good when spacing is known    Good when total samples are known

------------------------------------------------------------------------

## plt.plot() vs plt.stem()

  plot()               stem()
  -------------------- ----------------------
  Continuous signals   Discrete signals
  Connects points      Draws vertical stems
  Smooth curve         Individual samples

------------------------------------------------------------------------

## plt.plot() vs plt.scatter()

  plot()                  scatter()
  ----------------------- -------------------
  Connects points         Only plots points
  Continuous appearance   Separate markers

------------------------------------------------------------------------

# Part C -- Python & Libraries

## Why is NumPy used?

NumPy provides efficient numerical computation, arrays, mathematical
functions, and signal generation. Functions like `np.sin()`, `np.cos()`,
`np.arange()`, and `np.linspace()` are heavily used in DSP.

## Why is Matplotlib used?

Matplotlib is used to visualize signals. It provides functions for
plotting, labeling axes, adding titles, legends, grids, and displaying
graphs.

## Explain np.arange(start, stop, step)

Generates equally spaced values beginning from `start` and increasing by
`step` until just before `stop`.

## Explain np.linspace(start, stop, num)

Generates exactly `num` equally spaced values between `start` and
`stop`. By default, the endpoint is included.

## What does np.sin() do?

Computes the sine of every input value. When given an array, it returns
an array of sine values.

------------------------------------------------------------------------

# Part D -- Matplotlib Functions

## What does plt.figure() do?

Creates a new figure (canvas) where graphs will be drawn.

## What does figsize do?

Controls the width and height of the figure in inches.

## What does plt.title() do?

Adds a title to the graph.

## What does plt.xlabel() do?

Adds a label to the x-axis.

## What does plt.ylabel() do?

Adds a label to the y-axis.

## What does plt.grid(True) do?

Displays grid lines to make graphs easier to read.

## What does plt.axhline(y=0) do?

Draws a horizontal reference line at y = 0.

## What does plt.axvline(x=0) do?

Draws a vertical reference line at x = 0.

## What does plt.legend() do?

Displays the labels assigned to plotted signals.

## What does label= do?

Assigns a name to a graph. It becomes visible only after calling
`plt.legend()`.

## What does color= do?

Changes the color of the plotted graph.

## What does plt.tight_layout() do?

Automatically adjusts spacing between subplots so titles and labels do
not overlap.

## What does plt.show() do?

Displays all prepared graphs.

------------------------------------------------------------------------

# Part E -- Code Viva

## Why do we use 2\*np.pi in the sine equation?

One complete cycle equals (2`\pi`{=tex}) radians. Therefore the standard
sine equation is

$$
x(t)=\sin(2\pi ft)
$$

## Why are both time and amplitude required?

Time specifies where the signal is measured, while amplitude specifies
the signal value at that instant.

## Why is the sine wave smooth?

Because many closely spaced samples are connected using `plot()`.

## What happens if the step size decreases?

More sample points are generated, producing a smoother graph but
increasing computation.

## Why print arrays?

To verify generated sample points and amplitudes.

------------------------------------------------------------------------

# Part F -- Mathematical Questions

## What is the equation of a sine wave?

$$
x(t)=\sin(2\pi ft)
$$

## What is the range of a sine wave?

The amplitude ranges from **-1 to +1**.

## What is the period of sin(t)?

$$
2\pi
$$

------------------------------------------------------------------------

# Part G -- Frequently Asked Viva Questions

1.  Why do we sample analog signals?
2.  Why can't computers process analog signals directly?
3.  Why do we use NumPy instead of Python lists?
4.  Why is Matplotlib important?
5.  Why is `plot()` used for continuous signals?
6.  Why is `stem()` used for discrete signals?
7.  When should `scatter()` be used?
8.  Can `linspace()` replace `arange()`?
9.  What is the purpose of grid lines?
10. What happens if sampling becomes too sparse?
11. Why are titles and axis labels important?
12. Why are legends used?
13. What is the difference between frequency and period?
14. What is the difference between sample point and sample value?
15. Explain analog-to-digital conversion in one minute.
