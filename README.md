Metodika hodnocení WebTop100
============================

Hodnocené weby se posuzují individuálně. Tento seznam je pouze základ a je tedy možné do hodnocení konkrétních webů přidat některá další kritéria a je potom na garantovi, aby s porotcem probral jejich váhu. Příkladem může být mobilní verze webu, na kterém se ihned po načtení začne načítat 20 MB video. Takové pravidlo v tomto seznamu není, ale dává smysl jej v hodnocení zohlednit.

Kritické problémy
-----------------
***0 bodů***

Web dostává 0 bodů, pokud obsahuje alespoň jeden z uvedených problémů. Při nalezení je potřeba zvážit jejich závažnost. Pokud bude na dvou stránkách ze sta stejný titulek, tak není důvod o webu tvrdit, že má kritické problémy. To samé se týká tabulkového layoutu a značek `FONT` v kódu.

Pokud web obsahuje uvedenou technickou chybu, která by mohla vést k nějakému bezpečnostnímu problému, tak nezáleží na kolika místech a kde se vyskytuje. Neprovádíme bezpečnostní test, nehledáme bezpečnostní chyby, nebereme v potaz dopad těchto chyb, neurčujeme jejich závažnost. Weby *nehackujeme*, ani nezkoušíme, jakou zátěž servery vydrží. Hledáme *pouze* technické chyby, tedy například místa, kde vývojáři zapomněli při výpisu nahradit `<` za `&lt;` nebo kde zobrazují neošetřené chybové hlášky programovacího jazyka. Pro hledání takových chyb nepoužíváme žádné automatizované skenovací nástroje. Použití jednoúčelových nástrojů pro zrychlení práce není vyloučeno.

- zobrazení neošetřené chybové hlášky obsahující důležité systémové informace (*Full Path Disclosure*)
- neošetřené uživatelem zadané znaky `<`, `>`, `"`, `'` při výpisu (může vést k útoku *Cross-Site Scripting*)
- špatně ošetřený uživatelský vstup při odesílání dotazů do databáze (riziko útoku *SQL Injection*)
- Vložení místního nebo vzdáleného souboru (*Local File Inclusion*, *Remote File Inclusion*)
- výstup z funkce `phpinfo()` (`/info.php`, `/phpinfo.php`, apod.)
- *Black hat* SEO
- *Not Found* stránka přesměrována na titulní stránku
- všechny stránky mají stejný `TITLE`
- tabulkový layout
- tagy `FONT` v kódu
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
- web běží pouze na HTTPS
- hlavička `Content-Security-Policy`
- hlavička `X-XSS-Protection`
