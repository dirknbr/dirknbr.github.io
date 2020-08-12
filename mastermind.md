# Mastermind solver in Python

In this code I am solving the mastermind problem. You have to guess a k-length permutation of n colours.

You are given feedback in the form of correct positions and colours (x, black), and just correct colours (o, white).

We simplify this game a bit, usually it's 4 out of 6 but in the code we do 3 out of 4. Colours are not repeated.

With 3 out of 4 we have 24 possible options. 

The solution strategy is
- guess the first sequence
- create a solution set `rem_sol` that has all possible solutions which return the same feedback (eg xoo)
- then in a while loop select (random) solutions from this set and reduce it until we have only one option left, using the same feedback function 

```py

# guess 3 out of 4 possible
# true: 123, pred: 13, eval -> xo, x is colour and position correct, o colour correct

import numpy as np
from itertools import permutations 

def gen_seq(n=4, k=3):
  seq = list(np.random.choice(n, k, replace=False))
  return ''.join(map(str, seq))

def select_from_set(s):
  return np.random.choice(list(s), 1)[0]

def feedback(y, pred):
  # check pred has unique, x=pos and colour, o=colour
  assert len(pred) == len(set(pred))
  assert len(y) == len(pred)
  x = sum([y[i] == pred[i] for i in range(len(y))])
  o = sum([pred[i] in y for i in range(len(y))])
  o -= x # avoid double count
  return 'x' * x + 'o' * o

def all_possible(n=4, k=3):
  ran = map(str, range(n))
  allp = list(permutations(ran, k))
  allp = [''.join(p) for p in allp]
  return allp

n, k = 4, 3

# some tests
print(gen_seq(n, k))

print(feedback('123', '321'))
print(feedback('123', '421'))
print(feedback('123', '456'))

# iterate all possible permutations
allp = all_possible(n, k)
print(len(allp))
print(allp)

step = 0
sol = gen_seq(n, k)
guess = gen_seq(n, k)
score = feedback(sol, guess)

rem_sol = set()
for s in allp:
  if feedback(s, guess) == score:
    rem_sol.add(s)

print(step, guess, score, len(rem_sol), rem_sol)

while len(rem_sol) > 1:

  rem_sol2 = set()
  # guess = gen_seq()
  guess = select_from_set(rem_sol)
  score = feedback(sol, guess)

  for s in allp:
    if feedback(s, guess) == score:
      rem_sol2.add(s)

  rem_sol = rem_sol.intersection(rem_sol2)
  step += 1
  print(step, guess, score, len(rem_sol), rem_sol)

print(sol)
```

Example output

```
120
xoo
xo

24
['012', '013', '021', '023', '031', '032', '102', '103', '120', '123', '130', '132', '201', '203', '210', '213', '230', '231', '301', '302', '310', '312', '320', '321']
0 120 xo 6 {'310', '023', '103', '230', '321', '132'}
1 321 xo 2 {'310', '023'}
2 023 oo 1 {'310'}
310
[Finished in 0.2s]
```
