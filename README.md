# ChokeSpeare
Using different models to generate poems and compare performance.

## Background
1. Used a combination of multiple poem datasets I could find on the internet. 
2. Have followed a semi-bare bones structure (Avoided using explicit torch implementations except for maybe backprop and optimizers).
   
## Approaches
1. [x] Bigrams
2. [x] Simple NN with optimizations - 12k
3. [x] Deep NN - 175k
4. [x] Simple RNN as given in [Mikolov et al. 2010](https://www.fit.vut.cz/research/group/speech/public/publi/2010/mikolov_interspeech2010_IS100722.pdf) - 18k
5. [x] Wavenet - 80k
6. [x] GRU - 35k 
7. [x] LSTM - 42k
8. [x] Encoder-Decoder
9. [ ] Transformers

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

3. Deep NN 
<br/>

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

4. Simple RNN
<br/>

![rnnloss.png](./assets/rnnloss.png)

```
thate that that in the stord i sunded to stream is shines.
with stin the preep the stands.
a sumber to lives indel young is shis the chaits all so the can.
wature.
who she clis stone to the peech i stirds is shared the such the praspleds.
when that the was but the wind tell asting are bet a stonger space and back the pares this what so long in the pere.
a takes a standing a prinds the who truck is and and shoil that ister will terrive.
in the will weat i water shatest some.
i the surresside all so me the wind i cranch the was bettance to see i warms the can thined.
whis stan.
```

5. LSTM
<br/>

![lstmloss.png](./assets/lstmloss.png)

```
never somether the stars.
nothing and the she care a can't and a star.
walking strengs the shet this still somerigant.
all the words and the say are always are a thoughts the strenglate.
not a there's the same a still something a time the was so we leaves and such in a the persence.
with the wine an think and the walk to that's a time they child the shade.
a spring to this hollood.
when my procking and the wintered tomorrow.
wind thing so stanted an only still the staits to the stain.
will and the still and summing.
```

6. GRU
<br/>

![gruloss.png](./assets/gruloss.png)

```
to lost in the shore.
the stonew so sea stimbered it's soul and starts falls that take a shorting.
i she still shower and touch are this who to too change and a tooms.
the way on teal winds it the first stands to let soul to like shines fall.
trught we world the such so founting is i cannant ats the falls in the friend i his.
we seen the life shines face is the strend and sunlight take trught friends that.
the wind it and the face a let suns to fill stay i chold i choose to to let.
we changes should the seas the will the too madariness to from the will stance.
in the wind the too me it's father sout than as too to chills a lights.
i fathers and and the see sun and who we stirve to life that to stars.
```

7. Wavenet
<br/>

```
Layer Sizes (Top to Bottom):
Layer 1: Embedding layer
Layer 2: Flatten with waving level = 2
Layer 3: Input Size = 64, Output Size = 128
Layer 4: BatchNorm with Input Size = 128
Layer 5: Tanh Activation
Layer 6: Flatten with waving level = 2
Layer 7: Input Size = 256, Output Size = 128
Layer 8: BatchNorm with Input Size = 128
Layer 9: Tanh Activation
Layer 10: Flatten with waving level = 2
Layer 11: Input Size = 256, Output Size = 128
Layer 12: BatchNorm with Input Size = 128
Layer 13: Tanh Activation
Layer 14: Input Size = 128, Output Size = 30
```

![wavenetloss.png](./assets/wavenetloss.png)

```
dreams of just is no fight brued orrow openge
starled as colity day peace
moon so for the sun like you said way jay tell my think we healy meather every arriends oving victorb two die
whispered and fall the could me they are my awrites a hest hail aven sqarty day sky abora sittent to klif hoods of time
embers they one hurned summeraccess in llver i have forgocus his the ruaporation faltem cut think and dubred
mistarxers black it is lame tlacm beats not paiking in defing winter
azure open acchopos but it to feel mutuma have is dimations touch are to the lost than aluly in i jozing their freen and thwn so to in gone
shadows a time on them in't soous broping flock ty love fall airs no clarbs
crystall grest decome the need dived blue my lo thinms the hunder alma dark keeps mokiday
velvets suns ocrappage seaged why don't cher watch tomore
sunsets of hooden forging
autumn water powee me myself
echoisment the vism passed unways corce a'd call on deathes
```

8. Encoder-Decoder

![encdecloos.png](./assets/enc-dec.png)

```
the rafters buckle and the embers brare waten.
sun streams through glass panes gold warmthn want.
from his own tripode will.
i invented you no flaws only peres its.
my phone reflected t we set.
as summer ends the shades project ted are.
his balls were dangling like the et we warmy.
drowning in dharma a raft making i the way.
grievance good given a higher posede sounds.
the past may tempt you to dwell in an in sead.
```

## Performance logs (train, val, test)
- Bigrams -> (2.4455533027648926, didn't bother, didn't bother)
- Pre weight init optimization on MLP-> (1.7559022903442383, 1.7703694105148315, 1.785829782485962)
- Post weight init optimization on MLP -> (1.7148950099945068, 1.729537844657898, 1.7452518939971924)
- Post Batch norm on MLP-> (1.77047860622406, 1.7761619091033936, 1.7911485433578491)
- Multiple layers with batch norm & increased context length-> (1.4757354259490967, 1.6017286777496338, 1.6243505477905273)
- Wavenet -> (1.5621434450149536, 1.606853723526001, 1.623463749885559)
- Simple RNN -> (1.7627, -, 1.7784347534179688)
- RNN with GRU cell -> (1.5669128894805908, -, 1.5835411548614502)
- RNN with LSTM cell -> (1.6525046825408936, -, 1.651007890701294)
- Encoder-Decoder with LSTM cell -> (0.5115, -, -)

## Observations
- Batchnorm sucks on small networks.
- There was a batchnorm bug while implementing wavenet that essentially made it do nothing without any explicit errors. However, fixing the bug gave not much improvements.
- Making weights gaussian and using kaiming normalalization improves performance significantly because it is a workaround for the vanishing gradients problem with tanh.
- Increasing context length, embedding dimensions or the network size surprisingly do not have a significant effect on loss.
