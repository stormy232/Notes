state is a "list of vars with associated values"

s1 = [ (x,5), (y, 6)]

State for now is going to be a list of tuples ig

Eval an expr -> replace vars with their vals, then eval

States can serve as a math model of program states

Execution of imperative programs can be though of as state transformation

State predicates focus on select aspects of this state transform induced by program exec
  [ (x,5), (y,6)]
 -> { x:= x+y }
 [(x,11), (y,6)]

Program correctness statements:
 - { P } C { Q } 
 - P is the precondition
 - C is statement
 - and Q is post condition

This is a Hoare triple

$$
P\implies [C]\ \ Q
$$
"If command C is started in a state statisfied precond P hold then it will term only when postcondition Q holds"


$$
(x = 0) \implies [x := x+1] \ (x=1) \ \checkmark \newline
$$
