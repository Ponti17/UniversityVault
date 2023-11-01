# Konfidensintervaller

Formlen til beregning af et 95%-konfidensinterval for middelværdien i en normalfordelt population er
$$ 95\%\textrm{-konfidensinterval} = \Biggl[ \bar{x} - t_{0.975}(f) \frac{SD}{\sqrt{n}}; \bar{x} + t_{0.975}(f) \frac{SD}{\sqrt{n}} \Biggr]$$
Hvor
$\bar{x}$: Angiver stikprøvens gennemsnits. 
$SD$: Angiver stikprøvens spredning
$n$: Angiver antal målinger brugt til beregning af gennemsnittet.
$f$: Er antallet af frihedsgrader hørende til spredningen $SD$. 
$t_{0.975}$: Er 0.975 fraktilen i t-fordelingen med $f$ frihedsgrader. 

## Frihedsgrader og n

$n$ indgår i beregningen af $SEM$, sammen med $SD$. Der er dog INGEN sammenhæng mellem disse størrelser. Antal frihedsgrader $f$ er fastlagt af $SD$. 

Ofte vil $SD$ og $n$ være bestemt ved hjælp af den samme stikprøve. Her vil det gælde at $f = n - 1$. 

## Konfidensinterval for middelværdi

Vi betagter en stikprøve fra en normalfordeling med middelværdi $\mu_0$ og spredning $\sigma$. Stikprøvens gennemsnit betegnes som sædvanlig med $\bar{x}$, dens spredning med $SD$ og antallet af målinger i stikprøven med $n$. Hvis man gentagne gange laver sådan en stikprøve og hver gang beregner størrelsen:
$$ t = \frac{ \bar{x} - \mu_0 }{SD / \sqrt{n}} $$
så vil denne størrelse være t-fordelt. Antallet af frihedsgrader for denne t-fordeling er lig med antallet af frihedsgrader for $SD$. 

Ovenstående kan anvedes til at vurdere om en given værdi af $\mu_0$ er "rimelig", og dermed til at beregne et interval som indeholder de "rimelige" værdier af $\mu_0$. 