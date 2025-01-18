# Approaching haikus generation with different strategies - following [makemore](https://github.com/karpathy/makemore)

## Approaches
1. [x] Bigrams
2. [x] Simple NN with optimizations
3. [ ] Not sure yet...

## Loss
- Bigrams saturates negative log likelihood at around 2.5, which is not so great.
![bigramloss.png](./assets/bigramloss.png)

Some of its generations:

```
astce sskisedénesilozqqāwale dsth lebemvivi wer 
t is llan be heñy f a ce blese aplke l owingetencr

```

- Simple NN after optimizations through weight initialisation and HPT hits 1.7. You could argue that this is not a great improvement. Take a look at the results below to understand!
![mlploss.png](./assets/mlploss.png)

Some of its generations:

```
hearth   soft the strance thermen spiat told mour lets  day 

hunthes one skiend my line bricher to love breats the would i haikuled words nour clow its hope 
```

