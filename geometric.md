# Geometric distribution

## On examples from quant interview problems

## Reminder 

$$P(X = success) = p$$
$$P(X = fail) = 1 - p$$

$$ \mu = \frac{1}{p}$$

$$ \sigma^2 = \frac{1-p}{p^2} $$

## Task 1: You are flipping a fair coin repeatedly. How many times on average do you need to flip it to get 5 heads in a row?

To find out how many times on average you need to flip a fair coin to get $n$ heads in a row, 
we can use the concept of Markov chain and induction approach.

Let $E[f(n)]$ be the expected number of coin tosses to get $n$ heads in a row. 
Using the Markov chain approach, we divide the experiment into states , state 
$i$ defines we have seen i heads in a row. We know state before 
(n+1) heads in a row must be 
$n$ heads in a row. Conditioned on state
$n$ heads in a row, there is a $1/2$  probability it will go to 
$n+1$ heads in a row (the new toss yields H) and the process stops. There is also a 
$1/2$ probability that it will go to the starting state 0 (the new toss yields T) and we need another expecct
$E[f(n+1)]$ tosses to reach 
$(n+1)$ heads in a row ( i.e. In addition to the existing 
$E[f(n)]$ steps to reach the state of $n$ heads). So we have

$$E[f(n+1)]= (1+E[f(n)]) + (1+E[f(n)]+E[f(n+1)]) $$

This simplifies to $$E[f(n+1)]=2E[f(n)]+2$$. 
This recursion can be solved easily and yields E[f(n)]=2 n+1 −2. Therefore, on average, you need to flip a fair coi $2^{n+1} −$2 times to get 5 heads in a row.

## Task 2: 
