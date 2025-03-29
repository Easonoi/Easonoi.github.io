OI入门3

注意到，其实(n-1)*(m-1)的区域可以随便填 1 或 -1，这会唯一确定第n行和第m列的填数（为了使得乘积为k）
但是要特别注意(n,m)处的数字，他会同时影响第n行、第m列的乘积

k=-1时，
设
$x={\prod \limits_{i=1}^{n-1}a_{i,m}}$
$y={\prod \limits_{i=1}^{m-1}a_{n,i}}$
$t=\prod \limits_{i=1}^{n-1} \prod \limits_{j=1}^{m-1} a_{i,j}$

$\because x\times a_{n,m}=y\times a_{n,m}=k $
$\therefore x=y$（使得(n,m)处能够填）
$\therefore \frac{k^{n-1}}{t}=\frac{k^{m-1}}{t}$
$\therefore k^{n-1}=k^{m-1}$
$k=1$时显然符合
$k=-1$时只有$n \equiv m \  (mod\ 2)$时可行