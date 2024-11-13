# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$
Observing the pattern:
$$ T(n) = T(n/13) + 5
     \ = T(n/13^2) + 5 + 5
     \ = T(n/13^3) + 5 + 5 + 5
     \ = T(n/13^k) + 5k
$$
Since the recursion stops when n <= 1 then $n/13^k<=1$ or $n<=13^k$
$k=log<sub>13</sub>n$
After substituting the formula is $T(n) = T(n/13^k) + 5k$
$=1+5log<sub>13</sub>n$
Since log<sub>13</sub>n grows logarithmically, the asymptotic complexity of T(n) is
$T(n) = O(logn)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$
Using the (Master Theorem)[https://towardsdatascience.com/all-about-mater-theorem-with-its-proof-93455cdb6a4e] where '$T(n) = aT(n/b) + O(n^d)$' and it's three cases
'Case 1: d < log(a) [base b] => Time Complexity = O(n ^ log(a) [base b])

Case 2: d = log(a) [base b] => Time Complexity = O((n ^ d) * log(n) )

Case 3: d > log(a) [base b] => Time Complexity = O((n ^ d))'
\In this case a = 13, b = 13, d = 0 (since the constant is O(1)) and the recurrence has the form: $T(n) = 13T(n/13) + O(1)$
\Comparing d and log<sub>b</sub>a, d = 0 and log<sub>b</sub>a = log<sub>13</sub>13 = 1
\d < log<sub>b</sub>a 
4.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$
