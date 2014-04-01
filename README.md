Metodika hodnocení WebTop100
============================

Všechny weby začínají s plným počtem bodů. Podle nalezených prohřešků a vylepšení se danému webu poté
strhávají a přičítají body podle závažnosti prohřešku nebo vylepšení.

Kritické prohřešky
------------------
***-10 bodů***

- XSS, SQLI, FPD, LFI, RFI
- `/info.php`
- *Black hat* SEO
- *Not Found* stránka přesměrována na titulní stránku
- všechny stránky mají stejný `TITLE`
- tabulkový layout
- tagy FONT v kódu
- HTTPS certifikáty podepsané nedůvěryhodnou CA
- přítomnost skriptu, přes který se dá posílat spam
- heslo zaslané e-mailem, při registraci nebo zapomenutí

Závažné prohřešky
-----------------
***většinou -2 body***

- přihlašování přes HTTP
- *Not Found* stránka neposílá HTTP stavový kód 404
- nepoužitelná *Not Found* stránka (standardní stránka poskytovaná serverem)
- nehezké URL
- nepoužitelné vyhledávání
- inline CSS
- lze odeslat nevyplněné formuláře s vypnutým JS

Prohřešky
---------
***něco kolem -1 bodu***

- chybějící soubor `robots.txt`
- nefunkční web bez `www` prefixu
- Flashové ovládací prvky vyžadují kliknutí navíc pro jejich aktivaci

Menší prohřešky
---------------
***většinou neovlivňují hodnocení (-0 bodu)***

- HTML entity místo českých znaků

Podstatné vylepšení
-------------------
***+2 body***
