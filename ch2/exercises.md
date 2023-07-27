# Exercises

### 2.10

A *relation* is a set of $n$-tuples, while a *relation schema* is a set of attributes, and
optionally their types and constraints, of a certain relation.

### 2.11

No, since $s\_id$ wouldn't uniquely identify a tuple in that relation anymore. The primary
key should be both $s\_id$ and $i\_id$, since a student can't be advised by the same
instructor more than once.

### 2.12

* a: Primary keys:

  * $branch: branch\_name$
  * $costumer: customer\_name$
  * $loan: loan\_number$
  * $borrower: loan\_number$
  * $account: account\_number$
  * $depositor: ID$

* b: Foreign keys:

  * $branch:$ None
  * $customer: ID$
  * $loan: loan\_number$
  * $borrower: loan\_number$
  * $account: branch\_name$
  * $depositor: accout\_number$

### 2.13

TODO

### 2.14

* a:

$$
\Pi_{person\_name} (\sigma_{company\_name = ``BigBank"} (works))
$$

* b:

$$
\Pi_{employee.person\_name, city} (employee \bowtie_{
  \begin{aligned}
  &employee.person\_name = works.person\_name \\
  &\land company\_name = ``BigBank"
  \end{aligned}
} works)
