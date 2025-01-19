# ChokeSpeare - following [makemore](https://github.com/karpathy/makemore)
Makemore is this interesting video [series](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) by Andrej Karpathy which is imo one of the best practical learning materials out there for NN/DL.

I have attempted to replicate the approach in the context of **poem** generation, exploring similar techniques to create poetic structures and verses.

## Background
1. Used a haiku dataset. Haikus follow a certain rule (5-7-5 syllable pattern). I did not choose to build this constraint into my model. I just let the model learn word coherence (on a character level of ourse) and let it "freestyle".
2. Have followed a semi-bare bones structure (Avoided using explicit torch implementations except for maybe backprop and optimizers).
3. The Simple NN is an explicit trigram model
4. The Deep NN model uses 10 characters context windows.
5. The RNN theoretically could use the max block size.

## Approaches
1. [x] Bigrams
2. [x] Simple NN with optimizations
3. [x] Deep NN
4. [x] Simple RNN as given in [Mikolov et al. 2010](https://www.fit.vut.cz/research/group/speech/public/publi/2010/mikolov_interspeech2010_IS100722.pdf)
5. [ ] LSTM
6. [ ] Transformers

## Results
1. Bigrams
<br/>

![bigramloss.png](./assets/bigramloss.png)
```
'mof tieru arber itost thinot bontikin
t t s by  bf  is lltudske sine e  s lountss me
ceve,usetllitplor n it pesoubug t ts bung  pln tinge y blsthere  y iticogimati jzcere den le  y desyoncthom
vesusie tep.
merrnond o or slichee  pzzwanojutikdd ng hitg t
in
peasievethinoma trofon nomof pl unxxrkeh fqoupe ts tumy sugile hay  ve acachee conthe nd avidorthi's   desithay
tarus furured hismps fu tr itetsheveryhithe n t tt f ithi'ving  t   wing he s diqnere cl
cak ybarer hetand che  y tibo mymere an she n
fe  jnordsh w'qqlis chajs awashenorea gen mbneg'so atjs b,qjud s t
bl gher mzve an powi l a  d
d sticrd bitora matold ancamean to cir aricanspp se nenge ad  s mowveng ndowily ocashxwenioutous  inanete'f cher  icat  s s d  pas huttee ie kes pere is xormbesiorofrghesloxun ksctam'soy te t g tof mest atpe miore owhe,p,sath wqike m d m anteaith
be ctheaconos cedadalicts t ing tispepe shthe  wsword tereee c t kdesckis tamago twindefish  mu'd pin d itay d  pronculilaju ant fereworineriy  p g ce
ifi  gse  mo gs
inca wa ises bold
inon powhas gethe  bmyacr hid inveete bouin sow
```

2. Simple NN.
<br/>

![mlploss.png](./assets/mlploss.png)
```
my like afting on all that it sun i go hill toshine wide i smell slicking the but and brang 
love 
ear word is sun sins colds of on in cold 
the eder samer firer's yeged to blanchone poean 
my hair and it of godtinn sumwelling always 
must hundertain therent be vame  drest i smill now a chold breame clashbove griend tone 
sione watch all good grinco nights all chank tiges a move  
a swife the were from the me and exhelpemeding agains  
mome no not ander light bus you was sight leave tring natain  
to blast i cry reflecty blue's no mes hode tosess perfling in hear am heir  was  here 
i ted to your patting rains the mile celiness 
stone nowhy or fricall seekze to word they 
i leave cool a ver the have sucked to bothe red and nevellinessed in home 
easks solflyain a forghour shy fend to your splayresh at up 
the the for again theys of my he won't ther the like morn 
wine woulderf cretempere day in my carreft the soft and close actans has down a p all cly 
prengone forning grave is ands alched and but in unds it bongivence my and manight anxed time 
my stake morever soges spe but string cared be ampile reaf the day you 
```

3. Pretty Deep NN 
```
Layer Sizes (Top to Bottom):
Layer 1: Input Size = 300, Output Size = 300
Layer 2: BatchNorm with Input Size = 300
Layer 3: Input Size = 300, Output Size = 200
Layer 4: BatchNorm with Input Size = 200
Layer 5: Input Size = 200, Output Size = 100
Layer 6: BatchNorm with Input Size = 100
Layer 7: Input Size = 100, Output Size = 30
```

![deepnnoutput.png](./assets/deepnnoutput.png)


It did achieve a lower result. A significant drop in training loss, but a slight overfit. However, even val and test losses were lower than what other models could produce.

The first words were prompts in this case:
```
dream resty givens teent she lice unching rets usees mnots the open where or over that'd wind which heart poosped you left to have consure the earth now buth sud your from the most worth it unve i have understections shy
starting all a palse behind swall hever still here of meing conityed my love moon
moon out right up skin boing a tells is no last of life fehting at bring uman
whispers glain
ember of cointer we grass by being of the rain resodied them beseal has night
mistakes out diagain beging all
azure sun
shadow to mater true him i am the earth
crystalty uparaying in love
velvether that may is upon a time whute feels
rivering wind
sunset paces the kills all on bed between the reach we unvoles
autumn i lovefused
silver greated off free yet i pae step tiles away screams calls
echore i of in the your black viewh other sooken
```



4. RNN

![rnnloss.png](./assets/rnnloss.png)

```
somels now i
the conswalied leaven my is to the bips a emodin
hup be away lead of now
oceh sackled tree moine pill to sky honeacig'
the of i grair due too soxay ite misch tries your off now offatcer verys take some of never look than conted you you
sky mathine on gay no at haisy too to be
minding time me but and youg the bad in toikled huld one
the life nog a dear gives
my loors a death cads cheared overy a bive'p nother out my she snimbor blied of me abrous know
hea the rivere lack no shopes you shine a timench to gelling tat crying thathed you kn turns light i he we grise aut
```

PS: Ignore the extra spaces in the generated results. It was a preprocessing issue :p
