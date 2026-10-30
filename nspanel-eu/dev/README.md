# NODIUM NSPanel EU — DEV

Aktuální sada: **0.2.0-dev.44-home-url-recovery-experiment**.

Tato oprava obnoví použitelnou adresu TFT i tehdy, když se do pole 06.46
zkopíroval celý Markdown odkaz nebo známý NODIUM DEV manifest místo TFT.
Při startu a před AUTO opraví a uloží čistou URL. V Setupu ukazuje použitý
zdroj a při selhání zachová konkrétní chybu HTTP nebo potvrzení displeje.
Jiné platné HTTP(S) TFT zdroje zachovává. Oprava URL sama nespouští upload.

## Instalace ze stávajícího DEV kanálu

1. V NODIUM Setup zvolte **09.04 · Zjistit novou verzi**.
2. Po nabídnutí dev.44 stiskněte **09.05 · Aktualizovat firmware** a vyčkejte na restart.
3. Po restartu je 06.46 opravená bez dalšího kopírování. Řádek **DEV · HMI TFT použitá adresa** ukáže zdroj.
4. Jednou stiskněte **DEV · NAHRÁT HMI TFT · AUTO**.

ESP32 a Nextion jsou dva samostatné aktualizační kroky. Je-li původní TFT
na 9600 baud, skutečný přenos může trvat přibližně deset minut.
Správný TFT má **581380 bajtů**. Konkrétní chybu lze přečíst přímo ve stavu
uploadu. Zobrazení průběhu v prohlížeči při blokujícím sériovém přenosu
není zaručené; procenta na displeji/logy doplňují fyzické ověření.

## Adresy pro případ ruční konfigurace

Do 09.02 patří čistá adresa manifestu:

```text
https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/manifest.json
```

Do 06.46 patří čistá adresa TFT:

```text
https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/display.tft
```

Soubor `bundle.json` uvádí přesné verze, délky a SHA-256. Nový firmware
používá stejný HOME TFT API2 / feature512 / build41001, UART115200 a směr270°.
Hlavní scény vyžadují přiřazení a Core. Spodní navigace v tomto HOME
experimentu zůstává nezapojená.

**Experimentální DEV distribuce na žádost vlastníka; žádný STABLE release.**
Kompilace a ověření souborů nejsou důkazem úspěšného nového TFT přenosu nebo
ovládání na fyzickém panelu. Soukromé zdroje, HMI projekt, debug symboly ani
nastavení domácí instalace se zde nezveřejňují. Starší obrazy se zachovávají.
