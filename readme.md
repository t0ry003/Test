Grupa: 434D

Stabilizator de tensiune cu element regulator serie

*Universitatea Politehnica din Bucureşti - Facultatea de Electronică şi Telecomunicaţii*

Prof. Coordonator: Drăghici Florin

# 1. Stabilizatoarele de tensiune cu element de reglaj serie (ERS)

Stabilizatoarele de tensiune cu element de reglaj serie, care utilizează amplificatoare de eroare, sunt sisteme complexe, proiectate pentru a menține o tensiune constantă la ieșire în ciuda variațiilor de sarcină sau tensiune de intrare. Aceste stabilizatoare funcționează conform principiului reacției negative și sunt frecvent utilizate datorită preciziei și fiabilității lor.

## 1.1. Configurația generală a stabilizatoarelor cu amplificator operațional

Aceste stabilizatoare folosesc *amplificatoare operaționale (AO)* ca amplificatoare de eroare în configurație neinversoare. În această configurație avem:

1. **Intrarea neinversoare** primește o tensiune de referință (denumită *V_(ref)*​), generată de obicei de un stabilizator parametric, cum ar fi unul cu diodă Zener.

2. ![](media/image1.png)**Intrarea inversoare** primește o fracțiune din tensiunea de ieșire, preluată printr-un divizor de tensiune. Divizorul este format din rezistențe care ajustează nivelul semnalului proporțional cu tensiunea de ieșire.

   *(Fig. 1) Schema bloc a stabilizatorului de tensiune cu ERS*

## 1.2. Funcționarea amplificatorului operațional

Amplificatorul operațional are un factor de amplificare foarte mare în buclă deschisă. Acest lucru determină ca diferența de potențial între intrările inversoare și neinversoare să fie extrem de mică în timpul funcționării normale. Prin urmare, orice modificare a tensiunii de ieșire care creează o diferență între aceste două intrări va genera o tensiune diferențială la ieșirea AO. Această tensiune va fi folosită pentru a corecta variația prin comanda elementului de reglaj serie, restabilind echilibrul.

## 1.3. Principiul funcționării

Stabilizatoarele liniare de tensiune continuă (*SLTC*) se bazează pe:

- **Conexiunea cu reacție negativă**, care monitorizează și ajustează continuu tensiunea de ieșire *(P – potențiometrul si R – rezistenta, Fig. 1)*

- **Comparația între tensiunea de ieșire și tensiunea de referință**, realizată de amplificatorul de eroare.

## 1.4. Indicatori de performanță ai stabilizatoarelor liniare

Calitatea unui stabilizator este determinată de mai mulți parametri esențiali:

1.  **Coeficientul de stabilizare (*S₀*​)** - reprezintă capacitatea stabilizatorului de a menține tensiunea constantă în fața variațiilor de intrare. Valori mai mari indică o performanță superioară.

2.  **Rezistența de ieșire (*R₀*​)** - influențează cât de mult scade tensiunea la ieșire pe măsură ce crește curentul de sarcină. Rezistența scăzută este dorită pentru o stabilitate mai bună.

3.  **Coeficientul de temperatură (*K_(T)*​)** - exprimă sensibilitatea stabilizatorului la variațiile de temperatură. O valoare mică asigură o performanță constantă în condiții de mediu diferite.

## 1.5. Protecții integrate în stabilizatoare

Pentru a preveni deteriorarea circuitului în condiții de suprasarcină sau scurtcircuit, majoritatea stabilizatoarelor liniare moderne includ:

- **Circuite de limitare a curentului de ieșire**, care previn suprasolicitarea regulatorului serie. Această limitare poate fi:

1.  **Simplă**, protejând doar împotriva curentului excesiv.

2.  **Cu întoarcerea curentului**, unde, în cazul unui scurtcircuit, se reduce și puterea disipată de regulator.

## 1.6. Structura amplificatorului de eroare

S-a utilizat o configurație de amplificator operațional neinversor, în care factorul de amplificare în tensiune (*A_(v)*​) este determinat de relația matematică:

``` math
A_{\nu} = 1 + \frac{R_{2}}{R_{1}}
```

Pentru implementarea amplificatorului de eroare, s-a adoptat o arhitectură clasică de amplificator operațional în clasa A, care este structurată în două secțiuni principale:

1.  **Secțiunea de intrare și semnal mic**, responsabilă pentru adaptarea impedanțelor și procesarea semnalului de mică amplitudine.

2.  **Secțiunea de amplificare în tensiune**, care realizează o amplificare semnificativă a semnalului.

Această divizare permite utilizarea etajelor specializate fie pentru amplificare în curent, fie pentru amplificare în tensiune, optimizând astfel performanța generală a circuitului.

### 1.6.1. Etajele amplificatorului

#### a) Etajul de intrare

> Etajul de intrare este configurat ca **amplificator diferențial**, având rolul principal de a asigura **adaptarea impedanței** între sursa de semnal (impedanță mare) și etajele ulterioare (impedanță mică). Acesta funcționează conform principiului de **transconductanță**, transformând semnalul de intrare de tip tensiune într-un semnal de tip curent.

#### b) Etajul de amplificare în tensiune

> Al doilea etaj, dedicat amplificării semnalului, este de tip **trans impedanță** și transformă curentul provenit de la etajul de intrare într-un semnal de tensiune de amplitudine mare. Amplificarea în tensiune a acestui etaj este extrem de mare în **regim de buclă deschisă**. Pentru a asigura o funcționare stabilă și o amplificare utilă, se implementează obligatoriu o **buclă de reacție negativă**, care reduce amplificarea totală la o valoare controlată.

### 1.6.2. Caracteristici funcționale ale etajelor amplificatorului

Etajele amplificatorului sunt conectate în **cascadă**, ceea ce determină înmulțirea factorilor de amplificare individuali. Cu toate acestea, **etajul pilot** contribuie majoritar la amplificarea totală în tensiune a amplificatorului.

## 1.7. Componente adiționale

Pe lângă etajele de amplificare, circuitul este completat de următoarele componente:

- **Circuite de protecție**, care asigură fiabilitatea în condiții de funcționare anormală (suprasarcină, temperatură, etc.).

- **Generator de tensiune de referință**, care furnizează un semnal stabil utilizat ca punct de comparație pentru amplificatorul de eroare.

- **Rețea de reacție**, utilizată pentru controlul precis al tensiunii de ieșire prin ajustarea amplificării și stabilității circuitului.

Această arhitectură permite obținerea unei amplificări eficiente, cu performanțe stabile și adaptabile diverselor aplicații.

# 2. Funcționarea schemei

![](media/image2.emf)

(Fig. 2) Schema circuit stabilizator de tensiune cu ERS

![](media/image3.emf)

(Fig. 3) Tensiunea de referința si amplificatorul de eroare diferențial

Proiectul a fost realizat pentru N = 20

## 2.1. Referința de tensiune

Referința de tensiune este generată cu ajutorul unei **diodă Zener** (D₂​), alimentată printr-un curent constant asigurat de tranzistorul Q₁ și rezistența R₂​. Alegerea diodei Zener se face astfel încât tensiunea sa nominală (V_(Z)) să fie mai mică decât tensiunea minimă ce trebuie obținută la ieșire (V_(min)). În acest caz, s-a optat pentru o diodă Zener cu V_(Z) ​= 6.2V. *(Fig. 3)*

Curentul constant prin dioda Zener ​D₂ este generat de tranzistorul Q₁​, care formează o sursă de curent constant. Aceasta asigură o tensiune de referință stabilă pentru funcționarea optimă a schemei.

## 2.2. Etajul diferențial

Elementul central al schemei este **amplificatorul diferențial**, realizat cu tranzistoarele Q₃​ și Q₄​. Acesta este alimentat printr-o **sursă de curent constant**, formată din tranzistorul ​Q₂ și rezistența R₄​. *(Fig. 3)*

Rolul acestui etaj este de a realiza atât **amplificarea în tensiune**, cât și **amplificarea în curent**. Pentru îndeplinirea acestor sarcini se folosesc etaje specializate:

- **Etajul de intrare** facilitează adaptarea între sursa de semnal și amplificator.

- În plus, contribuie la **eliminarea fluctuațiilor** provenite de la sursa de alimentare, având un impact direct asupra raportului *semnal-zgomot*.

## 2.3. Stabilizarea tensiunii

Pentru a îmbunătăți stabilitatea circuitului, o diodă D₁ este utilizată pentru a menține tensiunea constantă pe sursele de curent constant. Aceasta fixează tensiunea pe rezistențele R₂​ și R₄​, ceea ce contribuie la stabilizarea generală a circuitului. *(Fig. 3)*

Astfel, integrarea diodei D₁​ reduce variațiile nedorite, îmbunătățind performanțele sursei de alimentare și menținând parametrii tensiunii de ieșire în limite stricte.

La pornire, **joncțiunea bază-emitor (BE)** a tranzistorului Q₁​ intră în conducție prin intermediul rezistorului R₁​. Curentul furnizat de această sursă poate fi calculat utilizând formula:

``` math
I_{C_{1}} = \frac{v_{z} - v_{BE}}{R_{2}}
```

``` math
I_{C_{1}} = 6mA
```

Curentul prin etajul diferențial este stabilit de rezistența R₄, având la borne o tensiune de aproximativ:

``` math
v_{z} - v_{BE}
```

Astfel, curentul I_(C2)​ este calculat ca:

``` math
I_{C2} = 0.8mA
```

Cum curentul colector al tranzistoarelor Q₃​ și Q₄​ este împărțit egal:

$`Ic_{3} + I_{C4} = \frac{Ic_{2}}{2}`$ → $`Ic_{3} = I_{C4} = 0.4mA`$

Rezistențele R₅​ și R₆​ furnizează curentul de polarizare pentru etajul următor. Rezistorul R₅​ este dimensionat astfel încât să asigure o cădere de tensiune minimă de 0.6V, necesară pentru a aduce în conducție tranzistorul Q₅​.

### **2.3.1. Componentele utilizate**

- Etajul diferențial este realizat cu tranzistoare bipolare PNP de tipul **BC856**.

- Etajul de emitor comun utilizează un tranzistor NPN de tipul **BC846**.

Aceste tranzistoare sunt adecvate, deoarece:

- Tensiunea de alimentare a circuitului este de 40V.

- Curentul colector pentru fiecare tranzistor diferențial Q₃​ și Q₄ este limitat la 0.4mA.

### 2.3.2. Etajul amplificator în tensiune

Etajul de amplificare în tensiune este format dintr-un singur tranzistor bipolar Q₅​, configurat ca **emitor comun**. Sarcina acestui etaj este rezistorul R₇​.

Curentul prin R₇​ poate fi determinat cunoscând că tensiunea la bornele acestuia este aproape întotdeauna egală cu:

``` math
V_{CC} - \ V_{OUT} + 2V_{BE}
```

Această configurație asigură funcționarea stabilă și precisă a circuitului.

Curentul I_(C5) este egal cu curentul I_(R7), iar relația acestuia poate fi exprimată astfel:

``` math
I_{C5} = I_{R7} = \frac{V_{CC} - V_{OUT} + 2V_{BE}}{R_{7}}
```

Amplificarea în tensiune a etajului emitor comun depinde de rezistența internă de emitor și de rezistența văzută în colector (adică a sursei de curent). Aceasta se poate calcula folosind formula:

``` math
A_{V5} = \frac{R_{7}}{R_{E5}}
```

Unde $`R_{E5} = \frac{V_{T}}{I_{C}}`$ , rezulta $`R_{E5} = \frac{25mV}{4mA} \cong 6\Omega`$

$`R_{7} = 4.7k\Omega`$, rezulta $`A_{V5} \cong 780`$

![](media/image4.emf)

(Fig. 4) Elementul regulator serie

## 2.4. Elementul regulator serie (ERS)

Elementul regulator serie este realizat pe baza unei conexiuni de **colector comun**. Acest tip de etaj oferă doar amplificare în curent și este numit și **etaj final**, deoarece asigură adaptarea către impedanța sarcinii. Scopul acestui etaj este să amplifice în curent, menținând în același timp o amplificare unitară în tensiune.

Pentru a asigura condiția de amplificare unitară în tensiune, vom utiliza o conexiune de tip **colector comun** realizată cu două tranzistoare bipolare în configurație **Darlington** (Q₆ si Q₇). Această configurație oferă cea mai mare amplificare în curent posibilă. Factorii de amplificare ai celor două tranzistoare se înmulțesc, rezultând o amplificare în curent de ordinul 10⁴. (Fig. 4)

Tranzistorul final este Q₇, care conduce cea mai mare parte a curentului. Din acest motiv, a fost ales modelul **MJD31**, deoarece poate suporta curenți de până la **3A** și poate disipa o putere mai mare decât alte modele de tranzistoare (pana la 25W, comparat cu altele care suporta pana la 250mW).

![](media/image5.emf)

(Fig. 5) Circuitul de protecție la supracurent

## 2.5. Circuitul de protecție la supracurent

Circuitul de protecție la supracurent Q₉ + R₁₀ + R₁₁ + R₁₂ este realizat cu un tranzistor bipolar NPN. Tensiunea V_(BE) a tranzistorului este generată de căderea de tensiune pe aceste rezistoare. Astfel, la curenți mari (\>0.5A), tranzistorul Q₉ va intra în conducție și va limita curentul de bază al regulatorului serie.

Pentru a obține o valoare precisă de 1.4 Ω, au fost utilizate trei rezistoare în serie.

Dimensionarea rezistorului se face conform relației:

``` math
R = \frac{V_{BE}}{I_{OMAX}}
```

R = R₁₀ + R₁₁ + R₁₂

Astfel, pentru un curent maxim de 0.5 A, rezultă o valoare de aproximativ 1.4 Ω pentru R.

![](media/image6.emf)

(Fig. 6) Circuitul de protecție la temperatură

## 2.6. Circuitul de protecție la temperatură

Circuitul de protecție la temperatură este realizat cu Q₈ și un divizor rezistiv format din P₂ și R₈.

Tensiunea bază-emitor pentru Q₈ este stabilită de divizor la un nivel care împiedică intrarea în conducție a tranzistorului Q₈ (aproximativ 400 mV). Totuși, la temperaturi ridicate, datorită coeficientului termic negativ al joncțiunilor din siliciu (−2 mV/°C), potențialul stabilit de divizor devine suficient de mare pentru ca Q₈ să intre în conducție.

Astfel, la temperaturi de peste **120°C**, se limitează curentul de bază al regulatorului serie, iar tensiunea de la ieșire scade către 0.

Potențialul V_(BE)​ este stabilit la aproximativ 400 mV conform raportului dintre P₂ și R₈, după relația:

$`V_{BE8} = V_{ref} \times \frac{P_{2}}{R_{8} + P_{2}}`$, unde $`V_{ref} = 6.2V`$

Din potențiometrul P₂ se reglează cu precizie valoarea temperaturii la care acționează protecția. In acest caz a fost reglat la 0.505 (2,525kΩ)

![](media/image7.emf)(Fig. 7) Rețeaua de reacție negativă

## 2.7. Rețeaua de reacție negativă

Rețeaua de reacție negativă este formata din potențiometrul P₁ si doua grupuri de rezistente: R₁₄, R₁₅ si R₁₆, R₁₇ . Acestea realizează un divizor de tensiune variabil din potențiometru care are ca scop reglarea tensiunii de ieșire.

Știm că $`V_{out\ min} = 10V,\ \ V_{out\ max} = 20V,{\ V}_{ref} = 6.2V\ `$

``` math
R = \frac{6.2}{10} = 0.62k\Omega
```

``` math
V_{ref} = V_{out\ min} \times \frac{P_{1} + R_{16} \parallel R_{17}}{P_{1} + R_{16} \parallel R_{17} + R_{14} + R_{15}} = 10V \times \frac{10}{10 + 6.28}k\Omega = 6.14V
```

``` math
R = \frac{6.2}{20} = 0.31k\Omega
```

``` math
V_{ref} = V_{out\ min} \times \frac{R_{16} \parallel R_{17}}{P_{1} + R_{16} \parallel R_{17} + R_{14} + R_{15}} = 10V \times \frac{5}{10 + 6.28}k\Omega = 6.14V
```

Din aceste relații, am ales valorile:

``` math
R_{14} = 0.6k\Omega,\ R_{15} = 5.6k\Omega,\ R_{16} = R_{17} = 10k\Omega\ \left( R_{16} \parallel R_{17} = 5k\Omega \right),\ {\ P}_{1} = 5k\Omega
```

# ![PSF - TENSIUNI](media/image8.emf)3. Punct static de funcționare (simulari)

![PSF - CURENTI](media/image9.emf)

(Fig. 8) Punct static de funcționare – afișare tensiuni

(Fig. 9) Punct static de funcționare – afișare curenți

![](media/image10.emf)

(Fig. 10) Punct static de funcționare – afișare puteri disipate

Se poate observa alegerea corecta a componentelor electrice si folosirea lor corespunzătoare. Au fost respectate toate cerințele impuse de producător, ba chiar la majoritatea a fost lăsata o marjă pentru siguranță.

# 4. Simulări funcționalitate

## ![](media/image11.png)4.1. Reglajul tensiunii de ieșire din potențiometrul P₁

(Fig. 11) Graficul variației tensiunii de ieșire din P₁

## ![](media/image12.png)4.2. Variația rezistenței de sarcina R_(LOAD)

(Fig. 12) Graficul variației rezistentei de sarcina, protecția la supra-curent

## 4.3. Variația tensiunii de intrare

![A graph with green line Description automatically generated](media/image13.png)(Fig. 13) Graficul variației tensiunii de intrare intre 36÷40V

## 4.4. Variația temperaturii, protecția de temperatura

![A grid with green lines Description automatically generated](media/image14.png)(Fig. 14) Graficul variației temperaturii, simulare pentru protecția de temperatura

Deriva termica este aproximativ 1.5mV/°C

## 4.5. Simularea amplificării in buclă deschisă

(Fig. 15) Graficul ![A screen shot of a black screen Description automatically generated](media/image15.png)amplificării de tensiune in buclă deschisă

Amplificatorul de eroare are A_(V) \> 3690

#   

# 5. Transfer Capture-PCB

![A computer circuit board with many different colored lines Description automatically generated](media/image16.png)(Fig. 16) PCB Design

**Cuprins**

[1. Stabilizatoarele de tensiune cu element de reglaj serie (ERS) [1](#stabilizatoarele-de-tensiune-cu-element-de-reglaj-serie-ers)](#stabilizatoarele-de-tensiune-cu-element-de-reglaj-serie-ers)

[1.1. Configurația generală a stabilizatoarelor cu amplificator operațional [1](#configurația-generală-a-stabilizatoarelor-cu-amplificator-operațional)](#configurația-generală-a-stabilizatoarelor-cu-amplificator-operațional)

[1.2. Funcționarea amplificatorului operațional [2](#funcționarea-amplificatorului-operațional)](#funcționarea-amplificatorului-operațional)

[1.3. Principiul funcționării [2](#principiul-funcționării)](#principiul-funcționării)

[1.4. Indicatori de performanță ai stabilizatoarelor liniare [2](#indicatori-de-performanță-ai-stabilizatoarelor-liniare)](#indicatori-de-performanță-ai-stabilizatoarelor-liniare)

[1.5. Protecții integrate în stabilizatoare [3](#protecții-integrate-în-stabilizatoare)](#protecții-integrate-în-stabilizatoare)

[1.6. Structura amplificatorului de eroare [3](#structura-amplificatorului-de-eroare)](#structura-amplificatorului-de-eroare)

[1.6.1. Etajele amplificatorului [4](#etajele-amplificatorului)](#etajele-amplificatorului)

[1.6.2. Caracteristici funcționale ale etajelor amplificatorului [4](#caracteristici-funcționale-ale-etajelor-amplificatorului)](#caracteristici-funcționale-ale-etajelor-amplificatorului)

[1.7. Componente adiționale [4](#componente-adiționale)](#componente-adiționale)

[2. Funcționarea schemei [6](#funcționarea-schemei)](#funcționarea-schemei)

[2.1. Referința de tensiune [7](#referința-de-tensiune)](#referința-de-tensiune)

[2.2. Etajul diferențial [7](#etajul-diferențial)](#etajul-diferențial)

[2.3. Stabilizarea tensiunii [7](#stabilizarea-tensiunii)](#stabilizarea-tensiunii)

[2.3.1. Componentele utilizate [8](#componentele-utilizate)](#componentele-utilizate)

[2.3.2. Etajul amplificator în tensiune [8](#etajul-amplificator-în-tensiune)](#etajul-amplificator-în-tensiune)

[2.4. Elementul regulator serie (ERS) [10](#elementul-regulator-serie-ers)](#elementul-regulator-serie-ers)

[2.5. Circuitul de protecție la supracurent [10](#circuitul-de-protecție-la-supracurent)](#circuitul-de-protecție-la-supracurent)

[2.6. Circuitul de protecție la temperatură [11](#circuitul-de-protecție-la-temperatură)](#circuitul-de-protecție-la-temperatură)

[2.7. Rețeaua de reacție negativă [12](#rețeaua-de-reacție-negativă)](#rețeaua-de-reacție-negativă)

[3. Punct static de funcționare (simulari) [13](#psf---tensiuni3.-punct-static-de-funcționare-simulari)](#psf---tensiuni3.-punct-static-de-funcționare-simulari)

[4. Simulări funcționalitate [15](#simulări-funcționalitate)](#simulări-funcționalitate)

[4.1. Reglajul tensiunii de ieșire din potențiometrul P₁ [15](#reglajul-tensiunii-de-ieșire-din-potențiometrul-p1)](#reglajul-tensiunii-de-ieșire-din-potențiometrul-p1)

[4.2. Variația rezistenței de sarcina R_(LOAD) [15](#variația-rezistenței-de-sarcina-rload)](#variația-rezistenței-de-sarcina-rload)

[4.3. Variația tensiunii de intrare [15](#variația-tensiunii-de-intrare)](#variația-tensiunii-de-intrare)

[4.4. Variația temperaturii, protecția de temperatura [16](#variația-temperaturii-protecția-de-temperatura)](#variația-temperaturii-protecția-de-temperatura)

[4.5. Simularea amplificării in buclă deschisă [16](#simularea-amplificării-in-buclă-deschisă)](#simularea-amplificării-in-buclă-deschisă)

[5. Transfer Capture-PCB [17](#transfer-capture-pcb)](#transfer-capture-pcb)
