# Readiness check

This page asks questions; it does not teach. Work down it with a pen and answer each item honestly — either you can do the thing on paper, or you cannot do it yet. Nothing is scored. Every item you cannot answer names the section that teaches it, so a run through this page produces a reading list rather than a mark.

There are three moments it is worth using:

- **Before you start**, to see what the course actually asks you to be able to do.
- **After a module**, to find out which parts of it stayed.
- **Before a paper**, top to bottom in twenty minutes, as a last sweep.

Two rules keep it honest. An item counts as "yes" only if you could carry it out with nothing open in front of you — recognising a method is not the same as running it. And take a module's items in order: most of them stand on the ones above.

Each module also ends with a **Check yourself** set: full problems, with worked answers. This page is the faster instrument: it tells you *which* of those to go back to.

The algebra assumed before Module 01 — fractions, linear equations, quadratics, slopes, reading notation — is checked by the self-test at the end of this page. Start there if you are not sure of it.

---

## Module 01 — Vectors, Length and Matrices

1. **Can you** write $c\mathbf{v}+d\mathbf{w}$ out in components, and say what all those combinations reach when $\mathbf{v}$ and $\mathbf{w}$ are not parallel, and what they reach when they are?
   - *If not:* [§1.1](#/ch01/learn) and [§1.2](#/ch01/learn), then draw both cases once by hand.
2. **Can you** decide *before* solving whether $c\mathbf{v}+d\mathbf{w}=\mathbf{b}$ has a solution at all, and then find $c$ and $d$?
   - *If not:* [§1.3](#/ch01/learn) — the test comes first, the algebra second.
3. **Can you** compute a length and a dot product from components, and get the angle between two vectors from them?
   - *If not:* [§1.4](#/ch01/learn) and [§1.5](#/ch01/learn), then redo one example with an obtuse angle so the negative cosine is not a surprise.
4. **Can you** say what a dot product of zero does mean, and what it does **not** mean?
   - *If not:* [§1.6](#/ch01/learn). The instinct carried over from ordinary numbers is the one to break here.
5. **Can you** produce a unit vector in a given direction, find a normal to the plane spanned by two vectors, verify the normal with two dot products, and write the plane's equation?
   - *If not:* [§1.7](#/ch01/learn). This is Midterm 2024, Problem II, all four parts, so it is worth being fluent rather than correct-eventually.
6. **Can you** compute $A\mathbf{x}$ by columns and by rows, and say how many components the answer has and why?
   - *If not:* [§1.8](#/ch01/learn) and [§1.9](#/ch01/learn). Do one product both ways every time until the check is automatic.

## Module 02 — Elimination, Inverses and $A=LU$

1. **Can you** describe both pictures of $A\mathbf{x}=\mathbf{b}$ — the rows and the columns — and say which question each one answers?
   - *If not:* [§2.1](#/ch02/learn) and [§2.2](#/ch02/learn). The two pictures are asked about directly, and they also decide what "no solution" looks like.
2. **Can you** run forward elimination on a $3\times3$ system, writing down each multiplier as you form it, and then back-substitute?
   - *If not:* [§2.3](#/ch02/learn) and [§2.4](#/ch02/learn), then solve one system end to end and substitute the answer into the original equations.
3. **Can you** say what a zero in a pivot position means, what to try, and how to tell the repairable case from the singular one?
   - *If not:* [§2.5](#/ch02/learn). The Model Test and the final exam each put one in the way.
4. **Can you** multiply two matrices by the row-times-column rule and check the same product by columns, and state which of the algebra rules survive for matrices and which do not?
   - *If not:* [§2.6](#/ch02/learn) and [§2.9](#/ch02/learn). If you cannot produce a counterexample from memory, that rule is not yet yours.
5. **Can you** invert a $3\times3$ matrix by elimination on the augmented block, use the $2\times2$ shortcut, and say in advance whether an inverse exists?
   - *If not:* [§2.11](#/ch02/learn) for the procedure, [§2.12](#/ch02/learn) for existence, [§2.13](#/ch02/learn) for the shortcut and for the order rule when a product is inverted. Verify every inverse you produce by multiplying, both ways round.
6. **Can you** recover $L$ from an elimination you have already done, check $LU$ against $A$, and then solve with $L$ and $U$ instead of starting again?
   - *If not:* [§2.14](#/ch02/learn) and [§2.15](#/ch02/learn). Midterm 2024, Problem III asks for the elimination, the inverse and the factorisation of one matrix, in that order — the third part is free if you kept the multipliers.
7. **Can you** transpose a product without getting the order wrong, and say what makes a matrix symmetric?
   - *If not:* [§2.16](#/ch02/learn). Midterm 2024, Problem I.2 hands you a transpose and asks for a product built from it.
8. **Can you** say what changes when a row exchange is unavoidable, and solve the system that results?
   - *If not:* [§2.17](#/ch02/learn). Reordering the matrix and forgetting to reorder the right-hand side is the standard way to lose these marks.

## Module 03 — Determinants

1. **Can you** state the three properties that define the determinant, without a formula?
   - *If not:* [§3.1](#/ch03/learn). Everything else in the module is derived from those three, so they are the cheapest thing to memorise.
2. **Can you** look at a matrix and write down $\det = 0$ with no arithmetic, in each of the situations that allow it?
   - *If not:* [§3.2](#/ch03/learn). Final 2024, Problem II turns entirely on spotting one of them.
3. **Can you** compute a determinant of any size by elimination, keeping count of the row exchanges?
   - *If not:* [§3.3](#/ch03/learn) and [§3.4](#/ch03/learn). Counting the exchanges is the step that gets skipped; write the count down as it happens, not afterwards.
4. **Can you** expand along a row or a column by cofactors, choosing the line that costs least, and get the signs right?
   - *If not:* [§3.8](#/ch03/learn) and [§3.9](#/ch03/learn). Take the sign after the minor, never before it.
5. **Can you** use $\det(AB)$, $\det(A^{-1})$ and $\det(A^{\mathsf T})$ without deriving them, and say which familiar rule has no determinant analogue?
   - *If not:* [§3.5](#/ch03/learn) and [§3.6](#/ch03/learn) for invertibility and products, [§3.9](#/ch03/learn) for the transpose.
6. **Can you** state the identity that relates $A$ to its cofactor matrix, use it to find $\det(C)$, and quote the hypothesis it needs before you use it?
   - *If not:* [§3.10](#/ch03/learn) and [§3.11](#/ch03/learn). Final 2024, Problem II.2 is exactly this, on a matrix that fails the hypothesis — the marks are in noticing.
7. **Can you** solve a small system by Cramer's rule, and find an area, a triangle's area and a volume from a determinant?
   - *If not:* [§3.12](#/ch03/learn) and [§3.13](#/ch03/learn).

## Module 04 — Vector Spaces, Rank and the Complete Solution

1. **Can you** run the three-part subspace test on a set given by an equation, and name which part fails when one does?
   - *If not:* [§4.2](#/ch04/learn). Testing the zero vector first settles most of these in one line.
2. **Can you** say which space the column space lives in, which space the nullspace lives in, and why they are not interchangeable?
   - *If not:* [§4.3](#/ch04/learn) and [§4.4](#/ch04/learn). Getting these two the wrong way round costs the rest of the question.
3. **Can you** reduce a matrix to echelon form and then to the fully reduced form, read off the rank, and say how many free variables there are before solving anything?
   - *If not:* [§4.5](#/ch04/learn) and [§4.7](#/ch04/learn). The count is columns minus rank — never rows minus rank.
4. **Can you** write down the special solutions and state the whole nullspace from them?
   - *If not:* [§4.6](#/ch04/learn) and [§4.7](#/ch04/learn). The sign change when a pivot variable is solved for is the step to slow down on.
5. **Can you** decide whether $A\mathbf{x}=\mathbf{b}$ is consistent, and find the value of an unknown constant that makes it consistent?
   - *If not:* [§4.8](#/ch04/learn). This is Final 2024, Problem III.1, and the marks are in the row that reduces to zeros.
6. **Can you** assemble the complete solution as one particular solution plus the nullspace, and verify both halves against the original matrix?
   - *If not:* [§4.9](#/ch04/learn), with the four existence-and-uniqueness cases in [§4.10](#/ch04/learn).
7. **Can you** test a list of vectors for independence, pick out a maximal independent subset, and write down the dependence that the discarded vectors satisfy?
   - *If not:* [§4.11](#/ch04/learn), and [§4.13](#/ch04/learn) for the distinction between spanning and being a basis. Model Test, Problem 4 asks for the subset.
8. **Can you** give a basis and a dimension for all three spaces from one reduction, taking each basis from the right matrix?
   - *If not:* [§4.14](#/ch04/learn).

## Module 05 — Eigenvalues and Eigenvectors

1. **Can you** state the eigenvalue equation with the condition on the vector that makes it mean anything, and turn it into a question about a nullspace?
   - *If not:* [§5.1](#/ch05/learn) and [§5.2](#/ch05/learn).
2. **Can you** write down the characteristic equation of a $2\times2$ matrix and solve it, from its trace and determinant rather than by expanding a symbolic determinant?
   - *If not:* [§5.3](#/ch05/learn) for the equation, [§5.4](#/ch05/learn) for the two numbers that write it down for you.
3. **Can you** check a list of eigenvalues against the trace and the determinant — and say what that check assumes, and what you do when a $2\times2$ matrix has a negative discriminant?
   - *If not:* [§5.4](#/ch05/learn). The identity is about *real* eigenvalues; a matrix with none still has a trace and a determinant, and Model Test 1(2) is such a matrix.
4. **Can you** read the eigenvalues off a triangular matrix, and say what it means when zero is one of them?
   - *If not:* [§5.5](#/ch05/learn), with the $3\times3$ case in [§5.6](#/ch05/learn).
5. **Can you** find every eigenvector for a given eigenvalue, know that a free variable has to appear, and decide whether the answer is a line or a plane?
   - *If not:* [§5.7](#/ch05/learn) and [§5.8](#/ch05/learn). Multiplicity does not settle the count on its own.
6. **Can you** describe what an eigenvalue does geometrically from its sign and its size?
   - *If not:* [§5.9](#/ch05/learn).
7. **Can you** write out, from memory and with every step named, the proof that an eigenvector of $A$ is an eigenvector of $A^2$?
   - *If not:* [§5.10](#/ch05/learn). It is the one written proof in the whole bank — Final 2024, Problem I.1 — and it is five lines long.
8. **Can you** apply a power or a polynomial of $A$ to a known eigenvector, and compute such a polynomial when the matrix has no real eigenvalues to work with?
   - *If not:* [§5.11](#/ch05/learn).
9. **Can you** say why $AB$ and $BA$ have the same eigenvalues, and why that does not make them equal?
   - *If not:* [§5.12](#/ch05/learn).

---

## What "ready" means for these papers

Three papers stand behind this course: the Model Test for the mid-term, the Linear Algebra Midterm 2024 and the Linear Algebra Final Exam 2024. Between them they set twenty-three numbered items. Twenty-two are computations — multiply these matrices, eliminate and back-substitute, invert, reduce and give the rank, solve the system, find the eigenvalues and eigenvectors. Exactly one asks for prose: Final 2024, Problem I.1, which asks you to *prove* that an eigenvector of $A$ is an eigenvector of $A^2$.

Readiness for this bank is therefore not the ability to recite theory. It is the ability to carry a standard procedure to the end by hand, without a calculator, and to check the result. Three things follow from the papers themselves.

**The same tasks come back.** Matrix multiplication appears on all three papers; elimination appears on all three — to an upper system on one, to echelon form with a rank or a free variable on the other two; an inverse is asked for on two. Which card covers which problem is set out on the other free page, the [Index and exam map](#/docs/exam-map).

**Each paper hides one assumption worth testing before you compute.** The Model Test asks for a polynomial in a matrix whose characteristic polynomial has no real roots, so the shortcut most students reach for has nothing to work with. The final exam's determinant problem is built on a singular matrix, which is the case the usual identity excludes. Both reward an answer that checks first.

**Checking is part of the method, not an extra.** Substituting a solution back into the original equations, multiplying a claimed inverse out both ways, matching a list of eigenvalues against the trace and the determinant — each costs under a minute, and each catches the arithmetic slip that would otherwise take a whole item down.

If every item above is a yes, these three papers hold no surprises. If most are, the pointers you collected are your revision order: start with the earliest module you said no in, because the later items stand on the earlier ones.

---

## Appendix — the algebra this course assumes

Everything above is linear algebra. This appendix is not: it checks the arithmetic and algebra the lessons build directly on top of, and it is worth half an hour before Module 01 if school mathematics is a while behind you. You are not expected to know any linear algebra to sit it.

Work through all 18 problems **without a calculator**, about 30–40 minutes. Write your working, not just answers: the point is to find gaps, not to get a score. Then check against the solutions, and read the interpretation table at the end.

---

### Part 1 — Problem set

#### Section A · Fractions and signed-number arithmetic

**A1.** Compute $\dfrac{2}{3}+\dfrac{5}{6}$.

**A2.** Compute $(-4)\left(\dfrac{3}{2}\right)-7$.

**A3.** Simplify $\dfrac{2}{5} \div \dfrac{4}{15}$.

#### Section B · Solving linear equations

**B1.** Solve for $x$: $3x-7 = 2x+5$.

**B2.** Solve for $x$: $2(x+3)-5 = 3(x-1)$.

**B3.** Solve for $x$: $\dfrac{x}{2}+\dfrac{x}{3} = 5$.

#### Section C · Systems of two linear equations

**C1.** Solve: $2x+y = 7$ and $x-y = 2$.

**C2.** Solve: $3x+2y = 16$ and $x-y = 2$.

#### Section D · Quadratic equations

**D1.** Solve by factoring: $x^2-5x+6 = 0$.

**D2.** Solve with the quadratic formula, leaving the answer in simplified radical form: $x^2-4x-1 = 0$.

**D3.** Solve: $x^2-9 = 0$.

#### Section E · Functions, graphs and lines

**E1.** Find the slope of the line through $(1,2)$ and $(4,8)$.

**E2.** Write the equation of the line with slope $3$ through $(0,-2)$.

**E3.** If $f(x) = 2x^2-3x+1$, compute $f(-1)$.

#### Section F · Exponents and algebraic manipulation

**F1.** Simplify $(2x^2y)(3xy^3)$.

**F2.** Expand $(a+b)^2$.

#### Section G · Basic mathematical reasoning

For each statement, say whether it is **true** or **false**, and justify your answer in one or two sentences.

**G1.** If $a\cdot b = 0$ for real numbers $a$ and $b$, then $a=0$ or $b=0$.

**G2.** Every linear equation $ax+b=0$ with $a \ne 0$ has exactly one solution.

---

### Part 2 — Concept check

Pick one answer per question.

**Q1.** Which best describes a "variable"?
(a) A fixed number, like 7 (b) A symbol such as $x$ or $y$ that can stand for different numbers (c) A mathematical operation, like addition (d) A type of equation

**Q2.** The equation $2x+3 = 2x+5$ has:
(a) exactly one solution (b) no solution (c) infinitely many solutions (d) exactly two solutions

**Q3.** The equation $2(x+1) = 2x+2$ has:
(a) exactly one solution (b) no solution (c) infinitely many solutions (d) exactly two solutions

**Q4.** A function $f(x)$ is a rule that assigns:
(a) exactly one output to each input (b) several possible outputs to each input (c) one input to each output (d) nothing in particular — "function" just means "equation"

**Q5.** On the coordinate plane, the graph of $y=2$ (for all $x$) is:
(a) a single point (b) a vertical line (c) a horizontal line (d) not a valid graph

**Q6.** Two distinct lines with the same slope are:
(a) perpendicular (b) parallel, and they never intersect (c) guaranteed to be the same line (d) guaranteed to intersect at exactly one point

**Q7.** Which set includes fractions like $3/4$ but not numbers like $\sqrt2$?
(a) integers (b) rational numbers (c) irrational numbers (d) natural numbers

**Q8.** In the expression $3x^2$, the number 3 is called the:
(a) variable (b) exponent (c) coefficient (d) constant term

---

### Part 3 — Confidence checklist

Rate your comfort with each skill from **1** (not at all) to **5** (very comfortable). Not graded — this is for your own planning.

| Skill | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Adding, subtracting, multiplying, dividing fractions | | | | | |
| Solving an equation like $3x-7 = 2x+5$ | | | | | |
| Solving a system of two equations in two unknowns | | | | | |
| Factoring a quadratic expression | | | | | |
| Plotting points and lines on a coordinate plane | | | | | |
| Working with negative numbers and absolute values | | | | | |
| Following a multi-step logical argument (a short proof) | | | | | |
| Reading mathematical notation (subscripts, sums, set notation) | | | | | |

Anything rated **2 or lower** is worth a quick refresher before you start, regardless of your problem-set score — a low confidence rating usually means the skill has not been practised recently, even if you technically remember the mechanics.

---

### Solutions — Part 1

**A1.** Common denominator 6: $\dfrac{4}{6}+\dfrac{5}{6} = \dfrac{9}{6} = \dfrac{3}{2}$.

**A2.** $(-4)\left(\dfrac{3}{2}\right) = -6$, so $-6-7 = -13$.

**A3.** Dividing by a fraction means multiplying by its reciprocal: $\dfrac{2}{5}\times\dfrac{15}{4} = \dfrac{30}{20} = \dfrac{3}{2}$.

**B1.** $3x-7 = 2x+5 \Rightarrow 3x-2x = 5+7 \Rightarrow x = 12$.

**B2.** Expand both sides: $2x+6-5 = 2x+1$ and $3x-3$. So $2x+1 = 3x-3 \Rightarrow x = 4$. Check: left $2(7)-5 = 9$, right $3(3) = 9$ ✓

**B3.** Multiply every term by 6: $3x+2x = 30 \Rightarrow 5x = 30 \Rightarrow x = 6$.

**C1.** Adding the two equations eliminates $y$: $3x = 9 \Rightarrow x = 3$, then $y = 1$. Solution $(3,1)$.

**C2.** From $x-y=2$, $x = y+2$. Substituting: $3(y+2)+2y = 16 \Rightarrow 5y = 10 \Rightarrow y = 2$, so $x = 4$. Check: $3(4)+2(2) = 16$ ✓

**D1.** Two numbers multiplying to 6 and adding to $-5$ are $-2$ and $-3$: $(x-2)(x-3) = 0$, so $x = 2$ or $x = 3$.

**D2.** With $a=1$, $b=-4$, $c=-1$: $x = \dfrac{4\pm\sqrt{16+4}}{2} = \dfrac{4\pm\sqrt{20}}{2} = \dfrac{4\pm2\sqrt5}{2} = 2\pm\sqrt5$.

**D3.** Difference of squares: $(x-3)(x+3) = 0$, so $x = \pm 3$.

**E1.** Slope $= \dfrac{8-2}{4-1} = \dfrac{6}{3} = 2$.

**E2.** Slope-intercept form with $m=3$ and intercept $-2$: $y = 3x-2$.

**E3.** $f(-1) = 2(1)-3(-1)+1 = 2+3+1 = 6$.

**F1.** Multiply coefficients, add exponents of matching variables: $(2\cdot3)x^{2+1}y^{1+3} = 6x^3y^4$.

**F2.** $(a+b)^2 = a^2+ab+ab+b^2 = a^2+2ab+b^2$.

**G1.** **True** — the zero-product property. For real numbers, if neither $a$ nor $b$ were zero, their product could not be zero. You rely on it every time you factor and set each factor to zero, as in D1 and D3.

**G2.** **True.** Since $a \ne 0$ you can always solve directly: $x = -\dfrac{b}{a}$, and it is the only value that works.

### Answer key — Part 2

| Question | Answer | Why it matters for this course |
|---|---|---|
| Q1 | b | Variables are the basic language of every lesson from [Module 01](#/ch01/learn) onward. |
| Q2 | b | Foreshadows **inconsistent** systems — no solution ([Module 02](#/ch02/learn)). |
| Q3 | c | Foreshadows **dependent** systems — infinitely many solutions ([Module 02](#/ch02/learn)). |
| Q4 | a | Linear transformations are a special kind of function. |
| Q5 | c | You read graphs like this constantly in the row picture of a system. |
| Q6 | b | Directly the geometric picture behind a system with no solution. |
| Q7 | b | Needed to interpret solutions correctly, e.g. irrational eigenvalues in [Module 05](#/ch05/learn). |
| Q8 | c | Coefficient vs variable vs exponent is used in every matrix entry. |

---

### Scoring and what to do next

Count how many of the 18 problems you got completely right (right method with a small arithmetic slip counts as "mostly correct" — note it, but do not panic about it), and add your Part 2 score out of 8, for a combined score out of 26.

| Combined score | Recommendation |
|---|---|
| 22–26 | Start on [Module 01](#/ch01/learn) now. No prerequisite review needed. |
| 15–21 | You are ready. Spend 20–30 minutes reviewing whichever problem-set sections you missed. |
| Below 15 | Take 3–5 days for a structured algebra refresher first — especially Sections C and D — then retake this. |

Regardless of the score: if any skill in Part 3 is rated 2 or lower, give it a quick review before starting.

**Why each section matters here**

| Section | Skill | Where it shows up |
|---|---|---|
| A | Fraction arithmetic | Constantly — row reduction, determinants, normalising vectors |
| B | Solving linear equations | Back-substitution in Gaussian elimination ([Module 02](#/ch02/learn)) |
| C | Systems of two equations | The entire foundation of [Module 02](#/ch02/learn): elimination and $A\mathbf{x}=\mathbf{b}$ |
| D | Quadratic equations | Finding eigenvalues from the characteristic polynomial ([Module 05](#/ch05/learn)) |
| E | Lines, slope, functions | The row picture of a linear system; reading graphs throughout |
| F | Exponents and expansion | Nearly every derivation, including the dot-product expansions in [Module 01](#/ch01/learn) |
| G | Basic logical reasoning | Following the short proofs woven through the lessons |

If Section C or D is your weakest area, prioritise it — those matter most once you reach elimination ([Module 02](#/ch02/learn)) and eigenvalues ([Module 05](#/ch05/learn)).

---

> *Independent study guide for a first course in Linear Algebra. Every worked example and every practice question is written for this course. Where a problem from a past paper or a homework sheet is worked through, it is named where it appears — those papers are the student's own course materials, and they are quoted to show how the method applies to them, never passed off as this course's own. Not affiliated with or endorsed by any university or instructor, and not endorsed by Strang's Introduction to Linear Algebra, which it follows as a reference.*
