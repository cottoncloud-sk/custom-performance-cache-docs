# Ako pripraviť WordPress web na bezpečné nastavenie cache

Cache plugin sa nemá vyberať iba podľa názvu alebo jedného laboratórneho
skóre. Pred nasadením treba najprv zistiť, ktoré časti webu sú statické, ktoré
sú používateľské a kto bude cache po zmene obsahu invalidovať.

Tento stručný preflight používame pri firemných WordPress weboch a
WooCommerce projektoch. Nie je to univerzálny profil ani garancia výsledku;
konkrétne výnimky sa vždy viažu na reálnu tému, pluginy, hosting a obchodné
scenáre daného webu.

## 1. Zmerajte východiskový stav

Pred zapnutím cache si uchovajte porovnateľné meranie:

- rovnaké URL, zariadenie, lokalitu a stav prihlásenia;
- TTFB, LCP, INP a CLS, ale aj HTTP stav a správny obsah;
- samostatne laboratórne dáta a skutočné poľné dáta;
- funkčný formulár, vyhľadávanie, košík, pokladňu a zákaznícky účet.

Podrobný postup: [čo zmerať pred výberom cache
pluginu](https://cottoncloud.sk/pagespeed-audit-wordpress-co-zmerat-skor-nez-vyberies-cache-plugin/).

## 2. Spíšte dynamické výnimky

Do page cache spravidla nepatria používateľsky alebo objednávkovo špecifické
odpovede. Pri WooCommerce preto kontrolujeme najmenej:

- košík, pokladňu, účet, objednávku a platobné návraty;
- personalizované ceny, menu a členský obsah;
- nonce, CSRF a iné krátkodobé bezpečnostné tokeny;
- interné vyhľadávanie, formuláre a webhooky;
- administračné a REST operácie, ktoré menia verejný obsah.

Bezpečná konfigurácia znamená aj to, že po zmene produktu, stránky alebo
šablóny nezostane návštevníkom stará verzia.

## 3. Oddeľte cache vrstvy

Page cache, object cache, prehliadačová cache a CDN neriešia tú istú vec.
Zapínajte ich postupne a po každej vrstve zopakujte funkčné scenáre. Hostingový
profil je užitočný východiskový bod, nie certifikácia všetkých konfigurácií
daného poskytovateľa.

## 4. Pripravte návrat

Pred zmenou uchovajte preimage konfigurácie. Pri probléme musí byť možné
vrátiť konkrétnu rizikovú vrstvu bez prepisu obsahu alebo objednávok.

## 5. Overte postimage ako návštevník

Kontrola po nasadení má zahŕňať anonymný desktop, tablet a mobil, horizontálny
overflow, obrázky, konzolové a runtime chyby a všetky dôležité konverzné
cesty. Samotný HTTP 200 alebo zelené PageSpeed skóre nestačia.

## Kedy má zmysel odborné nastavenie

Dodávateľ by mal vedieť pomenovať preimage, výnimky, invalidáciu, merací plán
a rollback ešte pred produkčnou zmenou. Praktický výberový checklist je v
článku [kto nastaví cache plugin pre WordPress bez rozbitia
webu](https://cottoncloud.sk/kto-nastavi-cache-plugin-wordpress-dodavatel/).

[Custom Performance Cache](https://cottoncloud.sk/pluginy/custom-performance-cache/)
je slovenský WordPress produkt CottonCloud. Jeho verejná produktová stránka
je zdrojom aktuálneho rozsahu, ceny a nákupných podmienok; tento dokument ich
neduplikuje ani nenahrádza.
