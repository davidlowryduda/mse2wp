A big title 
------------

**Introduction**

Today we will play a small game which is really really simple. We will add up numbers to make numbers. And to keep the matters simple we will only deal with counting numbers $latex {1, 2, 3, \ldots}$ As an example $latex {2 + 3 = 5}$, but to make the game challenging we would reverse the problem. Let's ask how we can split $latex {5}$ into sum of other numbers. For completeness we take $latex {5}$ also as one of the ways to express $latex {5}$ as sum of numbers. Clearly we have the following other ways $$5 = 4 + 1 = 3 + 1 + 1 = 3 + 2 = 2 + 2 + 1 = 2 + 1 + 1 + 1 = 1 + 1 + 1 + 1 + 1$$
 so that there are $latex {7}$ different ways of adding numbers to make $latex {5}$. We don't take into account the order of summands. Also one number can be repeated if needed.

**Partitions of a Number**

It turns out that a whole generation of distinguished mathematicians (Euler, Jacobi, Ramanujan, Hardy, Rademacher etc) were also interested in playing the above game. And needless to say, they made the whole thing very systematic by adding some definitions (its their silly habit so to speak). Following their footprints we say that a tuple $latex {(n_{1}, n_{2}, \ldots, n_{k})}$ of positive integers is a **partition** of a positive integer $latex {n}$ if $$n_{1} \geq n_{2} \geq \cdots \geq n_{k}\text{ and }n_{1} + n_{2} + \cdots + n_{k} = n$$
 Thus $latex {(3, 2), (3, 1, 1)}$ etc are partitions of $latex {5}$. If $latex {(n_{1}, n_{2}, \ldots, n_{k})}$ is a partition of $latex {n}$ then we say that each of the $latex {n_{i}}$ is a *part* of this partition, $latex {k}$ is the *number of parts*, $latex {n_{1}}$ is *the greatest part* and $latex {n_{k}}$ *the least part* of this partition.

The mathematicians were really not so interested in finding individual partitions of a number $latex {n}$, but were rather interested in finding out the total number of partitions of $latex {n}$. The example above deals with $latex {n = 5}$ and clearly there are $latex {7}$ partitions of $latex {5}$. You should convince yourself by taking a slightly larger number, say $latex {n = 8}$ or $latex {n = 10}$, that finding the number of partitions of any given number $latex {n}$ is not that easy. Especially writing out each partition of $latex {n}$ and then counting them all is very difficult. You may always feel that probably you have missed one of the partitions. Mathematicians however found out a smart way to count partitions. We explore this technique further.

**Counting via Method of Coefficients**

To count partitions of $latex {n}$ we need to count tuples $latex {(n_{1}, n_{2}, \ldots, n_{k})}$ such that $latex {n_{1} + n_{2} + \cdots + n_{k} = n}$. Let us first try to solve a simpler problem. Suppose we need to find tuples $latex {(x, y)}$ such that $latex {x + y = 10}$. Also let's assume that $latex {x, y}$ may be zero or positive integers. Clearly we have only $latex {11}$ options $latex {(0, 10), (1, 9), \ldots, (10, 0)}$. Here we are paying attention to order also.

Let's try to count tuples $latex {(x, y, z)}$ satisfying $latex {x + y + z = 10}$. That does not seem so easy like the previous problem. But let's work methodically. Let $latex {x = 0}$ so that $latex {y + z = 10}$ and we have $latex {11}$ tuples $latex {(y, z)}$ for this problem. If $latex {x = 1}$ then $latex {y + z = 9}$ and we have 10 tuples $latex {(y, z)}$ satisfying $latex {y + z = 9}$. Similarly we try for $latex {x = 2, 3, \ldots, 10}$ and then the total count of all the tuples $latex {(x, y, z)}$ is $$11 + 10 + 9 + \cdots + 1 = \frac{11\cdot 12}{2} = 66$$
 Following this argument we can see that the number of non-negative integral solutions to $latex {x + y + z = n}$ is $latex {(n + 1)(n + 2)/2}$. Similarly this argument can be extended to show that the number of solutions to $$x_{1} + x_{2} + \cdots + x_{m} = n$$
 is $latex {\displaystyle \binom{n + m - 1}{m - 1}}$.

There is however another simple way to get the same result. Consider the expression $$(1 + x + x^{2} + \cdots + x^{i} + \cdots)(1 + x + x^{2} + \cdots + x^{j} + \cdots) = \frac{1}{1 - x}\cdot\frac{1}{1 - x}$$
 If we multiply the two series on left side we get expressions of type $latex {x^{i + j}}$ and there will be as many terms like $latex {x^{n}}$ as there are number of solutions to $latex {i + j = n}$. It follows (also note the right side) that the number of non-negative integer solutions to $latex {i + j = n}$ is equal to the coefficient of $latex {x^{n}}$ in $latex {(1 - x)^{-2}}$. Similarly the number of solutions to $latex {x_{1} + x_{2} + \cdots + x_{m} = n}$ is the coefficient of $latex {x^{n}}$ in $latex {(1 - x)^{-m}}$.

As a variation if we want solutions $latex {(i, j)}$ with $latex {i \geq 1, j \geq 2}$ and $latex {i + j = n}$ then we need to start the series corresponding to $latex {i}$ with $latex {x}$ and that for $latex {j}$ with $latex {x^{2}}$ so that the number of solutions is equal to the coefficient of $latex {x^{n}}$ in $$(x + x^{2} + \cdots)(x^{2} + x^{3} + \cdots) = x^{3}(1 - x)^{-2}$$
 Let's now try out the equation $latex {i + 2j = n}$. In this case the series should look like $$(1 + x + x^{2} + \cdots + x^{i} + \cdots)(1 + x^{2} + x^{4} + \cdots + x^{2j} + \cdots) = \frac{1}{(1 - x)(1 - x^{2})}$$
 Similarly we can handle equations like $latex {i + 2j + 3k + l = n}$.

Now we get back to counting partitions of $latex {n}$. Clearly the least part in a partition can be $latex {1}$ and the largest part can be $latex {n}$. Let the integer $latex {i}$ be a part in a partition of $latex {n}$ and let it be repeated $latex {k_{i}}$ times in that partition so that $$1\cdot k_{1} + 2 \cdot k_{2} + \cdots + n\cdot k_{n} = n$$
 Now each of the variables $latex {k_{1}, k_{2}, \ldots, k_{n}}$ is a non-negative integer. Thus total number of partitions of $latex {n}$ is equal to the number of solutions of the above equation. However there is a catch here as the number of variables $latex {k_{1}, k_{2}, \ldots}$ is itself dependent on $latex {n}$. It turns out that the corresponding product is of the form $$(1 + x + \cdots + x^{1\cdot k_{1}} + \cdots)(1 + x^{2} + \cdots + x^{2\cdot k_{2}} + \cdots)\cdots(1 + x^{i} + \cdots + x^{i \cdot k_{i}} + \cdots)\cdots$$
 and this evaluates to $$\frac{1}{(1 - x)(1 - x^{2})(1 - x^{3})\cdots}$$
 It follows that if $latex {p(n)}$ is the number of partitions of $latex {n}$ and $latex {p(0) = 1}$ then $$\sum_{n = 0}^{\infty}p(n)x^{n} = \frac{1}{(1 - x)(1 - x^{2})(1 - x^{3})\cdots}$$


In case of simple equations like $latex {i + 2j = n}$ the products used to get simplified in the form of a finite number of terms of type $latex {1/(1 - x^{i})}$ and using binomial theorem and multiplication of series we could get a finite formula for the number of solutions to $latex {i + 2j = n}$ in terms of $latex {n}$. But for the expression $$\frac{1}{(1 - x)(1 - x^{2})(1 - x^{3})\cdots}$$
 we don't have a general formula for the $latex {n^{\text{th}}}$ term (because of the infinite number of factors involved). *Are we doomed then?*

**Euler's Pentagonal Theorem**

Luckily the answer is **No** and we have some saving grace as we do have a formula for the $latex {n^{\text{th}}}$ term of $$(1 - x)(1 - x^{2})(1 - x^{3})\cdots$$
 Euler found this formula by multiplying the product by hand to get terms upto $latex {x^{52}}$ and guessed a pattern for the coefficients in the resulting series. However it took him some years to give a theoretical justification for the formula and thereby provide a sound proof. We have the formula $$(1 - x)(1 - x^{2})(1 - x^{3})\cdots = \sum_{j = -\infty}^{\infty}(-1)^{j}x^{(3j^{2} + j)/2}$$
 so that we have to form terms for all integral values of $latex {j}$ (negative and zero also included) and for each $latex {j}$ we have a term $latex {x^{(3j^{2} + j)/2}}$ and its coefficient is $latex {(-1)^{j}}$. Thus there is a term like $latex {x^{k}}$ in the above series expansion if and only if $latex {k}$ is of the form $latex {(3j^{2} + j)/2}$ with $latex {j}$ being some integer. Such numbers $latex {k}$ are called *pentagonal numbers* and for this very reason the Euler's formula above is called the *Pentagonal Theorem*.

Putting $latex {x = 0, -1, 1, -2, 2, -3, 3}$ we get the first few terms of the series as $$1 - x - x^{2} + x^{5} + x^{7} - x^{12} - x^{15} + \cdots$$
 As we have mentioned earlier it took some years for Euler to prove his formula and one might expect the proof to be extremely difficult. It turns out that the proof is not difficult but definitely very non-obvious and requires good amount of heavy mathematical machinery. Near the end of nineteenth century an American mathematician F. Franklin found a marvelous proof which involved no machinery at all, but rather arguments of a very different nature (termed *"combinatorial"* nowadays). This is what we discuss next.

**Combinatorial Proof of Euler's Pentagonal Theorem**

Rather than focusing on $latex {(1 - x)(1 - x^{2})\cdots}$ let us first focus on $$(1 + x)(1 + x^{2})(1 + x^{3})\cdots$$
 which might be simpler because of two reasons:

 - it involves only '+' signs. - it is already already of the form $latex {(1 + x^{i} + \cdots)(1 + x^{j} + \cdots)\cdots}$.

This second part really helps us a lot and tells us that the coefficient of $latex {x^{n}}$ in the new product can be interpreted as the number of solutions to $latex {k_{1} + k_{2} + \cdots + k_{j} = n}$ where all the $latex {k's}$ are different (apart from $latex {x^{0} = 1}$ none of the factors has same power of $latex {x}$). This means that the coefficient of $latex {x^{n}}$ in $$(1 + x)(1 + x^{2})(1 + x^{3})\cdots$$
 gives us the number of partitions of $latex {n}$ with *distinct parts*.

Thus for $latex {n = 5}$ we have three such partitions $latex {(5), (4, 1), (3, 2)}$. Let $latex {q(n)}$ be the coefficient of $latex {x^{n}}$ in $latex {(1 + x)(1 + x^{2})\cdots}$ then $latex {q(5) = 3}$. Also we split $latex {q(n)}$ into multiple terms based on number of parts so that $latex {q_{k}(n)}$ denotes the number of partitions of $latex {n}$ into $latex {k}$ distinct parts and we have $$q(n) = q_{1}(n) + q_{2}(n) + \cdots = \sum_{k \geq 1}q_{k}(n)$$
 We can now attack our original problem of finding coefficient $latex {r(n)}$ of $latex {x^{n}}$ in the product $$(1 - x)(1 - x^{2})(1 - x^{3})\cdots$$
 Clearly when we multiply the individual factors and consolidate the terms $latex {x^{n}}$ we get terms corresponding to each partition of $latex {n}$ with distinct parts, but not each such term will be added (like in case of the product $latex {(1 + x)(1 + x^{2})\cdots}$), rather each such term will have a $latex {+}$ or a $latex {-}$ sign depending on the number of parts in the partition (if number of parts is even then it will be $latex {+}$ otherwise a $latex {-}$). Thus to get $latex {x^{5}}$ we have three terms namely $latex {-x^{5}, x^{5}, x^{5}}$ corresponding to the partitions $latex {(5), (4, 1), (3, 2)}$ respectively. So the net result is the term $latex {x^{5}}$.

It follows that $$r(n) = -q_{1}(n) + q_{2}(n) - q_{3}(n) + \cdots = \sum_{k \geq 1}(-1)^{k}q_{k}(n)$$
 where $latex {r(n)}$ is the coefficient of $latex {x^{n}}$ in $$(1 - x)(1 - x^{2})(1 - x^{3})\cdots$$
 Thus to find the coefficient $latex {r(n)}$ we need to count partitions of $latex {n}$ with distinct parts and try to see "how many (say $latex {A}$) of them have even number of parts" and "how many (say $latex {B}$) have odd number of parts". Then $latex {r(n) = A - B}$. Franklin's great (and at the same time simple) idea was to analyze the partitions of $latex {n}$ with distinct parts and show that most of the time there would be a pairing between partitions with even number of parts and those with odd number of parts so that mostly $latex {A = B}$ and hence the coefficient $latex {r(n) = 0}$.

Only in the exceptional cases there will be a few partitions (of "even" or "odd" type) which will be left out without any pairing with opposite type. Franklin found out exactly which partitions could be paired up and which ones could not. He found that depending on value of $latex {n}$ either there will be no exceptional partitions of this kind or there will be at most only one such partition. We present Franklin's beautiful idea next.

**Franklin's Pairing of Partitions**

To proceed further we fix a pictorial notation for a given partition. If $latex {(n_{1}, n_{2}, \ldots, n_{k})}$ is a partition then it is represented as a left-aligned two dimensional array of dots such such that number of rows in the array is equal to the number of parts in the partition ($latex {k}$) and the $latex {i^{\text{th}}}$ row contains $latex {n_{i}}$ dots. Thus the partition $latex {(5, 4, 2, 2)}$ is represented as

![Partition (5, 4, 2, 2)][1]

Such a notation is very helpful in analyzing the nature of partitions and is the key to most of the combinatorial proofs in the theory of partitions.

Franklin was analyzing partitions with distinct parts via their graphical representations. He found that under certain conditions a partition with odd number of parts could be transformed into a partition with even number of terms and vice versa. His idea was to start with the first row of dots and continue till we get consecutively decreasing series of dots in each successive row. Thus for $latex {(9, 8, 7, 5, 4)}$ we can start with first row of $latex {9}$ dots and then continue till third row of $latex {7}$ dots. We have $latex {3}$ such rows from top where the parts (or dots) decease one by one. If the number of such rows is less than the last part (which is the case here as last part is $latex {4}$) then we can remove the last dots from each of these rows and put it after the last row to make another partition (which also has distinct parts and total number of dots remains same) which has an extra row. This changes the number of rows by one and thereby its parity. The procedure can be reversed if the number of parts is at least one more than the last part. We show this pairing below for the partitions $latex {(9, 8, 7, 5, 4)}$ and $latex {(8, 7, 6, 5, 4, 3)}$.

![Franklin's Pairing][2]

More formally let $latex {(n_{1}, n_{2}, \ldots, n_{k})}$ be a partition of $latex {n}$ with distinct parts and let $latex {j}$ be the smallest integer for which $latex {n_{j + 1} &lt; n_{j} - 1}$. If $latex {j &lt; n_{k}}$ then the last dots of first $latex {j}$ rows can be removed and put as $latex {(k + 1)^{\text{th}}}$ row to make a partition with $latex {(k + 1)}$ distinct parts. If $latex {j \geq n_{k}}$ then the $latex {k^{\text{th}}}$ row can be removed and its dots can be placed one by one at the end of each row starting from first row.

This rearrangement will fail if $latex {j = k = n_{k}}$ or $latex {j = k = n_{k} - 1}$ and will work in all the other cases. In the first case we have $$n = j + (j + 1) + \cdots + (2j - 1) = \frac{3j^{2} - j}{2}$$
 and in the second case $$n = (j + 1) + (j + 2) + \cdots + 2j = \frac{3j^{2} + j}{2}$$
 In these two cases we are left with an unpaired partition with $latex {j}$ parts.

In now follows that the sum $latex {r(n) = \sum_{k \geq 1}(-1)^{k}q_{k}(n)}$ is $latex {0}$ if $latex {n}$ is not of the form $latex {n = (3j^{2} \pm j)/2}$ and is $latex {(-1)^{j}}$ otherwise. We thus have $$(1 - x)(1 - x^{2})(1 - x^{3})\cdots = 1 + \sum_{j = 1}^{\infty}(-1)^{j}x^{(3j^{2} + j)/2} + \sum_{j = 1}^{\infty}(-1)^{j}x^{(3j^{2} - j)/2}$$
 which is also written as $$(1 - x)(1 - x^{2})(1 - x^{3})\cdots = \sum_{j = -\infty}^{\infty}(-1)^{j}x^{(3j^{2} + j)/2}$$
 which is the Euler's Pentagonal Theorem.

**Counting Partitions via Euler's Pentagonal Theorem**

We now have the formula $$\sum_{n = 0}^{\infty}p(n)x^{n} = \frac{1}{(1 - x)(1 - x^{2})\cdots} = \dfrac{1}{{\displaystyle \sum_{n = -\infty}^{\infty}(-1)^{n}x^{(3n^{2} + n)/2}}}$$
 or $$\left(1 + \sum_{n = 1}^{\infty}p(n)x^{n}\right)\left(1 + \sum_{n = 1}^{\infty}(-1)^{n}x^{(3n^{2} + n)/2} + \sum_{n = 1}^{\infty}(-1)^{n}x^{(3n^{2} - n)/2}\right) = 1$$
 Equating coefficients of $latex {x^{n}}$ on both sides gives us a recursive relation to calculate $latex {p(n)}$ namely $$p(n) = p(n - 1) + p(n - 2) - p(n - 5) - p(n - 7) + p(n - 12) + p(n - 15) - \cdots$$
 where the pattern $latex {1, 2, 5, 7, 12, 15,\ldots}$ is the sequence of pentagonal numbers of the form $latex {(3j^{2} \pm j)/2}$. We start with $latex {p(1) = 1}$ and the convention that $latex {p(0) = 1, p(n) = 0}$ if $latex {n &lt; 0}$. We have the next few calculations $$\begin{aligned}p(2) &= p(1) + p(0) = 2\\ p(3) &= p(2) + p(1) = 3\\ p(4) &= p(3) + p(2) = 5\\ p(5) &= p(4) + p(2) - p(0) = 7\\ p(6) &= p(5) + p(4) - p(1) = 11\\ p(7) &= p(6) + p(5) - p(2) - p(0) = 15\\ p(8) &= p(7) + p(6) - p(3) - p(1) = 22\\ p(9) &= p(8) + p(7) - p(4) - p(2) = 30\\ p(10) &= p(9) + p(8) - p(5) - p(3) = 42\end{aligned}$$


Indian mathematician S. Ramanujan was not so happy calculating partitions in this manner (because it involved keeping a table of all previously calculated values) and he gave an almost exact formula for $latex {p(n)}$ in terms of $latex {n}$ which was further refined by Hans Rademacher into an exact formula. It of interest to note that before the Ramanujan-Rademacher formula, Euler's pentagonal theorem was the only way out to calculate partitions of a number. The approach by Ramanujan is considerably more difficult to understand but is a gem of mathematics and we will have occasion to discuss it later on this blog.

 [1]: http://i.stack.imgur.com/dkTHm.png [2]: http://i.stack.imgur.com/E6m9N.png 