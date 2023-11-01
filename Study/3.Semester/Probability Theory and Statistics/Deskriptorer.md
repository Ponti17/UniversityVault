# Beregninger
---
## Middelværdi

Middelværdien (eller gennemsnittet) betegnes $\bar{x}$ og beregnes med formlen
$$ \bar{x} = \frac{\sum_{i=1}^n x_i}{n} $$
## Sprednings/Varians

Spredningen af et datasæt betegnes $SD$ eller $\sigma^2$ og beregnes efter formlen
$$ SD = \sqrt{ \frac{\sum_{i=1}^n (\bar{x} - x_i)^2}{n-1} } $$
Spredningen kaldes ofte standardafvigelse. Spredningen siger noget om hvor langt de enkelte målinger spreder sig fra middelværdien. Variansen er kvadratet på spredningen
$$ \sigma = \sqrt{ \sigma^2 } $$

## Variationskoefficient

Variationskoefficienten $CV$ er defineret som
$$ CV = \frac{SD}{\bar{x}} $$
Altså spredningen delt med middelværdien. Denne størrelse er interessant hvis man skal vurdere om en spredning er stor eller lille. 

## Standardfejl

Standardfejlen eller StandardError (SE) eller Standard Error of Mean (SEM) er defineret som
$$ SEM = \frac{SD}{\sqrt{n}} $$
Denne størrelse udtrykker usikkerheden på gennemsnittet af $n$ målinger. ($SD$ er usikkerheden på hver af målingerne). Vi bemærker at jo flere målinger man har jo mindre er usikkerheden.

## Median

I nogle sammenhænge, ofte ved små datasæt, kan det være en dårlig ide at bruge gennemsnittet. Egentlig må middelværdien kun bruges når datasættet er normalfordelt. Medianen bestemmes ved at opstille tallene i stigende rækkefølge og så vælge det midterste tal. Hvis man har et lige antal data vælger man gennemsnittet af de to tal i midten i.e. medianen af $(3,4,6,7)$ er $(4+6)/2 = 5$.
