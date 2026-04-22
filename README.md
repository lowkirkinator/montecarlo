# 📈 Komplett Frågebank: Beräkningsmetoder för Finansiell Matematik

Välkommen till den kompletta samlingen av övningar och konceptuella frågor för kursen. Dokumentet täcker allt från slumptalsgenerering till avancerade PDE- och Fouriermetoder.

---

## 🎲 Ämne 1: Slumptalsgenerering och Binomialträd

### Originalfrågor från Exercises
**Fråga 1.1 (Lätt) - LCG**
Givet en linjär kongruensgenerator (LCG) som definieras av sekvensen $x_{n+1} = (ax_n + c) \mod m$, förklara hur denna talsekvens kan användas för att generera likformigt fördelade slumptal i intervallet $[0,1)$.

**Fråga 1.2 (Medel) - Inversa transform-metoden**
Anta att vi vill generera slumptal från en exponentiell fördelning. Generera formeln för detta genom att införa ett likformigt fördelat slumptal $U$ från intervallet $[0,1)$ och beräkna $x = F^{-1}(U)$, där $F$ är den kumulativa fördelningsfunktionen (CDF) för exponentialfördelningen.

**Fråga 1.3 (Medel) - Acceptans-rejektionsmetoden**
Vi vill generera standardnormalfördelade slumptal $Z \sim \mathcal{N}(0,1)$ men har bara tillgång till en likformig slumptalsgenerator. Vi förenklar problemet till att generera fördelningen för absolutbeloppet $Y = |Z|$.
1. Härled täthetsfunktionen $f$ för $Y$.
2. Använd exponentialfördelningen (täthetsfunktion $g$) som kandidatfördelning. Hitta $c > 0$ så att $f(y) \le c \cdot g(y)$ för alla $y \ge 0$.
3. Hitta det optimala valet av $c$ och den motsvarande hastighetsvariabeln (rate) för exponentialfördelningen.

**Fråga 1.4 (Medel) - Enperiods binomialmodell**
Betrakta en enperiods binomialmodell för ett aktiepris. Aktiepriset vid tiden $t=0$ är $S_0$. Låt räntan vara $r$ och tidssteget $\Delta t = 1$. Aktiepriset kan antingen gå upp med en faktor $u$ eller ner med en faktor $d$. Låt $f: \mathbb{R} \to \mathbb{R}$ vara en godtycklig utbetalningsfunktion.
1. Härled formeln för den riskneutrala sannolikheten $q = \frac{1+r-d}{u-d}$.
2. Beräkna det förväntade diskonterade utbetalningsvärdet vid $t=1$ under det riskneutrala måttet.
3. Bestäm hedging-strategin $\Phi$ vid $t=0$ för att replikera utbetalningen.

**Fråga 1.5 (Lätt) - Flerperiods binomialmodell**
Ställ upp den rekursiva algoritmen för att beräkna priset för ett derivat med utbetalningsfunktionen $H = h(S_0, ..., S_T)$ i en binomialmodell med $T$ tidssteg vid tiden $t=0$.

### Modifierade & Konceptuella Frågor
**Fråga 1.6 (Medel) - Modifierad Enperiodsmodell**
Använd formlerna från Fråga 1.4. Anta nu att $S_0 = 100$, $u = 1.25$, $d = 0.8$, och räntan är $r = 5\%$. Beräkna priset på en europeisk säljoption (put option) istället för en köpoption, med lösenpris $K = 100$. Beräkna även hedging-portföljen. Vad säger tecknet på $\Phi$ om din position i den underliggande tillgången?

**Fråga 1.7 (Lätt) - Koncept: PRNG**
Enligt Definition 2.1.1 från slidesen, vad är en pseudo-random number generator (PRNG)? Ange dess beståndsdelar och förklara varför sekvensen som genereras så småningom alltid måste upprepa sig (vara periodisk).

---

## 🎯 Ämne 2: Monte Carlo-metoder och Väntevärdesriktiga Skattare

### Originalfrågor från Exercises
**Fråga 2.1 (Lätt) - Unbiasedness**
Låt $X_1, ..., X_n$ vara oberoende och likafördelade stokastiska variabler (iid) med ändligt väntevärde $\mathbb{E}[X] = \mu$ och varians $\text{Var}[X] = \sigma^2$. Låt $f: \mathbb{R} \to \mathbb{R}$ vara en mätbar funktion. Bevisa att stickprovsmedelvärdet $I_M[f;X] := \frac{1}{M}\sum_{i=1}^M f(X_i)$ är en väntevärdesriktig skattare.

**Fråga 2.2 (Medel) - Variansskattning**
Utifrån villkoren i Fråga 2.1, bevisa att $\sigma_M^2(f;X) := \frac{1}{M-1}\sum_{i=1}^M (f(X_i) - I_M[f;X])^2$ är en väntevärdesriktig skattare för $\sigma^2(f;X) = \text{Var}[f(X)]$.

**Fråga 2.3 (Svår) - Harris Olikhet**
Bevisa Harris Olikhet för fallet $k=1$. (Teorem: Låt $f,g: \mathbb{R} \to \mathbb{R}$ vara växande funktioner. Då gäller $\mathbb{E}[f(Z)g(Z)] \ge \mathbb{E}[f(Z)]\mathbb{E}[g(Z)]$, vilket ekvivalent innebär att $\text{Cov}(f(Z), g(Z)) \ge 0$).

**Fråga 2.4 (Medel) - Quasi-Monte Carlo (Ny)**
Förklara skillnaden mellan Plain Monte Carlo och Randomized Quasi-Monte Carlo (RQMC). Varför vill man randomisera en lågdiskrepanssekvens (t.ex. Sobol) genom en "random shift"? Relatera detta till skattningens varians.

### Modifierade & Konceptuella Frågor
**Fråga 2.5 (Medel) - Omvänd Harris olikhet**
Anta istället att $f$ är en strängt växande funktion och $g$ är en strängt avtagande funktion. Vad kan vi nu dra för slutsats om $\text{Cov}(f(Z), g(Z))$? Bevisa ditt påstående genom att använda substitutionen $\tilde{g}(z) = -g(z)$.

**Fråga 2.6 (Medel) - Antithetic Variates**
Förklara variansreduktionstekniken Antithetic Variates. Visa matematiskt under vilket villkor denna metod faktiskt leder till en minskad varians jämfört med Plain Monte Carlo-skattaren.

**Fråga 2.7 (Svår) - Koksma-Hlawkas olikhet**
Förklara Koksma-Hlawkas olikhet och kontrastera dess "worst-case"-felgräns (som beror på Hardy-Krause variationen och stjärndiskrepansen) med den probabilistiska "average-case"-felgränsen från Plain Monte Carlo (som beror på Centrala Gränsvärdessatsen).

---

## 📈 Ämne 3: Ito-kalkyl, Martingaler och SDE:er

### Originalfrågor från Exercises
**Fråga 3.1 (Lätt) - Brownska Egenskaper**
Låt $B_t^1$ och $B_t^2$ vara två oberoende Brownska rörelser, och låt $\rho \in [-1,1]$. Definiera processerna $W_t^1 = B_t^1$ och $W_t^2 = \rho B_t^1 + \sqrt{1-\rho^2}B_t^2$.
1. Visa att $W^1$ och $W^2$ är Brownska rörelser.
2. Bevisa att den kvadratiska samvariationen är $\langle W^1, W^2 \rangle_t = \rho t$.

**Fråga 3.2 (Medel) - Itos Lemma**
Använd Itos lemma för att beräkna dynamiken $dZ_t$ för följande processer, givet att $dX_t = \alpha X_t dt + \sigma X_t dW_t$:
1. $Z_t = \exp(\alpha W_t)$
2. $Z_t = \frac{1}{X_t}$
3. $Z_t = \ln(X_t)$
4. $Z_t = X_t^2$

**Fråga 3.3 (Medel) - Martingalbevis**
Låt $\sigma(t)$ vara en deterministisk funktion och $X_t = \int_0^t \sigma(s)dW_s$.
Visa att processen $M_t := \exp\left( \lambda \int_0^t \sigma(s)dW_s - \frac{1}{2}\int_0^t (\lambda\sigma(s))^2 ds \right)$ för $\lambda > 0$ är en martingal.

**Fråga 3.4 (Medel) - Geometrisk Brownsk Rörelse**
Givet SDE:n $dS_t = \mu S_t dt + \sigma S_t dW_t$. Använd substitutionen $Y_t = \ln(S_t)$ och Itos formel för att härleda den explicita lösningen för $S_t$.

**Fråga 3.5 (Svår) - Ornstein-Uhlenbeck**
Betrakta SDE:n $dr_t = (b - ar_t)dt + \sigma dW_t$. Inför processen $Y_t = e^{at}r_t$, och använd Itos formel för att lösa ekvationen explicit. Visa att den asymptotiska fördelningen då $t \to \infty$ är $\mathcal{N}\left(\frac{b}{a}, \frac{\sigma}{\sqrt{2a}}\right)$.

**Fråga 3.6 (Svår) - Heston-modellen (Ny)**
Ställ upp Euler-Maruyama-schemat för Heston-modellen. Förklara problematiken med att volatiliteten $v_t$ kan bli negativ i det diskreta schemat, och beskriv hur "Truncated" och "Reflected" Euler-Maruyama löser detta.

**Fråga 3.7 (Medel) - Multi-Level Monte Carlo (Ny)**
Förklara grundkonceptet bakom MLMC (Multi-Level Monte Carlo) för att lösa en SDE. Hur används en teleskopsumma av väntevärden över olika diskretiseringsnivåer $l$ för att optimera beräkningskostnaden?

### Modifierade & Konceptuella Frågor
**Fråga 3.8 (Medel) - Heltalspotenser av GBM**
Beräkna dynamiken för logaritmen av den Geometriska Brownska rörelsen upphöjt till ett heltal $n \ge 1$. Det vill säga, låt $Y_t = \ln(S_t^n)$ där $dS_t = \mu S_t dt + \sigma S_t dW_t$. Beräkna $dY_t$.

**Fråga 3.9 (Lätt) - Martingaldefinitioner**
Definiera formellt en martingal, en submartingal och en supermartingal. Ge ett exempel på en egenskap hos den Brownska rörelsen som bygger på martingalbegreppet.

**Fråga 3.10 (Medel) - Levys Karaktärisering**
Vad innebär Levys karaktärisering av den Brownska rörelsen? Om $Y_t = \int_0^t \text{sign}(W_s) dW_s$, bevisa med hjälp av Levys sats att $Y_t$ också är en Brownsk rörelse.

---

## 🧮 Ämne 4: PDE-metoder och Transformationer

### Originalfrågor från Exercises
**Fråga 4.1 (Svår) - Black-Scholes till Värmeledningsekvationen**
Priset $u(t,S)$ för en europeisk köpoption i Black-Scholes-modellen satisfierar:
$$\partial_t u + rS \partial_S u + \frac{1}{2}\sigma^2 S^2 \partial_{SS} u - ru = 0$$
med slutvillkoret $u(T,S) = (S-K)^+$. Använd transformationen:
$$v(x,\tau) = \frac{u(S,t)}{K} \exp\left( \frac{1}{2}(q-1)x + \left(\frac{1}{4}(q-1)^2 + q\right)\tau \right)$$
där $x = \ln(S/K)$, $\tau = \frac{(T-t)\sigma^2}{2}$ och $q = \frac{2r}{\sigma^2}$.
Visa steg-för-steg att $u$ satisfierar Black-Scholes PDE om och endast om $v$ satisfierar den klassiska värmeledningsekvationen $\partial_\tau v = \partial_{xx} v$.

**Fråga 4.2 (Svår) - Fouriertransform för en Säljoption**
Beräkna den kontinuerliga Fouriertransformen för utbetalningsfunktionen av en dämpad europeisk säljoption, $f_R(x) = e^{-Rx}(K - e^x)^+$. För vilka värden på dämpningsparametern $R$ är denna funktion integrerbar i $L^1(\mathbb{R})$?

**Fråga 4.3 (Medel) - COS-metoden (Ny)**
Använd log-moneyness transformationen $x = \ln(S_0/K)$ för att härleda payoffen för en "vanilla call option" som $f(x) = K(e^x - 1)^+$. Ställ sedan upp den analytiska integralen för COS-koefficienterna $H_k$.

### Modifierade & Konceptuella Frågor
**Fråga 4.4 (Svår) - Säljoptionens Randvillkor**
Tillämpa transformationen från Fråga 4.1, men för en säljoption (put) istället för en köpoption. Vilket startvillkor $v(x,0)$ (vid $\tau=0$) får vi? Vilka asymptotiska randvillkor gäller för $x \to \infty$ respektive $x \to -\infty$?

**Fråga 4.5 (Medel) - Feynman-Kac teorem**
Förklara, utifrån Feynman-Kac, sambandet mellan att lösa en Cauchy-PDE och att beräkna ett förväntat värde under ett riskneutralt mått. Vilka krav ställs på den polynomiella tillväxten för lösningen?

---

## 🧠 Ämne 5: Olikheter & Mångdisciplinära Problem

### Olikheter från Inequalities.pdf
**Fråga 5.1 (Medel) - Jensens och Markovs Olikhet**
1. Formulera Jensens olikhet för en konvex funktion $\phi$.
2. Formulera Markovs olikhet och visa hur den direkt leder till Chebychevs olikhet genom att välja $h(x) = |x|^p$.

**Fråga 5.2 (Svår) - Youngs och Hölders Olikhet**
1. Ange Youngs olikhet ($ab \le \frac{a^p}{p} + \frac{b^q}{q}$).
2. Hur används Youngs olikhet traditionellt för att bevisa Hölders olikhet ($\|fg\|_1 \le \|f\|_p \|g\|_q$)?

### Kombinerade Master-frågor
**Fråga 5.3 (Svår) - Olikheter + Martingaler**
Låt $M_t = \int_0^t u_s dW_s$ vara en kontinuerlig Ito-integral. Genom att kombinera Doobs maximala olikhet (som ger $\mathbb{P}[X_t^* \ge \lambda] \le \frac{1}{\lambda} \mathbb{E}[X_t]$ för icke-negativa submartingaler) med Itos isometri,
