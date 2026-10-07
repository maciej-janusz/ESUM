# ESUM – lab notebooks

My completed lab assignments for the ESUM course (Computer Science, AGH, semester 4).
The labs cover Monte Carlo methods, Bayesian inference, Gaussian processes and
probabilistic programming in Python (NumPy, SciPy, TensorFlow Probability).

Task descriptions and starter code come from the course instructors; the solutions are mine.
Notebooks are saved with their outputs, so they can be read without running anything.

## Labs

| Lab | Topic |
|-----|-------|
| [lab1](lab1.ipynb) | Monte Carlo introduction to Python, NumPy and Jupyter (estimating π) |
| [lab2](lab2.ipynb) | Estimating object location from noisy radar echos |
| [lab3](lab3.ipynb) | Linear regression |
| [lab4](lab4.ipynb) | Gaussian process regression and its applications (incl. Bayesian optimization) |
| [lab5](lab5.ipynb) | Multinomial logistic regression (MNIST) |
| [lab6](lab6.ipynb) | Introduction to TensorFlow and TensorFlow Probability |
| [lab7](lab7.ipynb) | MCMC inference in hierarchical Bayesian models |

## Setup

Tested with Python 3.11.9 on macOS.

```bash
python3.11 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Then open the notebooks in VS Code (the `ipykernel` dependency is enough), or install
Jupyter yourself, e.g. `pip install jupyterlab && jupyter lab`.

Dependencies are pinned to the exact versions the notebooks were run with.
Lab5 uses `np.reshape(..., shape=...)`, which needs a recent NumPy 2.x, so don't downgrade NumPy.

## Notes

- **MNIST (lab5)** is downloaded on first run by the `mnists` package into the system
  temp directory (`/tmp/mnists` on macOS/Linux), so the first run needs internet access
  and the data is re-downloaded after the temp directory is cleaned.
- **TensorFlow** is a heavy dependency (several hundred MB); lab6 and lab7 are the
  ones that use it.
- All notebooks seed NumPy with `np.random.seed(1234)`. Lab4 explicitly asks to re-run
  cells several times and compare results, so some outputs there will differ between runs.

## Layout

```
.
├── lab1.ipynb … lab7.ipynb
├── requirements.txt
└── README.md
```
