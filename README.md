# Generating small poems with different strategies - following [makemore](https://github.com/karpathy/makemore)

## Background
Used a haiku dataset. Haikus follow a certain rule (5-7-5 syllable pattern). I did not choose to build this constraint into my model. I just let the model learn the coherence (on a character level of ourse) and let the models "freestyle".

## Approaches
1. [x] Bigrams
2. [x] Simple NN with optimizations
3. [ ] Not sure yet...

## Loss
1. Bigrams saturates negative log likelihood at around 2.5, which is not so great.
<br/>

![bigramloss.png](./assets/bigramloss.png)

Results:
```
'mof tieru arber itost thinot bontikin .
t t s by  bf  is lltudske sine e  s lountss me .
.
ceve,usetllitplor n it pesoubug t ts bung  pln tinge y blsthere  y iticogimati jzcere den le  y desyoncthom .
vesusie tep.
.
merrnond o or slichee  pzzwanojutikdd ng hitg t .
in .
.
peasievethinoma trofon nomof pl unxxrkeh fqoupe ts tumy sugile hay  ve acachee conthe nd avidorthi's   desithay .
tarus furured hismps fu tr itetsheveryhithe n t tt f ithi'ving  t   wing he s diqnere cl .
cak ybarer hetand che  y tibo mymere an she n .
 fe  jnordsh w'qqlis chajs awashenorea gen mbneg'so atjs b,qjud s t  .
 bl gher mzve an powi l a  d .
d sticrd bitora matold ancamean to cir aricanspp se nenge ad  s mowveng ndowily ocashxwenioutous  inanete'f cher  icat  s s d  pas huttee ie kes pere is xormbesiorofrghesloxun ksctam'soy te t g tof mest atpe miore owhe,p,sath wqike m d m anteaith .
  .
be ctheaconos cedadalicts t ing tispepe shthe  wsword tereee c t kdesckis tamago twindefish  mu'd pin d itay d  pronculilaju ant fereworineriy  p g ce .
ifi  gse  mo gs .
 inca wa ises bold .
inon powhas gethe  bmyacr hid inveete bouin sow.

```

2. Simple NN with a single hidden layer after optimizations through weight initialisation and HPT hits 1.7. You could argue that this is not a great improvement, but compare the generated results to better understand the 0.8 loss improvement!
<br/>

![mlploss.png](./assets/mlploss.png)

Results:
```
i can all ing   younderse are haveath recing 

hearth   soft the strance thermen spiat told mour lets  day 

hunthes one skiend my line bricher to love breats the would i haikuled words nour clow its hope 

me   i was  the vhing thoubblight   i wishird 

the red 

coconto paineckin to be 

along lets the enes  tear to dring and stilened 

whaterry i zanes   remarve freus an a bough  life leaveful rag infester corabeling the sad willust for more 

the nunselver casfriatls would i cle  he winted one  are of famn 

ancing of us deple  down   a blue  i new i was is asway   drop faile   like 

i fgence cast a pregreth in befucklack pubetrance  augh pine  pernet again thare 

poste  curly of brie 

i cer thirnely overgoreddirg and much in wintert nosetoday  tir stracicks have  fellent shing my am not tears shout a gux  i am nothat  my grows my whatrled on   coss ours ving fall upraying nicadistearly weath   moon 

six 

maning 

silence so hoice 

the suzsy path 

thiness  sure crofet a foe 

any you corce from today don't falling  dreach wher duotcp the ro remblan out woul senst how oh in the so fire wall hib  were dog broxe wher neach lunice pock wring about  it  was sad like sour passeet limur love scoolse are dark cragic   fromet 

gomorever and  tunning died wailing  onches 

```
PS: Ignore the extra spaces in the generated results. It was a preprocessing issue :p
