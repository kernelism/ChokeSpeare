# Approaching haikus generation with different strategies - following [makemore](https://github.com/karpathy/makemore)

## Approaches
1. [x] Bigrams
2. [x] Simple NN with optimizations
3. [ ] Not sure yet...

## Loss
1. Bigrams saturates negative log likelihood at around 2.5, which is not so great.
<br/>

![bigramloss.png](./assets/bigramloss.png)

Some of its generations:

```
astce sskisednesilozqqāwale dsth lebemvivi wer 
t is llan be heñy f a ce blese aplke l owingetencr

```

2. Simple NN with a single hidden layer after optimizations through weight initialisation and HPT hits 1.7. You could argue that this is not a great improvement, but compare the generated results to better understand the 0.8 loss improvement!
<br/>

![mlploss.png](./assets/mlploss.png)

Some of its generations:

```
hearth   soft the strance thermen spiat told mour lets  day 

hunthes one skiend my line bricher to love breats the would i haikuled words nour clow its hope 

i fgence cast a pregreth in befucklack pubetrance  augh pine  pernet again thare 

poste  curly of brie 

i cer thirnely overgoreddirg and much in wintert nosetoday  tir stracicks have  fellent shing my am not tears shout a gux  i am nothat  my grows my whatrled on   coss ours ving fall upraying nicadistearly weath   moon 
```

PS: Ignore the extra spaces in the generated results. It was a preprocessing issue :p