Metodika hodnocení WebTop100
============================

Kritické problémy
-----------------
***0 bodů***

Web dostává 0 bodů, pokud obsahuje alespoň jeden z následujících problémů:

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

Prostor pro zlepšení
--------------------
***1 bod***

Web dostává 1 bod, pokud neobsahuje nic z předchozího, ale obsahuje alespoň jeden z následujících problémů:

- přihlašování přes HTTP
- *Not Found* stránka neposílá HTTP stavový kód 404
- nepoužitelná *Not Found* stránka (standardní stránka poskytovaná serverem)
- nehezké URL
- nepoužitelné vyhledávání
- inline CSS
- lze odeslat nevyplněné formuláře s vypnutým JS
- vyhledávání nenajde hlavní kategorie webu (např. bílé víno na webu s vínem)

Bez velkých chyb a nedostatků
-----------------------------
***2 body***

Web dostává 2 body, pokud neobsahuje nic z předchozího, ale obsahuje alespoň jeden z následujících problémů:

- chybějící soubor `robots.txt`
- nefunkční web bez `www` prefixu
- session cookie bez příznaku HttpOnly (jiné cookie mohou být bez tohoto příznaku)

Skvěle a inspirativně řešeno
----------------------------
***3 body***

Web dostává 3 body, pokud neobsahuje nic z předchozího, ale obsahuje alespoň jedno z následujících vylepšení:

- responzivní design (ne speciální mobilní verze)
