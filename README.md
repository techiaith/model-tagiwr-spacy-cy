# Model Tagio Rhannau Ymadrodd Cymraeg

(see below for English)

Model spaCy (2.3.2) yw hwn sy'n cynnwys tagiwr rhan ymadrodd Cymraeg cychwynnol gyda chywirdeb o **91%**.

Mae'n dagiwr ystadegol sy'n gweithio ar sail dulliau dysgu peirianyddol, yn wahanol i dagwyr blaenorol sy'n gweithio ar sail rheolau.

O ganlyniad, mae'n well am ddygymod â chamsillafiadau a geiriau dieithr, ac yn fwy addas fel sail i adeiladu arno.

Er enghraifft, er nad oes unrhyw beth yn ymwneud â Smyrffs yn y corpws hyfforddi, mae'n dehongli'r frawddeg hon yn gywir:

```
Roedd AUX
y DET
smyrffs NOUN
yn PART
smyrffio VERB
yn PART
smyrfflyd ADJ
```

Yn ogystal, mae'n gallu dysgu i wahaniaethu rhwng gwahanol ystyron geiriau amwys fel 'ceir' (ffurf ar 'cael') a 'ceir' (lluosog 'car'), ac mae hefyd yn gallu gwahaniaethu rhwng berfau (VERB) a berfau cynorthwyol (AUX):

```
ceir VERB
dynion NOUN
hynod ADV
sy AUX
'n PART
gwerthu VERB
ceir NOUN
am ADP
eu DET
bywoliaeth NOUN
```


Gall hefyd **ymdpi** gyda chamsillafiadau:

```
Gall VERB
hefyd ADV
ymdpi VERB
gyda ADP
chamsillafiadau NOUN
```

Hyfforddwyd y tagiwr cychwynnol hwn ar y brawddegau hyfforddi CC0 hyn:

https://github.com/techiaith/corpws-brawddegau-tagiedig

Mae'r tagiwr yn defnyddio set rhannau ymadrodd Universal Dependencies. 

Ar hyn o bryd, bydd angen i chi osod ffolder iaith `lang` Cymraeg yn spaCy i hyn weithio. Mae ffolder ddrafft a chyfarwyddiadau ar sut i'w osod yn spaCy ar gael gennym yma:

https://github.com/techiaith/spacy-cy-lang

Byddwn yn cyfrannu'r ffeiliau hyn i spaCy yn y dyfodol agos er mwyn gwneud i ffwrdd â'r angen am y cam hwnnw.

Byddwn yn parhau i wella'r tagiwr ac ychwanegu nodweddion newydd iddo dros y misoedd nesaf.

## Cyfarwyddiadau

1. Gosodwch spaCy 2.3.2 o fewn rhithamgylchedd

```
python -m venv .env
source .env/bin/activate
pip install -U spacy
```

2. Gosodwch y ffolder lang cy drwy ddilyn y cyfarwyddiadau YMA.
3. Gosodwch y model ar eich peiriant a'i ddadsipio
4. Crëwch ffeil Python gyda'r cod canlynol a'i redeg:

```
import spacy

nlp = spacy.load("lleoliad eich model")

sents = ["mae'r cathod yn bwyta",
         "roedd y dynion yn hapus",
         "cododd y carped a'i ysgwyd",
         "gwyliodd y teledu yn ddistaw"]

for sent in sents:
    doc = nlp(sent)
    for token in doc:
        print(token.text, token.pos_)
    print ("--------------")
```

Canlyniad disgwyliedig:

```
mae AUX
'r DET
cathod NOUN
yn PART
bwyta VERB
--------------
roedd VERB
y DET
dynion NOUN
yn PART
hapus ADJ
--------------
cododd VERB
y DET
carped NOUN
a CONJ
'i DET
ysgwyd VERB
--------------
gwyliodd VERB
y DET
teledu NOUN
yn PART
ddistaw ADJ
--------------
```

Ariannwyd y gwaith hwn gan Lywodraeth Cymru.

# Welsh-language Part-of-Speech Tagging Model

This is a Welsh-language spaCy (2.3.2) model featuring a part-of-speech tagger that achieves 91% accuracy on unseen data. 

The tagger is a statistical tagger that works using machine learning methods, in contrast to earlier taggers that are based on rules.

As a result, it copes better with misspellings and unfamiliar words, and therefore forms a better basis on which to build.

For example, even though the training corpus does not feature any references to Smyrffs (Smurfs), the tagger parses this sentence correctly:

```
Roedd AUX
y DET
smyrffs NOUN
yn PART
smyrffio VERB
yn PART
smyrfflyd ADJ
```

Additionally, the parser can learn to differentiate between the different meanings of ambiguous words such as 'ceir' (a form of the verb 'cael' [EN:have]) and 'ceir' (the plural of 'car' [EN:cars]). It can also differentiate between verbs (VERB) and auxiliary verbs (AUX):

```
ceir VERB
dynion NOUN
hynod ADV
sy AUX
'n PART
gwerthu VERB
ceir NOUN
am ADP
eu DET
bywoliaeth NOUN
```

It can also cope with misspellings such as **ymdpi** (ymdopi [EN:cope]):

```
Gall VERB
hefyd ADV
ymdpi VERB
gyda ADP
chamsillafiadau NOUN
```

This tagger was trained on the following CC0 corpus:

https://github.com/techiaith/corpws-brawddegau-tagiedig

The tagger uses the Universal Dependencies tagset. 

Currently, you will need to install a Welsh `lang` folder in spaCy for this to work. We've provided a draft folder and installation instructions here:

https://github.com/techiaith/spacy-cy-lang

We will be contributing these files to spaCy in the near future so that this step will no longer be required.

We will be improving the tagger and assing additional functionality over the coming months.

## Instructions

1. Install spaCy 2.3.2 within a virtual environment

```
python -m venv .env
source .env/bin/activate
pip install -U spacy
```

2. Install the lang cy folder by following the instructions HERE.
3. Install the model on your computer and unzip it
4. Create a Python file using the following code and run it:

```
import spacy

nlp = spacy.load("location of the model")

sents = ["mae'r cathod yn bwyta",
         "roedd y dynion yn hapus",
         "cododd y carped a'i ysgwyd",
         "gwyliodd y teledu yn ddistaw"]

for sent in sents:
    doc = nlp(sent)
    for token in doc:
        print(token.text, token.pos_)
    print ("--------------")
```

Expected results:

```
mae AUX
'r DET
cathod NOUN
yn PART
bwyta VERB
--------------
roedd VERB
y DET
dynion NOUN
yn PART
hapus ADJ
--------------
cododd VERB
y DET
carped NOUN
a CONJ
'i DET
ysgwyd VERB
--------------
gwyliodd VERB
y DET
teledu NOUN
yn PART
ddistaw ADJ
--------------
```

This work was funded by the Welsh Government.
