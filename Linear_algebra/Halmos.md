# Finite Dimensional Vector Spaces

$$
\renewcommand{\R}{\mathbb{R}}
\newcommand{\inner}[2]{\langle #1, #2 \rangle}
\newcommand{\un}[1]{\hat{\mathrm{#1}}}
\newcommand{\bv}[1]{\mathrm{#1}}
\newcommand{\norm}[1]{\left\|{#1}\right\|}
$$

## Chapter 1

### Fields

**Axioms**:
* $a+b=b+a$
* $a+(b+c)=(a+b)+c$
* $\exists \text{ unique element } 0: a+0=a$, $\forall a\in F$
* $\forall a\in F$ there is a unique element symbolized $-a\in F$ such that $a+(-a)=0$
* $ab=ba$
* $a(bc)=(ab)c$
* $\exists \text{ unique element 1 }: a1=a, \forall a\in F$
* $\forall a\neq0$ there is a unique element $a^{-1}\equiv 1/a$ such that $aa^{-1}=1$.
* $a(b+c)=ab+ac$

#### Exercise 1
(a) Prove that $0+a=a$.

We have $0+a=a+0=a$. $\square$

(b) Prove that $a+b=a+c\Rightarrow b=c$.

$$
\begin{align*}
b &= 0+b=\\
&= [(-a)+a]+b=\\
&= (-a)+(a+b)=\\
&= (-a)+(a+c)=\\
&= [(-a)+a]+c=\\
&= 0+c=\\
&=c.\quad\square
\end{align*}
$$

(c) Prove that $a+(b-a)=b$

$$
a+(b-a)=a+[(-a)+b]=[a+(-a)]+b=0+b=b.\quad\square
$$

(d) Prove that $0\cdot a =a\cdot 0=0$.

For an arbitrary $b\in F$ we have

$$
\begin{gather*}
a\cdot 0=(-a+a)+a0=(-a+a1)+a0=-a+(a1+a0)=\\
=-a+a(1+0)=-a+a1=-a+a=0
\end{gather*}
$$

Moreover $a0=a0=0$. $\square$

(e) Prove that $(-1)a=-a$.

$$
(-1)a+a=a(-1)+a1=a[(-1)+1]=a0=0,
$$

hence the unique opposite of $a$, noted as $-a$ is equal to $(-1)a$. $\square$

(f) Prove that $(-a)(-b)=ab$.

$$
(-a)(-b)=[a(-1)](-b)=a[(-1)(-b)]=a(-(-b))=ab\quad\square
$$

(g) Prove that if $ab=0$ then $a=0$ or $b=0$ or both.

If $a\neq 0$, there is $a^{-1}$ such that $aa^{-1}=1$. Hence

$$
b = 1b = (aa^{-1})b = (a^{-1}a)b=a^{-1}(ab)=a^{-1}0=0.
$$

Likewise, if $b\neq 0$ we can prove that $a=0$. $\square$

#### Exercise 2

(a) Is the set of all positive integers a field?

No, since there is no opposite element for addition except for 0.

(b) Is the set of all integers a field?

No, since there is no inverse element for multiplication, except for 1.

(c) Can the answer to these questions be changed if we redefine addition or multiplication or both?

I have no idea... 

$$
f(a,b)=f(b,a)
$$

#### Exercise 3
$\mathcal{Z}_m=\{0,1,2,\dots, m-1\}$, with $a\oplus b=(a+b)\mod m$ and $a\odot b=ab\mod m$. Prove that $\mathcal{Z}_m$ is a field if and only if $m$ is prime.

Commutativity is evident both for multiplication and addition for any $m$. 

Associativity: let $a+b=km+r$ and $b+c=lm+q$. We have $r+c= a+b-km+c$ and $a+q=a+b+c-lm$. Let $a+b+c=nm+p$. Then $r+c = (n-k)m+p$ and the least positive remainder is $p$. Same, for $a+q=(n-l)m+p$ the least positive remainder is $p$

For multiplication let $ab=km+r$ and $bc=lm+q$. We have rc = (ab-km)c=abc-kmc$ and $aq = a(bc-lm)=abc-alm$. Now, let $abc=nm+p$. Then $rc=mn+p-kcm = (n-kc)m+p$ hence the remainder is $p$. Furthermore $aq=nm+p-alm=(n-al)m+p$ hence the remainder is also $p$.

As 0 and 1 we can use the standard numbers of arithmetic.

This far we didn't need $m$ to be prime. Now let us check for the existence and uniqueness of the inverse element. For addition we can define as $-a\equiv m-a$ which is always unique and adds up to $m$.

For multiplication we need an element $a^{-1}$ such that $aa^{-1}=km+1$ for some integer $k$. Let us examine all the products $a\cdot k$ for $k\in\mathcal{Z}_m$. We perform the division of each product with $m$ and get $ak=p_km+r_k$. Now, if two different integers $k,l\in\mathcal{Z}_m$ had the same remainder, i.e. if $r_k=r_l$, then $ak-p_km=al-p_lm$, hence $a(k-l)=(p_k-p_l)m$. If $m$ is prime, this means that at least one of $a$ or $k-l$ has $m$ in its prime factorization. However, this is impossible, since both are $<m$. Thus, all remainders are unique. If we have $m$ unique remainders that can only take the values $0,1,...,m-1$, this means that according to the pigeonhole principle they take on all these values, thus there exists one $k\in\mathcal{Z}_m$, such that $p_k=1$, which is the unique inverse element.

Distributivity: $a(b+c)=p_{b+c}m+r_{b+c}$ and $ab+ac=p_bm+p_cm+r_b+r_c$. Let $r_b+r_c=km+r$. Thus $a\odot(b+c)=r_{b+c}$ and $a\odot b+a\odot c=r$.

$$
\begin{gather*}
a(b+c)=p_{b+c}m+r_{b+c}\\
ab+ac=p_bm+p_cm+km+r
\end{gather*}
$$

By subtracting both equalities we have $r_{b+c}-r=(p_b+p_c+k-p_{b+c})m$, and since both $r_{b+c}$ and $r$ belong to $\mathcal{Z}_m$, their difference cannot be an integer multiple of $m$. Hence $r_{b+c}=r$.

Inverse: If $\mathcal{Z}_m$ is a field, the equation $a\odot b=0$ cannot be satisfied if both $a$ and $b$ are nonzero. If $m$ were not prime, it would be the product of at least two non zero positive integers $a,b$. These integers must be both smaller than $m$, hence they belong to $\mathcal{Z}_m$. This would mean that $ab=m$ and $a\odot b=0$, which is a contradiction.

Example: $-1$ in $\mathcal{Z}_5$ is $4$, since $1+4=5$ and $1\oplus 4=0$

Example: We want to find $1/3$ in $\mathcal{Z}_7$. We have $5\cdot 3=15=2\cdot 7+1$, hence $1/3=5$.

#### Exercise 4

Prove that if one adds $1+1+1+\dots$ and gets zero for the first time, the number of terms added is a prime number.

Let $m\cdot 1 \equiv \underbrace{1+1+1+\dots+1}_{m\text{ times }}=0$.