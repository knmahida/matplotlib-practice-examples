
# matplotlib-practice-examples
A collection of simple and intermediate Matplotlib examples taken from the `Matplotlib.ipynb` notebook. The notebook demonstrates line plots, subplots, custom axes, figure sizing, saving figures, and basic legends — useful for learning plotting idioms in Python.

## Quick start

- Requirements: `python` (3.8+ recommended), `matplotlib`, `numpy`, and Jupyter or VS Code.
- Install the required packages with pip:

```bash
python -m pip install --user matplotlib numpy jupyterlab
```

## Run the notebook

- Open the notebook and run cells interactively:

```bash
jupyter notebook Matplotlib.ipynb
# or open the file in VS Code
code Matplotlib.ipynb
```

## Examples (extracted from `Matplotlib.ipynb`)

Below are concise, runnable snippets that mirror the notebook examples.

1) Basic plot

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
y = x ** 2

plt.plot(x, y)
plt.title('Plot of y = x^2')
plt.xlabel('x')
plt.ylabel('y')
plt.show()
```

2) Two subplots (side-by-side) with different styles

```python
plt.subplot(1, 2, 1)
plt.plot(x, y, 'r-')
plt.title('Red Line')

plt.subplot(1, 2, 2)
plt.plot(x, y, 'b--')
plt.title('Blue Dashed Line')
plt.show()
```

3) Creating a figure and axes with `add_axes`

```python
fig = plt.figure()
ax = fig.add_axes([0.1, 0.1, 0.8, 0.8])  # left, bottom, width, height (0-1)
ax.plot(x, y)
ax.set_title('Title')
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')
plt.show()
```

4) Figure with an inset (larger and smaller axes)

```python
fig = plt.figure()
ax1 = fig.add_axes([0.1, 0.1, 0.8, 0.8])
ax2 = fig.add_axes([0.2, 0.5, 0.4, 0.3])
ax1.plot(x, y)
ax1.set_title('Larger Plot')
ax2.plot(y, x)
ax2.set_title('Smaller Plot')
plt.show()
```

5) Using `subplots` to create an axes array

```python
fig, axs = plt.subplots(nrows=1, ncols=2)
axs[0].plot(x, y)
axs[1].plot(x, y, '--')
plt.tight_layout()
plt.show()
```

6) Figure size, DPI, and saving

```python
fig, axes = plt.subplots(nrows=2, ncols=3, figsize=(10, 7), dpi=100)
plt.tight_layout()
# Save figure to file at higher DPI
fig.savefig('my_figure.png', dpi=200)
```

7) Plotting multiple lines and showing a legend

```python
fig = plt.figure()
ax = fig.add_axes([0, 0, 1, 1])
ax.plot(x, x**2, label='x squared')
ax.plot(x, x**3, label='x cubed')
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')
ax.set_title('Title')
ax.legend()
plt.show()
```

## Notes and next steps

- The notebook contains runnable cells with small explanatory comments and printed outputs — open `Matplotlib.ipynb` to run everything interactively.
- Running the save example will create `my_figure.png` in the repository root; include or commit that image if you want a visual reference in this README.
- If you want, I can:
	- add inline images (rendered PNGs) to this README,
	- extract each example into small `examples/` scripts, or
	- create a `requirements.txt` for this repo.
