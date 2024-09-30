
## *Problem 3.40.* Random Walk

$n+n' = N$ total steps. $n$ is the number of steps to the right, and has the probability $p$.

$$\begin{align*}
    \braket x /a &= \braket{n-n'} = \braket{n-(N-n')}
    \\
    &= \braket{2n - N} = (\braket{2n} - \braket{N}),\quad \braket n=pN
    \\
    &= \left(2p - 1\right)N

    \\\\
    \braket{x}^2/a^2 &= (2p-1)^2N^2 
    \\
    &= 4p^2N^2 -4pN^2 + N^2
    
    \\\\
    \braket{x^2}/a^2 &= \braket{(n-n')^2}a^2 = \braket{(2n - N)^2}
    \\
    &= 4\braket{n^2} +\braket{N^2} -\braket{4nN} 
    \\
    &= 4\braket{n^2} + N^2 - 4pN^2
    \\\\
    \sigma^2(x) /a^2 &= \braket{x^2}/a^2 - \braket{x}^2/a^2 
    \\
    &= \Big(4\braket{n^2} + \cancel{N^2} - \bcancel{4pN^2}\Big) - \Big(4p^2N^2 - \bcancel{4pN^2} + \cancel{N^2}\Big)
    \\
    &= 4\braket{n^2} - 4N^2p^2, \quad \braket{n^2} = \sigma^2(n) + \braket{n}^2,\quad \sigma^2(n) = Np(1-p)
    \\
    &= 4\Big(Np(1-p) + N^2p^2\Big) - 4N^2p^2
    \\
    &= 4Npq,\quad q=1-p
    
\end{align*}$$


## *Problem 3.41.* Monte Carlo Simulation of a one-dimensional random walk


## *Problem 3.45.* Exponential probability density (Ups)

We have the probability density: 

$$
    p(x) = 
    \begin{cases}
        Ae^{-\lambda x}, & 0 \leq x < \infty \\
        0 & \text{otherwise}
        
    \end{cases}
$$

### *(a)* Determine the namalization constant
$$\begin{align}
    \int_{-\infty}^\infty p(x)dx &= 1 \\

    \int_{0}^\infty Ae^{-\lambda x}dx &= A\left[-\frac1\lambda e^{-\lambda x}\right]_0^\infty = -\frac{A}{\lambda}\left[0 - 1\right],\quad A = \lambda
\end{align}$$


### *(b)* What is the mean value of $x$? What is the most probable value of $x$?

$$\begin{align}
    \braket{x} &= \int_0^\infty xp(x)dx = \underset{=0}{\underbrace{-xe^{-\lambda x}\Bigg\vert_0^\infty}}+ \underset{=-\dfrac{1}{\lambda}\exp(-\lambda x)\Big\vert_0^\infty}{\underbrace{\int_0^\infty dx \exp(-\lambda x)}} = \frac{1}{\lambda} 
\end{align}$$

The most probable value is one which 
$$
    x_{MLE} = \max_{x\in \left[0,\infty\right)}{\lambda \exp(-\lambda x)} =  0
$$

### *(c)* what is the mean value of $x^2$?

$$
    \braket{x^2} = \int_0^\infty x^2p(x) dx  = \underset{=0}{\underbrace{-x^2\exp(-\lambda x)\Big\vert_0^\infty}} - \underset{=\frac{2}{\lambda}\braket{x}}{\underbrace{\int_0^\infty2x\exp(-\lambda x)dx}} = \dfrac{2}{\lambda^2}
$$

### *(d)* Determine the probability that a measurement of $x$ yields a value between $1$ and $2$.

$$
    P(1\leq x < 2) = \int_1^2 p(x) dx = \exp(-\lambda) - \exp(-2\lambda)
$$

### *(e)* Determine the probability that a measurement of $x$ yields a value less than $0.3$

$$
    P(x\leq 0.3) = \int_0^{0.3}dx p(x) = 1 - \exp(-0.3\lambda)
$$

## *Problem 3.7.*