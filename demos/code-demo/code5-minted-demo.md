---
header-includes:
- \usepackage{minted}
- \setminted{linenos=true}

# pandoc -s -F pandoc-minted code5-minted-demo.md -o code5-minted-demo.tex && pdflatex --shell-escape code5-minted-demo.tex
---

Python sample code:

```python
import itertools

def iter_primes():
     # an iterator of all numbers between 2 and +infinity
     numbers = itertools.count(2)

     # generate primes forever
     while True:
         # get the first number from the iterator (always a prime)
         prime = numbers.next()
         yield prime

         # this code iteratively builds up a chain of
         # filters...slightly tricky, but ponder it a bit
         numbers = itertools.ifilter(prime.__rmod__, numbers)

for p in iter_primes():
    if p > 1000:
        break
    print p
```
