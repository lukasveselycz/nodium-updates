# NODIUM NSPanel EU — DEV

Aktuální sada: **0.2.0-dev.46-home-frame-recovery-experiment**.
Opravuje překrytí HOME celoplošným pozadím po startu a obnovu nedokončeného
prvního vykreslení. Renderer zachová nativní grafiku a do potvrzení prvního
rámce nepovažuje samotné zařazení příkazů do fronty za hotový obraz.
Při chybějícím potvrzení provede nejvýše tři úplné pokusy; další obnovu lze
vyžádat existujícím tlačítkem **06.47 · UI · synchronizovat texty do displeje**.
Ovládání nadále vyžaduje potvrzený rámec, Core a přiřazené scény.

## Instalace při již dokončeném TFT uploadu z dev.45

1. V NODIUM Setup zvolte **09.04 · Zjistit novou verzi**.
2. Nainstalujte **dev.46 přes 09.05 · Aktualizovat firmware** a počkejte na restart.
3. Obnovte webovou stránku a ověřte, že HOME zůstane zobrazené i při změně času.

**TFT už znovu nenahrávejte; AUTO kvůli této opravě nespouštějte.**
Adresy, obrázky, fonty a HMI projekt se nemění. Původní oprava TFT uploaderu
a uložený poslední pokus z dev.45 zůstávají. Běžný provoz používá nižší
diagnostickou podrobnost, aby každý ACK nevypisoval celou frontu.

## Adresy pro případ ruční konfigurace

Do 09.02 patří čistá adresa manifestu:

```text
https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/manifest.json
```

Do 06.46 patří čistá adresa TFT:

```text
https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/display.tft
```

`bundle.json` uvádí přesné verze, délky a SHA-256. Stejný HOME TFT má
581380 B, API2 / feature512 / build41001, UART115200 a směr270°.
Pro zařízení, kde tento TFT dosud nahraný není, zůstává samostatný ruční
AUTO krok. Přenos na9600 baud trvá přibližně deset minut. Spodní navigace
zůstává v tomto HOME experimentu nezapojená.

**Experimentální DEV distribuce na žádost vlastníka; žádný STABLE release.**
Vlastník již doložil dokončení stejného TFT a úplnou grafiku při zapnutí,
po níž nastalo překrytí. Oprava prošla hostovým kontraktem, konfigurací
a skutečným replayem v nativním Nextion simulátoru. Sestavení a integrita
obrazu neznamenají fyzické ověření dev.46, zachování grafiky ani dotyků/scén.
Zdroj, HMI, debug symboly a domácí konfigurace zůstávají soukromé.
Starší ESP obrazy se zachovávají.
