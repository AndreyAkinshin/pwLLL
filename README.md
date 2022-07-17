# Piecewise linear LLL-system

A [Shiny](https://shiny.rstudio.com/) app that builds 3D phase portraits for the following piecewise linear LLL-system:

$$
\begin{cases}
  \dot{x}_1 = L(a_1, k_1, x_3) - k_1 x_1,\\
  \dot{x}_2 = L(a_2, k_2, x_1) - k_2 x_2,\\
  \dot{x}_3 = L(a_3, k_3, x_2) - k_3 x_3,
\end{cases}
$$

where $L$ is a piecewise linear function:

$$
L(a, k, x) = \begin{cases}
ak & \quad \textrm{for}\ \ \ 0 \leq x \leq 1,\\
0 & \quad \textrm{for}\ \ \ 1 < x.
\end{cases}
$$

![](/screenshots/screen.png)

## Parameters

* $a_1$, $a_2$, $a_3$, $k_1$, $k_2$, $k_3$: the dynamical system parameter.
* $\textrm{TotalTime}$: the total time simulation.
* $\textrm{SkipTime}$: the initial time interval that will not be presented on the plot.
* $N$: the number of simulated trajectories.
* $\textrm{Seed}$: the randomization seed that controls the initial positions of all the trajectories.

## Initial points

We uniformly generate the initial point for each simulated trajectory from the following area:

$$
[0.5; (2+a_1)/3]
\times
[0.5; (2+a_2)/3]
\times
[0.5; (2+a_3)/3].
$$
