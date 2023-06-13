# Chapter 2 - Practice Exercises

### 2.1

TODO

### 2.2

* Insert: Inserting a new instructor $i$ such that $i.dept\_name$ doesn't exist in the $department$
  relation breaks the foreign-key constraint.
* Delete: Deleting any department $d$ such that there is an instructor $i$ where
  $i.department = d$ breaks the foreign-key constraint.

### 2.3

Because the attributes $time\_slot\_id$, $day$ and $start\_time$ are sufficient for uniquely
identifying a time slot, that is, they're the *minimal* attribute set for primary key
definition. If we did have two time slots with the same 3 cited attributes, it
would be a repetition (therefore, not a set) of a unique time slot.

### 2.4

No. A particular instance of a relation having no repetition of an attribute $A$ doesn't
mean that $A$ should be used as the primary key for the relation. We should always
antecipate, based on our domain knowledge, if it's possible to two tuples having the same
value for $A$. In this case, it's obvious that two instructors can have the same name.

### 2.5

It would return all the students that have an advisor, together with their $ID$s (repeated
twice, because of the $s\_id$ attribute), $name$, $dept\_name$ and $tot\_cred$.

### 2.6

* a:

$$
\Pi_{person\_name} (\sigma_{city = \text{``Miami"}} (employee))
$$

* b:

$$
\begin{aligned}
rich\_employees &\gets \sigma_{salary > 10^5} (works) \\
\Pi_{person\_name} &(rich\_employees)
\end{aligned}
$$

* c: Two possible ways, using a mix of join and project, and using a mix of selects, projects
and set operations. We chose the latter and also make it cleaner by using the assignment
operator.

$$
\begin{aligned}
rich &\gets \Pi_{person\_name}(\sigma_{salary > 10^5}(work)) \\
miami\_residents &\gets \Pi_{person\_name}(\sigma_{city = ``Miami"}(employees)) \\
rich &\cap miami\_residents
\end{aligned}
$$

### 2.7

* a:

$$
\Pi_{branch_name}(\sigma_{branch\_name = ``Chicago"}(branch))
$$

* b:

$$
\Pi_{ID} (borrower \bowtie_{
  \begin{aligned}
  &borrower.loan\_number = loan.loan\_number \\
  & \land branch\_name = ``Downtown"
  \end{aligned}} loan)
$$

### 2.8

In the book's 7th edition, none of the relations have $ID$. I believe this is a typo.

* a:

$$
\Pi_{person\_name} (\sigma_{company\_name \neq ``BigBank"} (works))
$$

* b:

$$
\begin{aligned}
&\Pi_{person\_name}(employee) - \\
&\Pi_{person\_name}( \rho_{A}(employee) \bowtie_{A.salary < B.salary} \rho_{B} (employee))
\end{aligned}
$$

### 2.9
