# 📈 Frågebank: Beräkningsmetoder för Finansiell Matematik

Välkommen till den kompletta frågebanken. Alla formler renderas med $\LaTeX$.

---

## 1. Slumptal & Binomialmodeller
### 1.1 Inversa Transformmetoden (Medel)
Låt $U \sim \mathcal{U}(0,1)$. Härled formeln för att generera slumptal från en Pareto-fördelning med täthetsfunktion:
$$f(x) = \frac{\alpha x_m^\alpha}{x^{\alpha+1}}, \quad x \ge x_m$$

### 1.2 Riskneutral Prissättning (Medel)
I en enperiods binomialmodell, visa att den riskneutrala sannolikheten $q$ måste vara:
$$q = \frac{1+r-d}{u-d}$$
för att förhindra arbitrage. Vad händer om $1+r > u$?

---

## 2. Monte Carlo & Variansreduktion
### 2.1 Harris Olikhet (Svår - Bevis)
Låt $f, g$ vara växande funktioner. Bevisa att:
$$\text{Cov}(f(Z), g(Z)) \ge 0$$
och förklara varför detta är relevant för *Antithetic Variates*.

### 2.2 Control Variates (Medel)
Vi vill skatta $I = \mathbb{E}[f(X)]$ med hjälp av en kontrollvariabel $Y$ där $\mathbb{E}[Y] = \mu_Y$ är känd. Härled den optimala koefficienten $b^*$ som minimerar variansen för:
$$\hat{I}_{CV} = f(X) - b(Y - \mu_Y)$$

---

## 3. Ito-kalkyl & Martingaler
### 3.1 Itos Lemma (Medel)
Låt $dX_t = \mu X_t dt + \sigma X_t dW_t$. Beräkna dynamiken $dZ_t$ för processen:
$$Z_t = \frac{1}{X_t}$$

### 3.2 Martingalegenskaper (Svår - Bevis)
Visa att den geometriska Brownska rörelsen $S_t = S_0 e^{(\mu - \frac{1}{2}\sigma^2)t + \sigma W_t}$ är en martingal om och endast om $\mu = 0$.

---

## 4. SDE & Numeriska Metoder
### 4.1 Milstein vs Euler (Medel)
Härled Milstein-schemat för en godtycklig SDE $dX_t = a(X_t)dt + b(X_t)dW_t$. Varifrån kommer termen $\frac{1}{2}b(X_n)b'(X_n)((\Delta W_n)^2 - \Delta t)$?

### 4.2 Ornstein-Uhlenbeck (Svår)
Lös SDE:n $dX_t = \kappa(\theta - X_t)dt + \sigma dW_t$ explicit genom att använda den integrerande faktorn $e^{\kappa t}$.

---

## 5. PDE & Finita Differenser
### 5.1 Black-Scholes Transformation (Svår)
Visa att genom substitutionen $x = \ln(S/K)$ och $\tau = \frac{\sigma^2}{2}(T-t)$, kan Black-Scholes PDE transformeras till värmeledningsekvationen:
$$\frac{\partial v}{\partial \tau} = \frac{\partial^2 v}{\partial x^2}$$

### 5.2 $\theta$-schemat (Medel)
Ställ upp tidsdiskretiseringen för värmeledningsekvationen med $\theta$-metoden. För vilka värden på $\theta$ är schemat ovillkorligt stabilt?

---

## 6. Fourier & COS-metoden
### 6.1 Fourier-transform för Put (Medel)
Beräkna den dämpade Fourier-transformen $\hat{f}_R(u)$ för en europeisk säljoption med payoff $(K - e^x)^+$.

---

## 7. Viktiga Olikheter
### 7.1 Jensens Olikhet
Låt $\phi$ vara en konvex funktion. Visa att:
$$\phi(\mathbb{E}[X]) \le \mathbb{E}[\phi(X)]$$
Tillämpa detta för att visa att priset på en köpoption är en konvex funktion av lösenpriset $K$.
