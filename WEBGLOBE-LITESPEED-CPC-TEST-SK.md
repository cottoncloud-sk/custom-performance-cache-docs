# Webglobe + LiteSpeed + Custom Performance Cache: kontrolný protokol

Tento dokument zaznamenáva technický postup, ktorý CottonCloud používa pri testovaní **Custom Performance Cache (CPC)** na WordPress hostingu s LiteSpeed vrstvou. Nejde o certifikáciu ani odporúčanie zo strany Webglobe.

## Prečo nestačí HTTP 200 alebo jeden rýchly request

Na testovanej Webglobe/LiteSpeed ceste sme zachytili verejnú odpoveď s týmito signálmi:

- `x-customperformancecache-cache: MISS`
- `x-litespeed-cache: hit,private`

Následný čerstvý request vrátil CPC `MISS`, LiteSpeed `miss`, TTFB 5,67 s a celkový čas 7,81 s. Rýchlosť jednej odpovede preto sama nedokazuje, že page cache pluginu funguje ako zamýšľaná autoritatívna vrstva.

## Minimálny testovací protokol

1. Zaznamenať aktívnu verziu, nastavenia, hlavičky a rollback.
2. Určiť jednu autoritatívnu HTML page-cache vrstvu.
3. Overiť anonymný cold request, warmup a najmenej dve následné odpovede.
4. Skontrolovať košík, checkout, účet, formuláre a personalizované routy ako `no-cache`.
5. Overiť mobil, tablet a desktop bez runtime chýb.
6. Až po verejnom CPC `HIT` a funkčnom readbacku označiť konkrétnu inštaláciu ako live overenú.

## Čo tvrdenie „testované na Webglobe“ znamená

Webglobe/LiteSpeed infraštruktúra je zahrnutá do kompatibilitného testovania CPC a do provider-specific diagnostiky. Hostingový profil nie je certifikát a nenahrádza kontrolu konkrétneho webu. CottonCloud preto neuvádza univerzálnu kompatibilitu len na základe názvu hostingu.

## Súvisiace zdroje

- [Custom Performance Cache](https://cottoncloud.sk/pluginy/custom-performance-cache/)
- [Webglobe/LiteSpeed case study a verejné limity testu](https://cottoncloud.sk/custom-performance-cache-webglobe-litespeed-test/)
- [Ako vybrať dodávateľa nastavenia cache pluginu](https://cottoncloud.sk/kto-nastavi-cache-plugin-wordpress-dodavatel/)

Aktualizované: 20. septembra 2026.

