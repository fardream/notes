# Notes

$$
X=QR
$$

where $Q^TQ=I$ and $R$ is upper triangular.

$$
\hat{\beta} = \left(X^TX\right)^{-1}Xy
$$

$$
\hat{\beta} = \left(R^TQ^TQR\right)^{-1}R^TQ^Ty = R^{-1}Q^Ty
$$

$$
\hat{y} = X\hat{\beta} = QRR^{-1}Q^Ty= QQ^Ty
$$

$$
\hat{\epsilon}=y-\hat{y} = y - QQ^Ty
$$

$$
\hat{\sigma}^2 = y^Ty - y^TX\left(X^TX\right)^{-1}X^Ty = y^Ty - y^TQQ^Ty
$$

with one extra $x$, we have

$$
X = \begin{pmatrix}QR & x\end{pmatrix}
$$

and the new

$$
X^TX = \begin{pmatrix}
R^TR & R^TQ^Tx \\
x^TQR & x^T x
\end{pmatrix}
$$

and

$$
\left(X^TX\right)^{-1} = \begin{pmatrix}A & B \\
B^T & D\end{pmatrix}
$$

where

$$
A =\left(R^TR\right)^{-1} + R^{-1}Q^Tx\left(x^Tx - x^T QQ^Tx\right)^{-1}x^TQR^{-T}
$$

$$
B = - R^{-1}Q^Tx\left(x^Tx - x^T QQ^Tx\right)^{-1}
$$

$$
D = \left(x^Tx - x^T QQ^Tx\right)^{-1}
$$

$$
\left(X^TX\right)^{-1}X^T=\begin{pmatrix}
R^{-1}Q^T + R^{-1}Q^Tx \left(x^Tx - x^T QQ^Tx\right)^{-1} x^TQQ^T - R^{-1}Q^Tx\left(x^Tx - x^T QQ^Tx\right)^{-1}x^T \\
-\left(x^Tx - x^T QQ^Tx\right)^{-1}x^TQQ^T +\left(x^Tx - x^T QQ^Tx\right)^{-1}x^T
\end{pmatrix}
$$

$$
X\left(X^TX\right)^{-1}X^T= QQ^T + QQ^Tx \left(x^Tx - x^T QQ^Tx\right)^{-1} x^TQQ^T - QQ^Tx\left(x^Tx - x^T QQ^Tx\right)^{-1}x^T -x\left(x^Tx - x^T QQ^Tx\right)^{-1}x^TQQ^T + x\left(x^Tx - x^T QQ^Tx\right)^{-1}x^T
$$

Let $z=x-QQ^Tx$, notice that $Q^Tz = Q^Tx - Q^TQQ^Tx = 0$, and $z^Tz=x^Tx - x^TQQ^Tx$

$$
X\left(X^TX\right)^{-1}X^T=QQ^T-QQ^Tx\left(z^Tz\right)^{-1}z^T+x\left(z^Tz\right)^{-1}z^T=QQ^T+z\left(z^Tz\right)^{-1}z^T
$$

finally

$$
\hat{\sigma}^2 = y^Ty - y^TX\left(X^TX\right)^{-1}X^Ty = y^Ty - y^TQQ^Ty - y^Tz\left(z^Tz\right)^{-1}z^Ty
$$

New

$$
Q = \left(Q \quad \frac{z}{\sqrt{z^Tz}}\right)
$$

$$
R = \begin{pmatrix}R & Q^Tx \\
0 & \sqrt{z^Tz}
\end{pmatrix}
$$

$$
QR = \begin{pmatrix}QR & QQ^Tx + z \end{pmatrix} = \begin{pmatrix}QR & x \end{pmatrix}
$$
