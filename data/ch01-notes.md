# Module 01 · Vectors, Length and Matrices

This module builds the three objects the rest of the course runs on: the **vector**, the **dot product**, and the **matrix**. Nothing here assumes any previous linear algebra. It assumes you can plot a point, solve two equations in two unknowns, and use Pythagoras — and it rebuilds the rest from those.

**By the end of it you will be able to:**

1. Write a vector, add two vectors, scale one, and say what each operation does to the picture.
2. Decide what a combination $c\mathbf{v} + d\mathbf{w}$ can reach — a line, a plane, or everything — *before* trying to solve anything.
3. Solve $c\mathbf{v} + d\mathbf{w} = \mathbf{b}$ for the unknown numbers $c$ and $d$, and recognise when no solution exists.
4. Compute lengths, dot products and angles from components alone.
5. Test perpendicularity with one arithmetic check, build a unit vector, and write the equation of a plane from a normal vector.
6. Compute $A\mathbf{x}$ two ways — as a combination of the columns of $A$, and row by row — and use each as a check on the other.

One task from the real exam papers is worked end to end inside this module: the plane $c\mathbf{v}+d\mathbf{w}$ with its normal, unit vector and equation — Midterm 2024, Problem II — in §1.7, on vectors chosen for this course rather than the exam's own; the paper's own version, with its own vectors, is set as question C1 in the practice set. Four homework assignments are covered as well: HW 1-1, HW 1-2 and HW 1-3, and the two ways of computing $A\mathbf{x}$ that HW 2-1 asks for explicitly, in §1.9.

## 1.1 Vectors: one object for a whole move

Imagine programming a robot on a grid floor. It knows exactly two moves:

- **Step A:** 1 unit east, 2 units north.
- **Step B:** 3 units east, 1 unit north.

You want it to finish at the point $(14, 8)$. How many of each step?

You could write two separate equations — one bookkeeping east-west, one bookkeeping north-south — and you would be right. But you have split *one physical movement* into two unrelated pieces of arithmetic, and you will keep re-splitting it every time. What you want is a single object that holds "1 east, 2 north" as one thing.

That object is a **vector**, written as a column:

$$\mathbf{v} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$$

Read it as: *first number = how far east, second number = how far north.* Picture it as an arrow from the origin $O=(0,0)$ to the point $(1,2)$. The arrow carries two facts at once — a direction and a distance — which is exactly why the object is worth having.

> **Definition (vector in $\mathbb{R}^n$).** A vector with $n$ components is an ordered list of $n$ real numbers, written as a column. The numbers $v_1,\dots,v_n$ are its **components**. The set of all such vectors is written $\mathbb{R}^n$.

Vectors are written in **boldface** ($\mathbf{v}$, $\mathbf{w}$, $\mathbf{b}$) to keep them visually apart from plain numbers, called **scalars**, which stay italic ($c$, $d$, $k$). They are written as *columns*, not rows, because in §1.8 a matrix is built by standing vectors side by side as its columns — having them already in column form makes that step immediate.

**Adding: "do this, then do that."** If the robot runs Step A and then Step B, it has moved $1+3=4$ east and $2+1=3$ north. Vector addition is defined component by component:

$$\mathbf{v} + \mathbf{w} = \begin{bmatrix} v_1 + w_1 \\ \vdots \\ v_n + w_n \end{bmatrix}$$

In the picture: draw $\mathbf{v}$ from the origin, then draw $\mathbf{w}$ starting where $\mathbf{v}$ ended. The single arrow from the very start to the very end is $\mathbf{v}+\mathbf{w}$. This is the **tip-to-tail rule**, and it gives the same answer as the **parallelogram rule** (both arrows drawn from the origin; the sum is the diagonal).

**One restriction, and it is not a technicality.** Two vectors can be added only if they have the *same number of components*. "1 east, 2 north" plus "1 east, 2 north, 3 up" has no meaning to give it.

**Scaling: "do it several times, or reverse it."** Running Step A three times moves the robot $3\times 1 = 3$ east and $3 \times 2 = 6$ north. Scalar multiplication multiplies every component by the same number:

$$c\mathbf{v} = \begin{bmatrix} cv_1 \\ \vdots \\ cv_n \end{bmatrix}$$

Geometrically: $c>1$ stretches the arrow, $0<c<1$ shrinks it, $c<0$ reverses it and scales it by $|c|$, and $c=0$ collapses it to the **zero vector** $\mathbf{0}$, the arrow of no length sitting at the origin. Subtraction is shorthand: $\mathbf{v}-\mathbf{w}$ means $\mathbf{v} + (-1)\mathbf{w}$, so the minus sign reaches *every* component of $\mathbf{w}$.

The one thing scaling can never do is bend the arrow off its own line. $c\mathbf{v}$ points along the same line through the origin as $\mathbf{v}$ — the same way if $c>0$, the exact opposite way if $c<0$. Only *adding* a second, differently-directed vector gets you off that line.

**Both ideas at once.** Scale each of several vectors, then add the results:

$$c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_k\mathbf{v}_k$$

This is a **linear combination**, and the numbers $c_1,\dots,c_k$ are its **coefficients**. "Linear" signals that nothing more exotic happens: no component is ever squared, no two vectors are multiplied together. Every idea in this course is built from this one expression.

The robot's question now has a one-line form:

$$c\begin{bmatrix}1\\2\end{bmatrix} + d\begin{bmatrix}3\\1\end{bmatrix} = \begin{bmatrix}14\\8\end{bmatrix}$$

**Worked example 1 (basic arithmetic).** With $\mathbf{v}=\begin{bmatrix}2\\1\end{bmatrix}$ and $\mathbf{w}=\begin{bmatrix}1\\2\end{bmatrix}$, compute $3\mathbf{v}+\mathbf{w}$, and then the general $c\mathbf{v}+d\mathbf{w}$.

Scale first: $3\mathbf{v} = \begin{bmatrix}6\\3\end{bmatrix}$. Add: $3\mathbf{v}+\mathbf{w} = \begin{bmatrix}6+1\\3+2\end{bmatrix} = \begin{bmatrix}7\\5\end{bmatrix}$.

With letters instead of numbers the same two steps give $c\mathbf{v} = \begin{bmatrix}2c\\c\end{bmatrix}$, $d\mathbf{w} = \begin{bmatrix}d\\2d\end{bmatrix}$, so

$$c\mathbf{v}+d\mathbf{w} = \begin{bmatrix}2c+d\\c+2d\end{bmatrix}$$

That second answer is the useful one: it describes *every* point reachable from these two vectors, as $c$ and $d$ range over all real numbers. Setting it equal to a target is how §1.3 solves for $c$ and $d$.

**Worked example 2 (solving for two unknown vectors).** Suppose $\mathbf{v}+\mathbf{w} = \begin{bmatrix}5\\1\end{bmatrix}$ and $\mathbf{v}-\mathbf{w} = \begin{bmatrix}1\\5\end{bmatrix}$. Find $\mathbf{v}$ and $\mathbf{w}$.

Add the two equations. On the left, $\mathbf{w}$ and $-\mathbf{w}$ cancel, leaving $2\mathbf{v}$; on the right, add component by component:

$$2\mathbf{v} = \begin{bmatrix}6\\6\end{bmatrix} \implies \mathbf{v} = \begin{bmatrix}3\\3\end{bmatrix}$$

$$\mathbf{w} = \begin{bmatrix}5\\1\end{bmatrix} - \begin{bmatrix}3\\3\end{bmatrix} = \begin{bmatrix}2\\-2\end{bmatrix}$$

Treating whole vectors as single unknowns is legal precisely because addition and scaling are defined component by component — working with the whole vector is doing both component calculations at once.

## 1.2 What cv + dw can reach

Before solving anything, it is worth asking what is even reachable. Let $c$ and $d$ range over **all** real numbers. Which points can $c\mathbf{v}+d\mathbf{w}$ produce?

- **One vector only.** The tips of $c\mathbf{v}$ trace the entire straight **line** through the origin in the direction of $\mathbf{v}$ (and the opposite direction, and everything between).
- **Two vectors pointing genuinely different ways.** You can reach **every point of the plane**. Intuitively: $c\mathbf{v}$ slides you anywhere along one line, and adding $d\mathbf{w}$ slides you off that line in a second, independent direction. Two independent choices, two dimensions covered.
- **The trap: two vectors on the same line.** If $\mathbf{w} = k\mathbf{v}$ for some number $k$, then $c\mathbf{v}+d\mathbf{w} = (c+dk)\mathbf{v}$ — still just a multiple of $\mathbf{v}$. Every combination is stuck on **one line**, no matter what $c$ and $d$ you pick. Two "directions" that are secretly the same direction give no more reach than one.

> **Fact 1.** For nonzero $\mathbf{v},\mathbf{w}$ in $\mathbb{R}^2$: if $\mathbf{w}$ is **not** a scalar multiple of $\mathbf{v}$, then every $\mathbf{b}$ in $\mathbb{R}^2$ can be written as $c\mathbf{v}+d\mathbf{w}$, in exactly one way. If $\mathbf{w}$ **is** a scalar multiple of $\mathbf{v}$, the combinations reach only the single line through the origin containing $\mathbf{v}$.

**Why it is true, in three lines.** Write out $c\mathbf{v}+d\mathbf{w}=\mathbf{b}$ component by component and you get two ordinary linear equations in the two unknowns $c,d$. Two independent linear equations in two unknowns have exactly one solution — which is the first case. When $\mathbf{w}=k\mathbf{v}$, the second equation is a multiple of the first, so the pair is really *one* equation (or a contradiction), and the usual reasoning breaks down — exactly matching the geometric picture.

There is a fast arithmetic test for "same line", and it is worth meeting now because you will meet it again in Module 03 under the name *determinant*: $\mathbf{v}$ and $\mathbf{w}$ in $\mathbb{R}^2$ lie on the same line through the origin exactly when

$$v_1w_2 - v_2w_1 = 0$$

Check it against $\mathbf{v}=(1,2)$, $\mathbf{w}=(3,1)$: $1\cdot 1 - 2\cdot 3 = -5 \neq 0$, so these two reach the whole plane, and the robot's target is reachable before you compute a single step.

**Why this matters.** This is your first encounter with the question that never stops being asked in this subject: *does this equation have a solution, and if so, is it the only one?* Right now you can answer it for two vectors by looking at the picture. Module 02 turns the same question into a procedure that works for any number of vectors in any number of dimensions.

**Worked example 3 (spotting the trap).** Can $c\mathbf{v}+d\mathbf{w} = \begin{bmatrix}3\\1\end{bmatrix}$ be solved, for $\mathbf{v}=\begin{bmatrix}2\\4\end{bmatrix}$, $\mathbf{w}=\begin{bmatrix}1\\2\end{bmatrix}$?

First the test: $v_1w_2 - v_2w_1 = 2(2) - 4(1) = 0$. Same line — so the combinations reach only that line, and the answer will be no unless the target happens to sit on it.

Concretely, $\mathbf{v}=2\mathbf{w}$, so $c\mathbf{v}+d\mathbf{w} = (2c+d)\mathbf{w}$: every combination is a multiple of $(1,2)$, i.e. a point with $y = 2x$. The target $(3,1)$ has $y=1$ but $2x=6$. Not on the line, so **no** choice of $c,d$ works.

The algebraic fingerprint of the same fact: the two component equations are $2c+d=3$ and $4c+2d=1$. The second is exactly twice the first on the left but not on the right ($2\times 3 = 6 \neq 1$) — a contradiction.

## 1.3 Solving cv + dw = b

The method has four steps, and the fourth is not optional.

1. **Expand** the left side component by component.
2. **Match components.** Two vectors are equal exactly when every corresponding component is equal, so one vector equation becomes a system of ordinary scalar equations.
3. **Solve** the system by elimination or substitution.
4. **Check** by substituting back into the original vector equation.

**Worked example 4 (the robot problem — HW 1-1 (3), on its own numbers).** Solve $c\begin{bmatrix}1\\2\end{bmatrix} + d\begin{bmatrix}3\\1\end{bmatrix} = \begin{bmatrix}14\\8\end{bmatrix}$.

*Expand:* $\begin{bmatrix}c+3d\\2c+d\end{bmatrix} = \begin{bmatrix}14\\8\end{bmatrix}$.

*Match:* $c+3d = 14$ and $2c+d = 8$.

*Solve:* multiply the second by 3 to get $6c+3d=24$, and subtract the first: $5c = 10$, so $c=2$. Back-substitute: $2(2)+d=8$, so $d=4$.

*Check:* $2\begin{bmatrix}1\\2\end{bmatrix} + 4\begin{bmatrix}3\\1\end{bmatrix} = \begin{bmatrix}2+12\\4+4\end{bmatrix} = \begin{bmatrix}14\\8\end{bmatrix}$ ✓

Step A twice and Step B four times, in any order. And because $(1,2)$ and $(3,1)$ are not multiples of each other, Fact 1 guaranteed in advance both that a solution exists and that this is the *only* one.

**Worked example 5 (three vectors in $\mathbb{R}^3$, and a staircase — the vectors of HW 1-3 (1), asked here as a solving problem rather than a combination to evaluate).** Let $\mathbf{u}=\begin{bmatrix}1\\1\\1\end{bmatrix}$, $\mathbf{v}=\begin{bmatrix}0\\1\\1\end{bmatrix}$, $\mathbf{w}=\begin{bmatrix}0\\0\\1\end{bmatrix}$. Find $a,b,c$ with $a\mathbf{u}+b\mathbf{v}+c\mathbf{w} = \begin{bmatrix}3\\4\\5\end{bmatrix}$.

Expanding gives $\begin{bmatrix}a\\a+b\\a+b+c\end{bmatrix} = \begin{bmatrix}3\\4\\5\end{bmatrix}$, i.e.

$$a = 3, \qquad a+b = 4, \qquad a+b+c = 5$$

Each equation introduces exactly one new unknown. That shape is called a **triangular** (or staircase) system, and it solves top to bottom with no rearranging: $a=3$, then $b=1$, then $c=1$. Check: $3\mathbf{u}+\mathbf{v}+\mathbf{w} = (3,4,5)$ ✓

Module 02 is largely about forcing *any* system into this shape on purpose; the procedure is called elimination.

**Worked example 6 (more equations than unknowns).** Let $\mathbf{v}=\begin{bmatrix}1\\2\\3\end{bmatrix}$ and $\mathbf{w}=\begin{bmatrix}3\\-2\\1\end{bmatrix}$ — the two vectors Midterm 2024, Problem II hands you — which fill a plane $P$ through the origin in $\mathbb{R}^3$. The test below is not one of that paper's four parts; §1.7 works the paper's own tasks on a plane of the same shape, and question C1 works them on this one — on a $\mathbf{b}$ that passes the test this example fails. Does $\mathbf{b}=\begin{bmatrix}4\\0\\5\end{bmatrix}$ lie on $P$?

The general point of $P$ is $c\mathbf{v}+d\mathbf{w} = \begin{bmatrix}c+3d\\2c-2d\\3c+d\end{bmatrix}$, so we need

$$\begin{aligned} c+3d &= 4 &&(1)\\ 2c-2d &= 0 &&(2)\\ 3c+d &= 5 &&(3) \end{aligned}$$

From (2), $c=d$. Substituting into (1): $4d=4$, so $d=1$ and $c=1$. **Now check equation (3), which has not been used yet:** $3(1)+1 = 4$, but it must equal $5$. Contradiction — so $\mathbf{b}$ does **not** lie on $P$.

This is worth pausing on. Two vectors in $\mathbb{R}^3$ give *three* component equations but only *two* unknowns. Two of the equations pin down $c$ and $d$; the third is then a genuine consistency test, which the target may pass or fail. Two vectors in $\mathbb{R}^3$ reach only a two-dimensional plane sitting inside three-dimensional space — never all of $\mathbb{R}^3$.

**Trainer.** *[What c·v + d·w can reach](#/sims/reach-of-a-combination)* — drag $c$ and $d$, then make $\mathbf{w}$ a multiple of $\mathbf{v}$ and watch every reachable point collapse onto one line.

## 1.4 Length, and the dot product inside it

Addition and scaling never answer two natural questions: *how far* did a move take us, and *do two moves meet at a right angle?* Both need a new operation — one that eats two vectors and returns a single number.

Start with distance. The arrow to $(3,4)$ is the hypotenuse of a right triangle with legs 3 and 4, so by Pythagoras its length is $\sqrt{3^2+4^2}=5$. In three dimensions, apply Pythagoras twice — once in the $v_1v_2$-plane, then again with that flat diagonal and the vertical rise as the two legs — and the pattern is clear: square the components, add, take one square root at the end.

> **Definition (length, or norm).** $\|\mathbf{v}\| = \sqrt{v_1^2+v_2^2+\cdots+v_n^2}$.

The double bars are deliberate: single bars $|\cdot|$ are reserved for the absolute value of a plain number, and the input here is a whole vector.

Now look hard at what is under that root: $v_1^2 + \cdots + v_n^2$ — each component multiplied by *itself*. What if we multiplied the matching components of two *different* vectors and added?

> **Definition (dot product).** $\mathbf{v}\cdot\mathbf{w} = v_1w_1 + v_2w_2 + \cdots + v_nw_n$, a **scalar**.

This is the first operation in the course that takes two vectors and hands back a plain number rather than a third vector — worth noticing, because the instinct built in §1.1 is that operations on vectors produce vectors.

Immediately, $\mathbf{v}\cdot\mathbf{v} = v_1^2+\cdots+v_n^2 = \|\mathbf{v}\|^2$, so

$$\|\mathbf{v}\| = \sqrt{\mathbf{v}\cdot\mathbf{v}}$$

Length and dot product are two views of one idea, and this identity gets used constantly.

**Before proving anything, compute a few.** Take $\mathbf{v}=(1,0)$ and $\mathbf{w}=(0,1)$, the two axis directions, which meet at a right angle by construction: $1(0)+0(1) = 0$. Take $\mathbf{v}=(3,4)$ and rotate it by $90°$ to get $\mathbf{w}=(4,-3)$: $3(4)+4(-3) = 0$ again. Try two vectors that are *not* perpendicular, $(1,1)$ and $(1,0)$: the answer is $1$, not zero. Two pointing nearly opposite ways, $(1,0)$ and $(-1,0)$: $-1$, negative.

A pattern has appeared before any theory: this quantity is **zero exactly when the vectors are perpendicular, positive when they point broadly the same way, negative when broadly opposite**. §1.5 turns the observation into a theorem.

> **Lemma 1 (algebraic properties of the dot product).** For all $\mathbf{v},\mathbf{w},\mathbf{u}$ in $\mathbb{R}^n$ and every scalar $c$:
> **(a)** $\mathbf{v}\cdot\mathbf{w} = \mathbf{w}\cdot\mathbf{v}$;  **(b)** $\mathbf{v}\cdot(\mathbf{w}+\mathbf{u}) = \mathbf{v}\cdot\mathbf{w} + \mathbf{v}\cdot\mathbf{u}$;  **(c)** $(c\mathbf{v})\cdot\mathbf{w} = c(\mathbf{v}\cdot\mathbf{w}) = \mathbf{v}\cdot(c\mathbf{w})$;  **(d)** $\mathbf{v}\cdot\mathbf{v}\ge 0$, and $\mathbf{v}\cdot\mathbf{v}=0$ only when $\mathbf{v}=\mathbf{0}$.

**What it means.** You may expand brackets in dot products exactly as in ordinary algebra.

**The idea in one line.** Every part is one familiar fact about ordinary multiplication of numbers, applied one component at a time.

**Proof.**

- **(a)** Each term $v_iw_i$ equals $w_iv_i$, because multiplication of numbers is commutative. Summing equal terms gives equal sums.
- **(b)** The $i$-th term on the left is $v_i(w_i+u_i)$, which equals $v_iw_i + v_iu_i$ because multiplication distributes over addition. Summing splits the sum in two: $\mathbf{v}\cdot\mathbf{w}+\mathbf{v}\cdot\mathbf{u}$.
- **(c)** The $i$-th term is $(cv_i)w_i = c(v_iw_i)$ by associativity, and a common factor $c$ pulls out of the sum. The same argument with $c$ attached to $w_i$ gives the third expression.
- **(d)** Each term $v_i^2 \ge 0$, since a real square is never negative, so the sum is $\ge 0$. A sum of non-negative numbers is zero only if every term is zero, i.e. every $v_i=0$. ∎

**Why this lemma earns its place:** it is what makes the expansion of $(\mathbf{v}-\mathbf{w})\cdot(\mathbf{v}-\mathbf{w})$ legal in the next proof — and that same expansion is the technique behind two of the harder homework problems.

**Worked example 7 (lengths, carefully).** $\mathbf{v}=\begin{bmatrix}3\\4\end{bmatrix}$: $\|\mathbf{v}\|=\sqrt{9+16}=5$. $\ \mathbf{w}=\begin{bmatrix}1\\2\\2\end{bmatrix}$: $\|\mathbf{w}\| = \sqrt{1+4+4}=3$. $\ \mathbf{a}=\begin{bmatrix}5\\-12\end{bmatrix}$: $\|\mathbf{a}\| = \sqrt{25+144}=13$ — note that the negative component squares to $+144$; length is never negative.

## 1.5 The angle formula

> **Theorem 1.** For nonzero $\mathbf{v},\mathbf{w}$ in $\mathbb{R}^n$, with $\theta$ the angle between them ($0° \le \theta \le 180°$), measured with both drawn from the origin:
> $$\mathbf{v}\cdot\mathbf{w} = \|\mathbf{v}\|\,\|\mathbf{w}\|\cos\theta$$

**What it says.** The left side is pure arithmetic — multiply matching components and add. The right side is pure geometry — two lengths and an angle. The theorem says they are always the same number. Rearranged, it computes an angle from components alone:

$$\cos\theta = \frac{\mathbf{v}\cdot\mathbf{w}}{\|\mathbf{v}\|\,\|\mathbf{w}\|}$$

**Why it matters.** Measuring an angle directly needs a picture, and there is no picture once you leave three dimensions. This converts every angle question into arithmetic, in any $\mathbb{R}^n$.

**The idea in one line.** Compute the length of the third side of the triangle twice — once with the Law of Cosines, once by expanding a dot product — and set the two answers equal.

**Proof.** Draw $\mathbf{v}$ and $\mathbf{w}$ from the origin. The origin and the two tips form a triangle whose two sides have lengths $\|\mathbf{v}\|$ and $\|\mathbf{w}\|$ meeting at angle $\theta$, and whose third side is $\|\mathbf{v}-\mathbf{w}\|$.

**Step 1 — the geometric expression.** The Law of Cosines, applied to that triangle:
$$\|\mathbf{v}-\mathbf{w}\|^2 = \|\mathbf{v}\|^2 + \|\mathbf{w}\|^2 - 2\|\mathbf{v}\|\,\|\mathbf{w}\|\cos\theta \tag{i}$$

**Step 2 — the algebraic expression.** Because $\|\mathbf{x}\|^2 = \mathbf{x}\cdot\mathbf{x}$ for every $\mathbf{x}$ (§1.4), the same quantity is $(\mathbf{v}-\mathbf{w})\cdot(\mathbf{v}-\mathbf{w})$. Expand it with Lemma 1(b),(c) exactly as you would expand $(a-b)(a-b)$:
$$\begin{aligned} (\mathbf{v}-\mathbf{w})\cdot(\mathbf{v}-\mathbf{w}) &= \mathbf{v}\cdot\mathbf{v} - \mathbf{v}\cdot\mathbf{w}\\ &\quad - \mathbf{w}\cdot\mathbf{v} + \mathbf{w}\cdot\mathbf{w} \end{aligned}$$
The two middle terms are equal by symmetry (Lemma 1a), so they combine:
$$\|\mathbf{v}-\mathbf{w}\|^2 = \|\mathbf{v}\|^2 - 2(\mathbf{v}\cdot\mathbf{w}) + \|\mathbf{w}\|^2 \tag{ii}$$

**Step 3 — set them equal.** (i) and (ii) describe the same number. Equating them, the terms $\|\mathbf{v}\|^2$ and $\|\mathbf{w}\|^2$ appear on both sides and cancel, leaving
$$-2(\mathbf{v}\cdot\mathbf{w}) = -2\|\mathbf{v}\|\,\|\mathbf{w}\|\cos\theta$$

**Step 4 — divide by $-2$.** $\mathbf{v}\cdot\mathbf{w} = \|\mathbf{v}\|\,\|\mathbf{w}\|\cos\theta$. ∎

Reproducing this proof — including the expansion in Step 2, which is the part that carries the marks — is a reasonable thing to be asked for. The Law of Cosines is taken as known from trigonometry; check that it reduces to Pythagoras at $\theta=90°$, where $\cos 90° = 0$.

**A free consequence.** Since $\cos\theta$ never leaves $[-1,1]$, the formula guarantees $|\mathbf{v}\cdot\mathbf{w}| \le \|\mathbf{v}\|\,\|\mathbf{w}\|$ — the **Cauchy–Schwarz inequality**. Recognise the name; the practical payoff is that $\cos\theta$ computed from components is always a legal cosine, so $\theta = \arccos(\cdots)$ always exists.

**Worked example 8 (an angle).** $\mathbf{v}=\begin{bmatrix}1\\0\end{bmatrix}$, $\mathbf{w}=\begin{bmatrix}1\\1\end{bmatrix}$. Dot product: $1(1)+0(1)=1$. Lengths: $\|\mathbf{v}\|=1$, $\|\mathbf{w}\|=\sqrt2$. So $\cos\theta = \dfrac{1}{\sqrt2}$ and $\theta = 45°$. Four steps, no picture, and they would run identically in $\mathbb{R}^{100}$.

**Worked example 9 (an angle with a negative component).** $\mathbf{p}=\begin{bmatrix}1\\2\end{bmatrix}$, $\mathbf{q}=\begin{bmatrix}2\\1\end{bmatrix}$: $\mathbf{p}\cdot\mathbf{q} = 4$, $\|\mathbf{p}\|=\|\mathbf{q}\|=\sqrt5$, so $\cos\theta = 4/5$ and $\theta = \arccos(0.8) \approx 36.87°$. Compare $\mathbf{p}'=\begin{bmatrix}2\\2\\-1\end{bmatrix}$ and $\mathbf{q}'=\begin{bmatrix}2\\-1\\2\end{bmatrix}$, the pair HW 1-2 (2)(a) asks about: $\mathbf{p}'\cdot\mathbf{q}' = 4-2-2 = 0$, so those two are perpendicular — the sign of each product matters, and the arithmetic is worth writing out rather than doing in your head.

**An obtuse angle, and the sign that produces it.** Every angle above came out at $90°$ or below, so every cosine was positive or zero. Take $\mathbf{r}=\begin{bmatrix}2\\1\end{bmatrix}$ and $\mathbf{s}=\begin{bmatrix}-1\\-3\end{bmatrix}$. Dot product: $2(-1)+1(-3) = -5$. Lengths: $\|\mathbf{r}\| = \sqrt{4+1} = \sqrt5$ and $\|\mathbf{s}\| = \sqrt{1+9} = \sqrt{10}$, so
$$\begin{aligned} \cos\theta &= \frac{-5}{\sqrt5\,\sqrt{10}} = \frac{-5}{\sqrt{50}} = -\frac{1}{\sqrt2}\\ \theta &= 135° \end{aligned}$$
A negative dot product forces a negative cosine, and a negative cosine puts the angle past $90°$. Carry the minus sign to the last line: dropping it turns $135°$ into $45°$, which is the same arithmetic with the geometry reversed. The angle is obtuse exactly when $\mathbf{v}\cdot\mathbf{w} < 0$, and HW 1-2 asks for one.

**Trainer.** *[The dot product, the angle, and the right-angle test](#/sims/dot-product-and-angle)* — move $\mathbf{v}$ and $\mathbf{w}$ and watch $\mathbf{v}\cdot\mathbf{w}$ pass through zero exactly as the arc reaches $90°$.

## 1.6 Perpendicularity, Pythagoras, and the parallelogram law

> **Corollary 1 (the perpendicularity test).** Two nonzero vectors are perpendicular ($\theta = 90°$, written $\mathbf{v}\perp\mathbf{w}$) if and only if $\mathbf{v}\cdot\mathbf{w}=0$.

**Proof.** Both lengths are nonzero, so by Theorem 1 the product $\|\mathbf{v}\|\|\mathbf{w}\|\cos\theta$ is zero exactly when $\cos\theta=0$, which for $0°\le\theta\le180°$ happens exactly at $\theta=90°$. ∎

This one line is the most-used fact in the module: it turns "are these at right angles?" into one arithmetic check, with no protractor and no picture.

> **Corollary 2 (Pythagoras, in vector form).** If $\mathbf{v}\perp\mathbf{w}$, then $\|\mathbf{v}+\mathbf{w}\|^2 = \|\mathbf{v}\|^2 + \|\mathbf{w}\|^2$.

**Proof.** Expand exactly as in Theorem 1's Step 2, but with a plus sign:
$$\begin{aligned} \|\mathbf{v}+\mathbf{w}\|^2 &= (\mathbf{v}+\mathbf{w})\cdot(\mathbf{v}+\mathbf{w})\\ &= \|\mathbf{v}\|^2 + 2(\mathbf{v}\cdot\mathbf{w}) + \|\mathbf{w}\|^2 \end{aligned}$$
Since $\mathbf{v}\perp\mathbf{w}$, Corollary 1 gives $\mathbf{v}\cdot\mathbf{w}=0$, so the middle term drops out. ∎

That is ordinary Pythagoras recovered as a special case: $\mathbf{v}$, the relocated $\mathbf{w}$ and the sum $\mathbf{v}+\mathbf{w}$ form a right triangle with legs $\|\mathbf{v}\|,\|\mathbf{w}\|$ and hypotenuse $\|\mathbf{v}+\mathbf{w}\|$.

**The parallelogram law.** The same expansion, run with both signs and added, proves something that holds for *every* pair of vectors — perpendicular or not:

$$\|\mathbf{v}+\mathbf{w}\|^2 + \|\mathbf{v}-\mathbf{w}\|^2 = 2\|\mathbf{v}\|^2 + 2\|\mathbf{w}\|^2$$

**Proof.** Expand each square with Lemma 1:
$$\begin{aligned} \|\mathbf{v}+\mathbf{w}\|^2 &= \|\mathbf{v}\|^2 + 2(\mathbf{v}\cdot\mathbf{w}) + \|\mathbf{w}\|^2\\ \|\mathbf{v}-\mathbf{w}\|^2 &= \|\mathbf{v}\|^2 - 2(\mathbf{v}\cdot\mathbf{w}) + \|\mathbf{w}\|^2 \end{aligned}$$
Add them: the $+2(\mathbf{v}\cdot\mathbf{w})$ and $-2(\mathbf{v}\cdot\mathbf{w})$ cancel exactly, leaving $2\|\mathbf{v}\|^2+2\|\mathbf{w}\|^2$. ∎

Geometrically: the squared diagonals of any parallelogram add up to the sum of the squares of all four sides. Notice that no numbers were chosen anywhere in that argument — that is what makes it a proof rather than a check, and it is exactly the style of answer expected when a question says "show that…" instead of "compute".

**Worked example 10 (a rectangle, and the Pythagorean check).** Let $\mathbf{v}=\begin{bmatrix}4\\-3\end{bmatrix}$ and $\mathbf{w}=\begin{bmatrix}3\\4\end{bmatrix}$ be two sides of a parallelogram drawn from the same corner. Show it is a rectangle and verify $\|\mathbf{v}\|^2+\|\mathbf{w}\|^2 = \|\mathbf{v}+\mathbf{w}\|^2$.

*Right angle:* $\mathbf{v}\cdot\mathbf{w} = 4(3)+(-3)(4) = 0$, so the two sides at that corner are perpendicular (Corollary 1). In a parallelogram opposite angles are equal and consecutive angles sum to $180°$, so all four angles are $90°$ — a rectangle.

*Lengths:* $\|\mathbf{v}\|^2 = 16+9 = 25$, $\|\mathbf{w}\|^2 = 9+16 = 25$.

*Diagonal:* $\mathbf{v}+\mathbf{w} = \begin{bmatrix}7\\1\end{bmatrix}$, so $\|\mathbf{v}+\mathbf{w}\|^2 = 49+1 = 50 = 25+25$ ✓ — exactly as Corollary 2 promises.

## 1.7 Unit vectors, normals, and the equation of a plane

Sometimes only the *direction* of a vector matters and its length is a distraction.

> **Definition (unit vector).** $\mathbf{u}$ is a unit vector if $\|\mathbf{u}\| = 1$. For any nonzero $\mathbf{v}$, the vector $\mathbf{u} = \dfrac{1}{\|\mathbf{v}\|}\mathbf{v}$ is a unit vector in the same direction as $\mathbf{v}$. Producing it is called **normalising** $\mathbf{v}$.

**Why $\mathbf{u}$ really has length 1.** First a small fact: for any scalar $c$, $\|c\mathbf{v}\| = |c|\,\|\mathbf{v}\|$, because
$$\begin{aligned} \|c\mathbf{v}\| &= \sqrt{(cv_1)^2+\cdots+(cv_n)^2}\\ &= \sqrt{c^2}\,\sqrt{v_1^2+\cdots+v_n^2} = |c|\,\|\mathbf{v}\| \end{aligned}$$
Apply it with $c = 1/\|\mathbf{v}\|$, a positive number, so $|c| = c$:
$$\|\mathbf{u}\| = \frac{1}{\|\mathbf{v}\|}\|\mathbf{v}\| = 1 \qquad ∎$$

Every component must be divided by the **same** number. Dividing one component only rotates the arrow instead of shrinking it.

**Worked example 11 (normalising).** $\mathbf{v}=\begin{bmatrix}5\\12\end{bmatrix}$: $\|\mathbf{v}\| = \sqrt{25+144} = 13$, so $\mathbf{u} = \frac{1}{13}\begin{bmatrix}5\\12\end{bmatrix} = \begin{bmatrix}5/13\\12/13\end{bmatrix}$. Check: $\left(\frac{5}{13}\right)^2+\left(\frac{12}{13}\right)^2 = \frac{169}{169}=1$ ✓

**A perpendicular vector in two dimensions.** If $\mathbf{v}=\begin{bmatrix}a\\b\end{bmatrix}$, then $\begin{bmatrix}-b\\a\end{bmatrix}$ is perpendicular to it, because $a(-b)+b(a) = 0$ for *any* $a,b$ — the cancellation is guaranteed by the algebra, not by luck. This swap-and-negate shortcut is two-dimensional only: in $\mathbb{R}^3$ there is a whole plane of directions perpendicular to a given vector, so no single formula can produce "the" one.

**Building one, and checking it.** Take $\mathbf{v}=\begin{bmatrix}5\\2\end{bmatrix}$. Swap the components and negate one of them: $\mathbf{w}=\begin{bmatrix}-2\\5\end{bmatrix}$. Check, rather than trust: $\mathbf{v}\cdot\mathbf{w} = 5(-2)+2(5) = 0$ ✓. If a unit vector is wanted as well, normalise the result: $\|\mathbf{w}\| = \sqrt{4+25} = \sqrt{29}$, so $\frac{1}{\sqrt{29}}\begin{bmatrix}-2\\5\end{bmatrix}$ is a perpendicular *unit* vector. The length need not come out whole — leave the surd rather than rounding it, and the check $\left(\frac{-2}{\sqrt{29}}\right)^2+\left(\frac{5}{\sqrt{29}}\right)^2 = \frac{29}{29}=1$ still closes exactly.

**The same task in $\mathbb{R}^3$.** Here there is no shortcut, so solve the condition itself. For $\mathbf{a}=\begin{bmatrix}3\\1\\2\end{bmatrix}$, a perpendicular $\mathbf{n}$ has to satisfy $\mathbf{n}\cdot\mathbf{a} = 3n_1+n_2+2n_3 = 0$ — one equation in three unknowns, so two of the components can be chosen freely. Choose $n_3=0$ and $n_1=1$: then $n_2=-3$ and $\mathbf{n}=\begin{bmatrix}1\\-3\\0\end{bmatrix}$, with $3(1)+(-3)+2(0) = 0$ ✓. Choose $n_1=0$ and $n_2=2$ instead: $\mathbf{n}'=\begin{bmatrix}0\\2\\-1\end{bmatrix}$, and $3(0)+2+2(-1) = 0$ ✓. Both are correct, which is the point — the answer is a whole plane of directions, not one vector. Normalise whichever you produced if the question asks for a unit vector: $\|\mathbf{n}\| = \sqrt{1+9+0} = \sqrt{10}$, giving $\frac{1}{\sqrt{10}}\begin{bmatrix}1\\-3\\0\end{bmatrix}$.

**Planes through the origin.**

> **Fact 2.** Let $\mathbf{n}$ be a nonzero vector in $\mathbb{R}^3$. The set of all $\mathbf{x}$ satisfying $\mathbf{n}\cdot\mathbf{x} = 0$, i.e. $n_1x_1+n_2x_2+n_3x_3 = 0$, forms a flat plane through the origin — precisely the vectors perpendicular to $\mathbf{n}$. We call $\mathbf{n}$ a **normal vector** to that plane.

**Why this is useful.** Suppose a plane $P$ is described the way §1.2 describes it — as all combinations $c\mathbf{v}+d\mathbf{w}$. To confirm a candidate $\mathbf{n}$ is perpendicular to the *entire* plane, it is enough to check $\mathbf{n}\cdot\mathbf{v}=0$ and $\mathbf{n}\cdot\mathbf{w}=0$. Here is why two checks cover infinitely many points — by Lemma 1(b),(c),

$$\begin{aligned} \mathbf{n}\cdot(c\mathbf{v}+d\mathbf{w}) &= c(\mathbf{n}\cdot\mathbf{v}) + d(\mathbf{n}\cdot\mathbf{w})\\ &= c(0)+d(0) = 0 \end{aligned}$$

for **every** choice of $c$ and $d$.

**Worked example 12 (exam-level: normal, unit vector, plane equation).** The vectors $\mathbf{v}=\begin{bmatrix}1\\-2\\0\end{bmatrix}$ and $\mathbf{w}=\begin{bmatrix}0\\1\\1\end{bmatrix}$ span a plane $P$ through the origin. Verify that $\mathbf{n}=\begin{bmatrix}2\\1\\-1\end{bmatrix}$ is perpendicular to $P$, find the unit vector along $\mathbf{n}$, and write the equation of $P$.

*Step 1 — check against $\mathbf{v}$:* $\mathbf{n}\cdot\mathbf{v} = 2(1)+1(-2)+(-1)(0) = 0$ ✓

*Step 2 — check against $\mathbf{w}$:* $\mathbf{n}\cdot\mathbf{w} = 2(0)+1(1)+(-1)(1) = 0$ ✓

*Step 3 — conclude for the whole plane:* by the identity above, $\mathbf{n}\cdot(c\mathbf{v}+d\mathbf{w}) = 0$ for all $c,d$, so $\mathbf{n}$ is perpendicular to every point of $P$, not merely to $\mathbf{v}$ and $\mathbf{w}$ individually. *State this reason explicitly* — an exam question that says "give the reason" is asking for exactly this line.

*Step 4 — unit vector:* $\|\mathbf{n}\| = \sqrt{4+1+1} = \sqrt6$, so the unit vector is $\frac{1}{\sqrt6}\begin{bmatrix}2\\1\\-1\end{bmatrix}$.

*Step 5 — equation of $P$:* $\mathbf{n}\cdot\mathbf{x} = 0$ reads $2x_1 + x_2 - x_3 = 0$.

*Step 6 — sanity check with the zero vector:* $\mathbf{0}$ is on $P$ both ways — directly, as $c=d=0$ in $c\mathbf{v}+d\mathbf{w}$, and through the equation, $2(0)+0-0=0$ ✓. Every plane through the origin contains $\mathbf{0}$, for exactly this reason.

## 1.8 Matrices: columns standing side by side

In §1.3 we combined three fixed vectors $\mathbf{u},\mathbf{v},\mathbf{w}$ with one recipe $(a,b,c)$. Testing a second recipe means writing all three vectors out again. If a hundred recipes have to be tested against the *same* three vectors, that is precisely the bookkeeping that vectors were invented to remove.

So store the vectors once, side by side, as the columns of a rectangular table:

$$S = \begin{bmatrix}1 & 0 & 0\\ 1 & 1 & 0\\ 1 & 1 & 1\end{bmatrix}$$

Nothing new has happened: $S$ *is* $\mathbf{u},\mathbf{v},\mathbf{w}$, redrawn next to each other instead of stacked as three separate lists — and it is the matrix HW 1-3 (1)(b) asks you to write, so that $\mathbf{b}$ becomes $S\mathbf{x}$. What is new is that a recipe can now be fed in as a second object.

> **Definition (matrix).** An $m\times n$ matrix $A$ is a rectangular array of numbers in $m$ rows and $n$ columns. The number $a_{ij}$ in row $i$, column $j$ is an **entry**. The order of the subscripts is a fixed convention — always **row first, column second**. Matrices take capital letters ($A$, $B$, $S$); vectors stay lowercase and bold.

Reading straight down column $j$ gives a vector in $\mathbb{R}^m$, written $\mathbf{a}_j$, so a matrix can equally be described as its list of columns: $A = [\,\mathbf{a}_1\ \mathbf{a}_2\ \cdots\ \mathbf{a}_n\,]$.

> **Definition (matrix–vector product).** For $A$ with columns $\mathbf{a}_1,\dots,\mathbf{a}_n$ and $\mathbf{x}$ in $\mathbb{R}^n$:
> $$A\mathbf{x} := x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n$$

$A\mathbf{x}$ is *defined* to be a linear combination of the columns of $A$, with the entries of $\mathbf{x}$ as coefficients. Everything in this course is built on reading it that way.

**Why the sizes must match.** Each entry $x_i$ needs a column $\mathbf{a}_i$ to scale, so $A$ must have exactly as many columns as $\mathbf{x}$ has components. There is no requirement at all on $m$, the number of rows: $A\mathbf{x}$ lands in $\mathbb{R}^m$ whatever $m$ is. A matrix–vector product can therefore *change the dimension* of a vector — genuinely new behaviour, since nothing in §1.1–§1.7 could change how many components a vector had.

**A second kind of matrix: running totals.** A hiker records her day-to-day *change* in altitude: $b_1$ metres on day 1, $b_2$ on day 2, and so on. Her cumulative altitudes $x_1,\dots,x_4$ satisfy $x_1 = b_1$, $x_2 - x_1 = b_2$, $x_3-x_2=b_3$, $x_4-x_3=b_4$. Moving every $x$ to the left:

$$\begin{aligned} x_1 &= b_1 & -x_1+x_2 &= b_2\\ -x_2+x_3 &= b_3 & -x_3+x_4 &= b_4 \end{aligned}$$

That whole system is one product $A\mathbf{x}=\mathbf{b}$ with

$$A = \begin{bmatrix}1&0&0&0\\-1&1&0&0\\0&-1&1&0\\0&0&-1&1\end{bmatrix}$$

This is the $4\times4$ difference equation of HW 1-3 (2), which asks for the four components and then for $A^{-1}$. $A$ turns cumulative totals into differences. The obvious next question — can we go back? — is the first glimpse of the **inverse**, and Worked example 15 answers it for this particular matrix.

## 1.9 Ax by columns and by rows

There is a second, completely different-looking way to compute the same product. Take the first row of $S$ above, read as a list $1,0,0$, and dot it against $\mathbf{x}=(3,1,1)$: $1(3)+0(1)+0(1) = 3$ — which is the first component of $S\mathbf{x}$. Row 2 gives $1(3)+1(1)+0(1)=4$; row 3 gives $5$.

> **Theorem 2.** For an $m\times n$ matrix $A$ and $\mathbf{x}$ in $\mathbb{R}^n$, the $i$-th component of $A\mathbf{x}$ is
> $$(A\mathbf{x})_i = a_{i1}x_1 + a_{i2}x_2 + \cdots + a_{in}x_n$$
> — the dot product of row $i$ of $A$ with $\mathbf{x}$.

**What it means.** Two recipes, one answer. Scale-and-add the **columns** (the definition), or dot each **row** against $\mathbf{x}$ (this theorem). They are not rival methods to choose between; they provably agree.

**Why it matters in practice.** The column view is how you *reason* about $A\mathbf{x}$ — it connects directly to linear combinations, the central idea of the course. The row view is how you *compute* $A\mathbf{x}$ by hand, one output number at a time. Having both means every product comes with a free, independent check: compute one way, verify the other. Use it — HW 2-1 asks for exactly this, both ways, on the same product.

**Why it is true, in one line.** $A\mathbf{x}$ is a sum of scaled columns, and taking the $i$-th component of a sum of vectors just adds up the $i$-th components — which are precisely the entries of row $i$.

::: details Full derivation of Theorem 2
By definition, $A\mathbf{x} = x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n$. This is a sum of vectors, and vectors add component by component (§1.1), so the $i$-th component of the sum is the sum of the $i$-th components of the pieces:

$$(A\mathbf{x})_i = x_1(\mathbf{a}_1)_i + x_2(\mathbf{a}_2)_i + \cdots + x_n(\mathbf{a}_n)_i$$

Now $(\mathbf{a}_j)_i$ — "the $i$-th component of the $j$-th column" — is by definition the entry sitting in row $i$, column $j$, which is $a_{ij}$. Substituting:

$$\begin{aligned} (A\mathbf{x})_i &= x_1a_{i1} + x_2a_{i2} + \cdots + x_na_{in}\\ &= a_{i1}x_1 + a_{i2}x_2 + \cdots + a_{in}x_n \end{aligned}$$

The last step only reorders each product, which is harmless for ordinary numbers. ∎
:::

**Worked example 13 (both views, side by side).** $A = \begin{bmatrix}2&1\\0&3\end{bmatrix}$, $\mathbf{x}=\begin{bmatrix}4\\2\end{bmatrix}$.

*Columns:* $A\mathbf{x} = 4\begin{bmatrix}2\\0\end{bmatrix} + 2\begin{bmatrix}1\\3\end{bmatrix} = \begin{bmatrix}8\\0\end{bmatrix}+\begin{bmatrix}2\\6\end{bmatrix} = \begin{bmatrix}10\\6\end{bmatrix}$.

*Rows, as a check:* row 1 is $2,1$: $2(4)+1(2) = 10$. Row 2 is $0,3$: $0(4)+3(2)=6$. Same vector ✓

**Worked example 14 (a non-square matrix).** $A = \begin{bmatrix}1&2\\3&0\\-1&4\end{bmatrix}$ (which is $3\times 2$), $\mathbf{x} = \begin{bmatrix}2\\3\end{bmatrix}$.

*Columns:* $2\begin{bmatrix}1\\3\\-1\end{bmatrix}+3\begin{bmatrix}2\\0\\4\end{bmatrix} = \begin{bmatrix}2\\6\\-2\end{bmatrix}+\begin{bmatrix}6\\0\\12\end{bmatrix} = \begin{bmatrix}8\\6\\10\end{bmatrix}$.

*Rows:* $1(2)+2(3)=8$; $3(2)+0(3)=6$; $-1(2)+4(3)=10$ ✓

$A$ has 2 columns and $\mathbf{x}$ has 2 components, so the product is legal — but the output lives in $\mathbb{R}^3$. The input dimension and the output dimension are different, and that is normal.

**Worked example 15 (the difference matrix, and a first inverse).** A hiker's daily changes are $\mathbf{b} = \begin{bmatrix}100\\50\\-30\\20\end{bmatrix}$. Solve $A\mathbf{x}=\mathbf{b}$ for the cumulative altitudes, with $A$ the difference matrix from §1.8, and then find the matrix that reverses the process.

*Step 1 — write the row equations (Theorem 2):* $x_1 = 100$; $-x_1+x_2 = 50$; $-x_2+x_3 = -30$; $-x_3+x_4 = 20$.

*Step 2 — solve top to bottom:* $x_1 = 100$, $x_2 = 150$, $x_3 = 120$, $x_4 = 140$.

*Step 3 — check by the column view:* $100\begin{bmatrix}1\\-1\\0\\0\end{bmatrix}+150\begin{bmatrix}0\\1\\-1\\0\end{bmatrix}+120\begin{bmatrix}0\\0\\1\\-1\end{bmatrix}+140\begin{bmatrix}0\\0\\0\\1\end{bmatrix}$ has components $100$, $-100+150=50$, $-150+120=-30$, $-120+140=20$ — exactly $\mathbf{b}$ ✓

*Step 4 — name the reverse matrix.* Look at the solution: $x_1 = b_1$, $x_2 = b_1+b_2$, $x_3=b_1+b_2+b_3$, $x_4 = b_1+b_2+b_3+b_4$. Each $x_i$ is a **running total**, and that rule is itself a matrix–vector product:

$$A^{-1} = \begin{bmatrix}1&0&0&0\\1&1&0&0\\1&1&1&0\\1&1&1&1\end{bmatrix}$$

$A$ turns cumulative values into differences; $A^{-1}$ turns differences back into cumulative values. Each undoes the other.

> **Fact 3 (informally, for now).** If $A$ is square and some matrix $A^{-1}$ satisfies $A^{-1}(A\mathbf{x}) = \mathbf{x}$ for every $\mathbf{x}$, then $A\mathbf{x}=\mathbf{b}$ is solved directly by $\mathbf{x} = A^{-1}\mathbf{b}$.

This is stated informally because multiplying two *matrices* is not defined until Module 02, so there is nothing yet with which to write a general formula for $A^{-1}$ or to say when one exists. What Worked example 15 shows is that for some matrices the undo pattern can simply be read off the answer. Module 02 turns that observation into Gauss–Jordan elimination, which finds $A^{-1}$ for any invertible matrix, staircase-shaped or not.

**Worked example 16 (exam-level: solving $A\mathbf{x}=\mathbf{b}$ that is not a staircase).** $A = \begin{bmatrix}2&1&0\\1&3&1\\0&1&2\end{bmatrix}$, $\mathbf{b} = \begin{bmatrix}3\\7\\7\end{bmatrix}$.

*Row equations:* $2x_1+x_2 = 3$ (1); $x_1+3x_2+x_3 = 7$ (2); $x_2+2x_3 = 7$ (3).

Unlike example 15, no equation hands you a variable for free. Solve (1) for $x_2 = 3-2x_1$, substitute into (3): $(3-2x_1)+2x_3 = 7 \Rightarrow x_3 = 2+x_1$. Substitute both into (2):

$$\begin{aligned} x_1 + 3(3-2x_1) + (2+x_1) &= 7\\ -4x_1 + 11 &= 7 \implies x_1 = 1 \end{aligned}$$

Then $x_2 = 1$, $x_3 = 3$.

*Verify with the column view:* $1\begin{bmatrix}2\\1\\0\end{bmatrix}+1\begin{bmatrix}1\\3\\1\end{bmatrix}+3\begin{bmatrix}0\\1\\2\end{bmatrix} = \begin{bmatrix}3\\7\\7\end{bmatrix} = \mathbf{b}$ ✓

Notice how much shuffling that took compared with the staircase in example 15. Module 02's elimination is exactly the procedure that forces any system into staircase shape first, so that solving becomes mechanical rather than improvised.

**Trainer.** *[Ax: columns and rows](#/sims/ax-columns-and-rows)* — change $A$ and $\mathbf{x}$ and watch the column combination and the row dot products stay equal, which is Theorem 2 happening in front of you.

## Common mistakes

These are the errors that actually cost marks on this material.

- **Adding a scalar to a vector.** $\mathbf{v}+3$ has no meaning. Scaling is $3\mathbf{v}$, which multiplies *every* component by 3.
- **Adding vectors of different sizes.** Addition is defined only when both vectors have the same number of components. Check first.
- **Sign errors in subtraction.** $\mathbf{v}-\mathbf{w}$ means $\mathbf{v}+(-1)\mathbf{w}$, so the minus reaches every component of $\mathbf{w}$: $\begin{bmatrix}5\\1\end{bmatrix}-\begin{bmatrix}1\\5\end{bmatrix} = \begin{bmatrix}4\\-4\end{bmatrix}$, not $\begin{bmatrix}4\\4\end{bmatrix}$.
- **Assuming any two vectors reach every point.** Test whether one is a multiple of the other ($v_1w_2-v_2w_1=0$ in the plane) *before* hunting for coefficients that may not exist.
- **Losing track of which coefficient belongs to which vector.** Always write the expansion step out in full before matching components; do not match "in your head".
- **Expecting the dot product to return a vector.** $\mathbf{v}\cdot\mathbf{w}$ is a plain number. It distributes correctly (Lemma 1b), but the result is never something you can then add to a vector.
- **Dropping a sign in a dot product.** For $\mathbf{v}=(4,-3)$, $\mathbf{w}=(3,4)$: $4(3)+(-3)(4) = 0$, not $24$. Write each product down when negatives are present.
- **Reading $\mathbf{v}\cdot\mathbf{w}=0$ as "one of them is zero".** It means *perpendicular*. $(1,0)\cdot(0,1)=0$ with neither vector zero.
- **Forgetting to divide by the lengths when finding an angle.** $\cos\theta = \dfrac{\mathbf{v}\cdot\mathbf{w}}{\|\mathbf{v}\|\|\mathbf{w}\|}$, never $\mathbf{v}\cdot\mathbf{w}$ alone — doubling $\mathbf{v}$ doubles the dot product without changing the angle at all.
- **Normalising by dividing one component.** Every component is divided by the same $\|\mathbf{v}\|$; dividing one rotates the arrow instead of shrinking it.
- **Expecting swap-and-negate to work in $\mathbb{R}^3$.** In three dimensions a whole plane of vectors is perpendicular to a given one; solve $\mathbf{n}\cdot\mathbf{v}=0$ directly instead.
- **Mismatching $A$ and $\mathbf{x}$.** The number of *columns* of $A$ must equal the number of components of $\mathbf{x}$. The number of rows is unrestricted and sets the size of the output.
- **Reading $a_{ij}$ as "column $i$, row $j$".** The convention is row first, column second, and every later formula depends on it.
- **Assuming $A\mathbf{x}$ has as many components as $\mathbf{x}$.** It has as many components as $A$ has rows.
- **Writing $\mathbf{x}A$ instead of $A\mathbf{x}$.** Matrix on the left, vector on the right. In Module 02 order genuinely changes the answer, so build the habit now.
- **Skipping the check.** Theorem 2 gives a free, independent verification: solve by rows, then recompute by columns (or the reverse).

## Check yourself

1. Write $c\mathbf{v}+d\mathbf{w}$ in components for $\mathbf{v}=\begin{bmatrix}3\\-1\end{bmatrix}$, $\mathbf{w}=\begin{bmatrix}-2\\4\end{bmatrix}$, then compute $2\mathbf{v}-3\mathbf{w}$.
2. Decide, without solving, whether $c\begin{bmatrix}2\\6\end{bmatrix}+d\begin{bmatrix}-1\\-3\end{bmatrix} = \begin{bmatrix}4\\5\end{bmatrix}$ has a solution. Give your reason.
3. Find $c$ and $d$ with $c\begin{bmatrix}2\\5\end{bmatrix}+d\begin{bmatrix}-1\\3\end{bmatrix} = \begin{bmatrix}9\\4\end{bmatrix}$, and check your answer.
4. Compute $\|\mathbf{a}\|$ for $\mathbf{a}=\begin{bmatrix}5\\-12\end{bmatrix}$, and the unit vector in the direction of $\begin{bmatrix}8\\15\end{bmatrix}$.
5. Find the cosine of the angle between $\begin{bmatrix}2\\2\\-1\end{bmatrix}$ and $\begin{bmatrix}2\\-1\\2\end{bmatrix}$, and say what the answer tells you.
6. Prove that the parallelogram with sides $\mathbf{v}=\begin{bmatrix}6\\2\end{bmatrix}$ and $\mathbf{w}=\begin{bmatrix}-1\\3\end{bmatrix}$ is a rectangle, and verify $\|\mathbf{v}\|^2+\|\mathbf{w}\|^2 = \|\mathbf{v}+\mathbf{w}\|^2$.
7. The vectors $\mathbf{v}=\begin{bmatrix}2\\1\\0\end{bmatrix}$ and $\mathbf{w}=\begin{bmatrix}0\\1\\2\end{bmatrix}$ span a plane $P$ through the origin. Verify that $\mathbf{n}=\begin{bmatrix}1\\-2\\1\end{bmatrix}$ is perpendicular to *every* point of $P$ — and state why two checks suffice. Then give the unit vector along $\mathbf{n}$ and the equation of $P$.
8. Compute $A\mathbf{x}$ both ways for $A = \begin{bmatrix}1&-1&2\\0&3&1\end{bmatrix}$, $\mathbf{x} = \begin{bmatrix}2\\1\\3\end{bmatrix}$, and state how many components the answer has and why.
9. Solve $A\mathbf{x}=\mathbf{b}$ for $A = \begin{bmatrix}1&1&0\\0&2&1\\1&0&3\end{bmatrix}$, $\mathbf{b}=\begin{bmatrix}3\\6\\14\end{bmatrix}$, using the row view, then verify with the column view.

---

### Answers to "Check yourself"

**1.** $c\mathbf{v}+d\mathbf{w} = \begin{bmatrix}3c-2d\\-c+4d\end{bmatrix}$. With $c=2$, $d=-3$: $2\mathbf{v} = \begin{bmatrix}6\\-2\end{bmatrix}$, $3\mathbf{w} = \begin{bmatrix}-6\\12\end{bmatrix}$, so $2\mathbf{v}-3\mathbf{w} = \begin{bmatrix}12\\-14\end{bmatrix}$.

**2.** No solution. The test: $v_1w_2-v_2w_1 = 2(-3)-6(-1) = 0$, so the two vectors lie on one line ($\mathbf{w} = -\tfrac12\mathbf{v}$) and every combination is a multiple of $(1,3)$ — points with $y=3x$. The target has $y=5$ but $3x = 12$, so it is off that line.

**3.** Expanding gives $2c-d = 9$ and $5c+3d = 4$. Multiply the first by 3: $6c-3d = 27$; add to the second: $11c = 31$, so $c = \tfrac{31}{11}$ and $d = 2c-9 = -\tfrac{37}{11}$. Check (multiplying through by 11): first component $2(31)-(-37) = 99 = 11\times 9$ ✓; second $5(31)+3(-37) = 44 = 11\times 4$ ✓. Coefficients need not be whole numbers — the method does not care.

**4.** $\|\mathbf{a}\| = \sqrt{25+144} = 13$. For $\begin{bmatrix}8\\15\end{bmatrix}$: length $\sqrt{64+225} = 17$, unit vector $\begin{bmatrix}8/17\\15/17\end{bmatrix}$, and $\left(\tfrac{8}{17}\right)^2+\left(\tfrac{15}{17}\right)^2 = 1$ ✓

**5.** Dot product $= 4-2-2 = 0$, so $\cos\theta = 0$ and $\theta = 90°$: the vectors are perpendicular (Corollary 1). Note both are nonzero — a zero dot product says nothing about either vector being zero.

**6.** $\mathbf{v}\cdot\mathbf{w} = 6(-1)+2(3) = 0$, so the sides at that corner are perpendicular and the parallelogram is a rectangle. $\|\mathbf{v}\|^2 = 36+4 = 40$; $\|\mathbf{w}\|^2 = 1+9 = 10$; $\mathbf{v}+\mathbf{w} = \begin{bmatrix}5\\5\end{bmatrix}$, so $\|\mathbf{v}+\mathbf{w}\|^2 = 50 = 40+10$ ✓

**7.** $\mathbf{n}\cdot\mathbf{v} = 2-2+0 = 0$ and $\mathbf{n}\cdot\mathbf{w} = 0-2+2 = 0$. Two checks suffice because $\mathbf{n}\cdot(c\mathbf{v}+d\mathbf{w}) = c(\mathbf{n}\cdot\mathbf{v})+d(\mathbf{n}\cdot\mathbf{w}) = 0$ for every $c,d$ (Lemma 1b,c), and every point of $P$ has that form. $\|\mathbf{n}\| = \sqrt{1+4+1} = \sqrt6$, so the unit vector is $\frac{1}{\sqrt6}\begin{bmatrix}1\\-2\\1\end{bmatrix}$, and the plane is $x_1-2x_2+x_3 = 0$.

**8.** Columns: $2\begin{bmatrix}1\\0\end{bmatrix}+1\begin{bmatrix}-1\\3\end{bmatrix}+3\begin{bmatrix}2\\1\end{bmatrix} = \begin{bmatrix}7\\6\end{bmatrix}$. Rows: $1(2)+(-1)(1)+2(3) = 7$; $0(2)+3(1)+1(3) = 6$ ✓ The answer has **2** components, because $A$ has 2 rows — even though $\mathbf{x}$ had 3.

**9.** Row equations: $x_1+x_2 = 3$ (1); $2x_2+x_3 = 6$ (2); $x_1+3x_3 = 14$ (3). From (1), $x_1 = 3-x_2$; substituting into (3): $-x_2+3x_3 = 11$, so $x_2 = 3x_3-11$. Into (2): $2(3x_3-11)+x_3 = 6 \Rightarrow 7x_3 = 28 \Rightarrow x_3 = 4$. Then $x_2 = 1$ and $x_1 = 2$. Column check: $2\begin{bmatrix}1\\0\\1\end{bmatrix}+1\begin{bmatrix}1\\2\\0\end{bmatrix}+4\begin{bmatrix}0\\1\\3\end{bmatrix} = \begin{bmatrix}3\\6\\14\end{bmatrix}$ ✓

---

> *Independent study guide for a first course in Linear Algebra. Every worked example and every practice question is written for this course. Where a problem from a past paper or a homework sheet is worked through, it is named where it appears — those papers are the student's own course materials, and they are quoted to show how the method applies to them, never passed off as this course's own. Not affiliated with or endorsed by any university or instructor, and not endorsed by Strang's Introduction to Linear Algebra, which it follows as a reference.*
