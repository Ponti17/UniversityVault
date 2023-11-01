# Fordelinger

## Sandsynlighed og Fraktiler

Når man taler om et tilfældigt variabel kaldes dette for et **stokastisk variabel**. Et stokastisk variabel benævnes ofte med et stort bogstav (typisk $X$).  Hvis $x$ er et reelt tal så angives sandsynligheden for at en måling af en stokastisk variabel antager en værdi der er mindre end $x$ som
$$ P(X \leq x) $$
Ønsker man derimod at gå den anden vej givet en sandsynligheden $p$, så kaldes $x$ for $p$-fraktilen.  For sandsynligheder har vi
$$ P(X > x) = 1 - P(X \leq x) $$
$$ P(x \leq X \leq y) = P(X \leq y) - P(X < x) $$
## Normalfordelingen

Normalfordelingen er den klasse af fordelinger som beskrives af tæthedsfunktionen
$$ f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{- \frac{(x - \mu)^2}{2\sigma^2} } $$
Det er altså en fordelingen der er entydigt beskrevet af dens middelværdi og spredning. For at teste om et datasæt er normalfordelt kan man tegne et qq-plot. Hvis punkterne i dette plot ligger tilnærmelsesvis på en ret linje kan det antages at datasættet er normalfordelt. 

I forbindelse med normalfordelingen har vi følgende symboler:

$\mu:$ Bruges som middelværdien.
$\bar{x}$: Bruges om det beregnede gennemsnit for stikprøven. Dette tal er et gæt på $\mu$.
$\sigma$: Bruges om spredningen for populationen. 
$SD$: Den spredning som man kan beregne ud fra stikprøven. Dette tal et et gæt på $\sigma$. 

Nedenunder vises tæthedsfunktionen af den normerede normalfordelingen ($\mu = 0, \sigma = 1$).
![[normfordeling-0-1.png]]
Arealet under grafen angiver sandsynligheden for at få en værdi på et bestemt interval. 

## t-fordelingen

t-fordelingen specificeres af et enkelt tal der kaldes "frihedsgrader".  Når antallet af frihedsgrader vokser mod uendelig, så vil t-fordelingen mere og mere ligne en normalfordeling med middelværdi 0 og spredning 1.
![[t-dist.png]]