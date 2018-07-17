Hodnocení technického řešení
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
- web přesměrovává na HTTPS, ale má certifikáty podepsané nedůvěryhodnou CA nebo neposílá *intermediate* certifikáty
- přítomnost skriptu, přes který se dá posílat spam
- heslo zaslané e-mailem, při registraci nebo zapomenutí
- přihlašování přes HTTP (týká se uživatelů i příp. administračních rozhraní na "předvídatelných" adresách `/admin` a dalších)
- možnost ze serveru získat zdrojové kódy nebo informace o nich (např. ze souboru `/.git/HEAD`, z výpisu adresářů apod.)
- použití JavaScriptových knihoven [se známými zranitelnostmi](https://developers.google.com/web/tools/lighthouse/audits/vulnerabilities)
- web běží na volně dostupném redakčním systému (Wordpress aj. včetně doplňků) se známými zranitelnostmi

Prostor pro zlepšení
--------------------
***1 bod***

Web dostává 1 bod, pokud neobsahuje nic z předchozího, ale obsahuje alespoň jeden z následujících problémů:

- *Not Found* stránka neposílá HTTP stavový kód 404
- všechny *Not Found* stránky jsou nepoužitelné (standardní stránky poskytované serverem)
- nehezké URL
- WebPagetest Speed Index 9000 a více (pro první i další načtení)
- chybějící, nenačtené obrázky na stránce

Bez velkých chyb a nedostatků
-----------------------------
***2 body***

Web dostává 2 body, pokud neobsahuje nic z předchozího, ale obsahuje alespoň jeden z následujících problémů:

- chybějící soubor `robots.txt`
- nefunkční web bez `www` prefixu
- session cookie bez příznaku HttpOnly (jiné cookie mohou být bez tohoto příznaku)
- 2 nebo méně bezpečnostních hlaviček¹
- WebPagetest Speed Index 6000-8999 (pro první i další načtení)
- stránky jsou dostupné pomocí HTTP, prohlížeč není přesměrován na HTTPS
- některé *Not Found* nebo *Forbidden* (HTTP kódy 4xx) jsou standardní stránky poskytované serverem

Výborné řešení
--------------
***3 body***

Web dostává 3 body, pokud neobsahuje nic z předchozího, ale chybí mu něco z kategorie [Skvěle a inspirativně řešeno](#skvěle-a-inspirativně-řešeno).

Skvěle a inspirativně řešeno
----------------------------
***4 body***

Web dostává 4 body, pokud neobsahuje nic z předchozího a má navíc všechna následující vylepšení:

- responzivní design (ne speciální mobilní verze)
- 4 nebo více bezpečnostních hlaviček¹
- WebPagetest Speed Index 0-2999 (pro první i další načtení)
- *Potential Compressed Weight* z [Website Speed Testu](https://webspeedtest.cloudinary.com/) nad 50 %

-----
¹Bezpečnostními hlavičkami jsou myšleny následující HTTP hlavičky, testují se pomocí [securityheaders.com](https://securityheaders.com):
- `X-Frame-Options`
- `X-Content-Type-Options`
- `Content-Security-Policy`
- `Strict-Transport-Security`
- `X-XSS-Protection`
- `Referrer-Policy`
