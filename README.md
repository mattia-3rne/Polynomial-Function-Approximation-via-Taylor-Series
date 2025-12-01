# Polynomial Function Approximation via Taylor Series

## 📊 Project Overview

The goal of this project is to demonstrate **Taylor's Theorem** by implementing a symbolic approximation engine from scratch. This implementation proves that complex, non-polynomial functions (such as transcendental functions like $\sin(x)$, $\cos(x)$, or $e^x$) can be expressed as infinite polynomials.

This project uses Calculus to derive the exact polynomial construction of a function based on its behavior at a single point. It visualizes how adding higher-degree terms converges the approximation to the target function.

---

## 🧠 Theoretical Background

### Taylor's Theorem

Taylor's Theorem states that any function $f(x)$ that is infinitely differentiable at a real number is the sum of its Taylor series. This allows us to convert complex functions into simple sums of powers.

Formally, the Taylor series of a function $f(x)$ that is infinitely differentiable at a point $x_0$ is the power series:

$$
P_N(x) = \sum_{n=0}^{N} \frac{f^{(n)}(x_0)}{n!} (x - x_0)^n
$$

Where:
* $f^{(n)}(x_0)$ is the $n$-th derivative of $f$ evaluated at the center $x_0$.
* $N$ is the degree of the polynomial approximation.

### Transcendental Functions as Polynomials

A core demonstration of this project is showing that trigonometric and exponential functions are essentially just polynomials with specific coefficients. For example, centered at $x_0 = 0$.

| Function | Taylor Expansion (at $x_0=0$) | Structure |
| :--- | :--- | :--- |
| $\sin(x)$ | $x - \frac{x^3}{3!} + \frac{x^5}{5!} - \dots$ | **Odd** powers only. Approximates the wave. |
| $\cos(x)$ | $1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots$ | **Even** powers only. Symmetric. |
| $e^x$ | $1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots$ | Sum of all powers. Grows exponentially. |

### Error Analysis (Lagrange Error Bound)

The approximation is rarely perfect for a finite $N$. The difference between the actual function and the polynomial is the Remainder term $R_N(x)$.

If we approximate $f(x)$ with a degree $N$ polynomial, the error is:

$$
R_N(x) = f(x) - P_N(x) = \frac{f^{(N+1)}(z)}{(N+1)!}(x - x_0)^{N+1}
$$

for some real number $z$ between $x$ and $x_0$. As $N \to \infty$, this error term goes to 0 for convergent functions.

---

## ⚠️ Limitations

| Limitation | Description                                                                                                                                                                                   |
| :--- |:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Radius of Convergence** | Not all series converge everywhere. For example, the series for $\ln(x)$ centered at $x=1$ only converges for $0 < x \le 2$. Outside this range, the approximation explodes towards infinity. |
| **Differentiability** | The function must be $C^\infty$ (smooth). Functions with "kinks" like $\vert x\vert$ at 0) or discontinuities cannot be approximated via Taylor Series at those points.                       |
| **Local Accuracy** | Taylor series are "local" approximations. They are incredibly accurate near $x_0$ but require significantly higher degrees $N$ to maintain accuracy as you move further away from the center. |

---

## 🚀 Getting Started

### Prerequisites
* Python 3.8+
* Jupyter Notebook

### Installation

1.  **Clone the repository**:
    ```bash
    git clone https://github.com/mattia-3rne/Polynomial-Function-Approximation-via-Taylor-Series.git
    ```

2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```

---

## 📂 Project Structure

* `requirements.txt`: Python package dependencies.
* `main.ipynb`: The main analysis notebook.
* `README.md`: Project documentation.
