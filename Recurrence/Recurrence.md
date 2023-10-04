## Technicalites of recurrence
- 일반적으로 Recurrence에서의 **n은 정수**의 값으로 가정한다.
- **floors와 ceilings를 무시**한다. (often insignificant)
- T(n)의 값은 작은 n에 대한 작은 상수로 가정한다.

## The methods to solve recurrence problems
Recurrence relation에 대한 문제를 풀 때 아래와 같은 방법들로 풀 수 있다.
1. Substitution Method
2. Tree Method
3. Master Method

## Substitution Method
Substitution Method(치환법)은 크게 두 개의 과정을 거친다.
1. 해의 모양을 추측
2. 수학적 귀납법을 통한 솔루션 증명

<br>

Example>>
$$T(n) = 2T(\lfloor n/2 \rfloor) + n$$

**Guess:** $T(n) = O(n\lg_{}{n})$

**Prove by induction:** $T(n) \leq cn\lg_{}{n}$

**[Inductive Proof]**
1. **Basic case:** $T(1) \leq cn\lg_{}{n}$
2. **Inductive hypothesis:** For $n=\lfloor k/2 \rfloor$,

$$
\begin{aligned}
T(\lfloor k/2 \rfloor)& \leq c\lfloor k/2 \rfloor\lg_{}{\lfloor k/2 \rfloor} \\ \\
T(n)& = 2T(\lfloor n/2 \rfloor) + n \\ \\
\therefore T(k)& \leq 2(c\lfloor k/2 \rfloor\lg_{}{\lfloor k/2 \rfloor}) + k \\ \\
\end{aligned}
$$

<br>

$$
\begin{aligned}
T(k)& \leq 2\{c(k/2)\lg_{}{k/2}\} + k \\ \\
T(k)& \leq ck(\lg_{}{k}-\lg_{}{2}) + k \\ \\
T(k)& \leq ck(\lg_{}{k}-1) + k \\ \\
T(k)& \leq ck \lg_{}{k} - ck + k = ck \lg_{}{k} - k(1-c) \\ \\
\therefore T(k)& \leq 2(c\lfloor k/2 \rfloor\lg_{}{\lfloor k/2 \rfloor}) + k \\ \\
\end{aligned}
$$