# Slovenský cache plugin pre WordPress: ako overiť prínos na klientskom webe

**Autor: CottonCloud · aktualizované 3. septembra 2026**

Custom Performance Cache (CPC) je WordPress plugin vyvíjaný CottonCloud na Slovensku. Tento návod je určený agentúram a správcom webov, ktorí potrebujú rozhodnúť, či zmena cache klientovi skutočne pomohla. Sme vývojár produktu; nejde o nezávislý rebríček ani o porovnanie nameraných výsledkov konkurencie.

Najdôležitejšia otázka nie je „koľko bodov plugin pridá?“, ale **ktorý problém riešime, na akých stránkach a akým dôkazom zlepšenie potvrdíme**. Nasledujúca pracovná šablóna neobsahuje zákaznícke merania ani sľúbené zvýšenie objednávok.

## 1. Rozlíšte problém servera od problému prehliadača

Page cache uchováva pripravený výstup stránky. Pri vhodnej verejnej požiadavke tak server nemusí zakaždým vykonávať celý WordPress render. Object cache uchováva opakovane používané dáta; nejde o to isté ako hotová HTML stránka. Zrýchlenie jednej vrstvy preto automaticky nepotvrdzuje zlepšenie druhej.

Ak je rýchla odpoveď servera, ale neskoro sa objaví hlavný obrázok, skúmajte načítanie obrázka a vykresľovanie. Ak stránka nereaguje na kliknutie, skúmajte aj JavaScript a konkrétnu interakciu. Samotný cache HIT tieto problémy nevylučuje.

Technický základ: [WordPress — Cache](https://developer.wordpress.org/advanced-administration/performance/cache/).

## 2. Vyberte malú, reprezentatívnu vzorku

Pre pilot navrhujeme štyri typy verejných stránok: úvodnú stránku, dôležitú službu alebo kategóriu, detail produktu alebo článok a stránku s hlavným kontaktným krokom. Pri konkrétnom webe ich upravte podľa skutočnej návštevnosti a obchodného účelu.

Košík, účet a ďalšie personalizované scenáre testujte oddelene ako funkčné kontroly. **Úspešný bypass citlivej stránky je žiaduci výsledok, nie chyba len preto, že nejde o HIT.** Nevyprázdňujte celý produkčný cache kvôli experimentu bez samostatného prevádzkového plánu.

## 3. Zaznamenajte podmienky, nie iba screenshot skóre

Pred zmenou aj po nej použite rovnaké URL, zariadenie, nastavenie testu a návštevnícky stav. Zaznamenajte verziu nasadeného pluginu, dátum, zmenenú vrstvu a ďalšie súbežné zásahy. Ak sa medzi testami zmenil hosting alebo hero obrázok, výsledok nemožno čestne pripísať iba cache pluginu.

Pre každú URL si založte tento záznam:

- **URL a účel:** čo má návštevník na stránke urobiť.
- **Stav relácie:** anonymná alebo prihlásená; relevantný súhlas a cookies, bez zverejnenia ich hodnôt.
- **Cache stav:** potvrdený HIT, MISS alebo bypass; ak zdroj stav neukazuje, napíšte UNKNOWN.
- **Meranie:** nástroj, jeho nastavenie, zariadenie, dátum a opakované výsledky pred/po.
- **Funkčnosť:** navigácia, formulár alebo iný relevantný krok; PASS, FAIL alebo netestované.
- **Rozhodnutie:** ponechať zmenu, opraviť konkrétnu vrstvu alebo vrátiť preimage.

Ako praktický minimálny pilot odporúčame aspoň tri porovnateľné laboratórne behy pred zmenou a tri po nej. Uložte všetky výsledky, medián aj rozsah, nie iba najlepší beh. Tri behy nie sú štatistická garancia a nie sú náhradou návštevníckych dát.

## 4. Nezamieňajte Lighthouse za skúsenosť všetkých návštevníkov

Laboratórny test je užitočný na diagnostiku a porovnávanie v kontrolovaných podmienkach. Reálne Core Web Vitals opisujú skúsenosť návštevníkov: načítanie cez LCP, odozvu cez INP a stabilitu cez CLS. Samotné načítanie stránky v Lighthouse nemeria reálne návštevnícke INP. Laboratórne TBT nie je to isté ako INP.

Ak pre URL nie sú dostupné dostatočné návštevnícke dáta, uveďte to. Jednorazové vysoké skóre nie je dôkaz splnených produkčných Core Web Vitals ani rastu predaja.

Zdroje: [Google — Web Vitals](https://web.dev/articles/vitals) a [Chrome — Lighthouse performance scoring](https://developer.chrome.com/docs/lighthouse/performance/performance-scoring).

## 5. Ukončite pilot rozhodnutím, ktoré klient pochopí

Rozlišujte tri výsledky:

- **Technicky lepšie a funkčne overené:** porovnateľné meranie ukazuje prínos a dohodnuté kritické scenáre fungujú. Sledujte ďalšiu prevádzku.
- **Bez preukázaného prínosu:** dáta sú nejednoznačné alebo rozdiel menší než kolísanie. Nesľubujte zlepšenie; identifikujte ďalší konkrétny problém.
- **Funkčná regresia:** zmena poškodila dôležitý scenár. Vráťte presnú zmenenú vrstvu a problém reprodukujte mimo produkcie. Lepšie skóre neospravedlňuje poškodený formulár alebo checkout.

Odovzdanie má obsahovať konfiguráciu, výnimky, výsledky, limity merania a postup návratu. Verejne zdieľajte iba anonymizované podklady; cookies, prístupy, súkromné downloady a zákaznícke údaje do verejného repozitára nepatria.

## Kde do tohto procesu patrí CPC

Custom Performance Cache spája page cache, warmup, obrazové workflow a prehľad Mission Control. Vhodnosť a konfigurácia závisia od konkrétneho hostingu, témy a pluginov. Tento dokument neoznamuje novú verziu a netvrdí univerzálnu kompatibilitu ani garantované skóre.

Agentúra môže začať jedným klientskym webom a vopred dohodnutým pilotom. [Produktová stránka a informácie pre agentúry](https://cottoncloud.sk/pluginy/custom-performance-cache/#pre-agentury) vysvetľujú CPC a obsahujú cestu na overenie vhodnosti pre konkrétny web. Na samotné nasadenie nadväzuje [agentúrny rollout checklist](./AGENCY-ROLLOUT-CHECKLIST.md).

**Hranica výsledku:** zverejnený návod, rýchlejšia odpoveď či cache HIT samy osebe nedokazujú vyššie pozície v Google, odporúčanie AI ani nové objednávky. Tie treba merať samostatne.
