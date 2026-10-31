# NODIUM NSPanel EU — DEV

Aktuální sada: **0.2.0-dev.45-home-bounded-upload-experiment**.
Opravuje čekání uploaderu při nepřetržitém UART příjmu, omezuje logování
rušivých bajtů a po dobu blokujících HTTP operací používá dočasný konečný
watchdog limit. Původní limit se po upload funkci obnoví; HTTPS ověřování
zůstává zapnuté. Oprava URL z dev.44 zůstává součástí.

Nové **DEV · HMI poslední pokus** uchovává fázi/výsledek přes restart i
vypnutí napájení. `BEZ VÝSLEDKU` znamená, že chybí uložené dokončení;
samotný text neurčuje příčinu přerušení a neprovádí automatický opakovaný pokus.
Procenta se do flash průběžně nezapisují.

## Instalace ze stávajícího DEV kanálu

1. Po zapnutí panelu v NODIUM Setup zvolte **09.04 · Zjistit novou verzi**.
2. Po nabídnutí dev.45 stiskněte **09.05 · Aktualizovat firmware** a vyčkejte na restart.
3. Obnovte stránku. V části displeje bude nový řádek **DEV · HMI poslední pokus**.
4. Jednou stiskněte **DEV · NAHRÁT HMI TFT · AUTO**.

Adresy zůstávají stejné, soubor není potřeba přejmenovávat. ESP32 firmware
a Nextion TFT jsou dva samostatné aktualizační kroky. Je-li původní TFT na
9600 baud, skutečný přenos může trvat přibližně deset minut. Začátek přenosu
potvrzuje ACK displeje; samotná žádost o nahrávání ještě není běžící upload.
Po chybě nebo restartu lze přečíst uchovaný poslední pokus. Během blokujícího
přenosu není zaručen průběžný refresh webu; nativní procenta displeje/logy
doplňují fyzickou kontrolu.

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
Hlavní scény vyžadují přiřazení a Core. Spodní navigace zůstává v tomto
HOME experimentu nezapojená.

**Experimentální DEV distribuce na žádost vlastníka; žádný STABLE release.**
Zdrojová chyba čekání byla reprodukována v hostové simulaci; příčina
předchozího fyzického pokusu zůstává nepotvrzená. Kompilace a integrita
souborů nejsou fyzickou přejímkou TFT nebo ovládání. Soukromé zdroje, HMI,
debug symboly a nastavení domácí instalace se zde nezveřejňují. Starší obrazy
se zachovávají.
