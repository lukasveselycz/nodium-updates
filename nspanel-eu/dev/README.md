# NODIUM NSPanel EU — DEV

**HOME vzhledová revize 01, 31. 10. 2026.** Nové fonty s českou diakritikou,
rovnoměrné mezery mezi kartami a stejné odsazení karet od vnitřního rámečku.
Navigace a malé údaje14 px, scény16 px, místnost20 px, čas/teplota40 px.

ESP zůstává **0.2.0-dev.46-home-frame-recovery-experiment**. Tento vzhledový
update mění jen TFT. Původní ESP obraz i manifest jsou byte-identické;
09.04/09.05 proto kvůli novému vzhledu nenabídnou vyšší ESP verzi.

## Instalace na panel s funkční dev.46

1. V sekci06 ponech v **06.46 · DEV · HMI TFT URL** tuto čistou adresu:

   ```text
   https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/display.tft
   ```

2. Jednou stiskni **DEV · NAHRÁT HMI TFT · AUTO**. Během přenosu zachovej
   napájení a počkej na dokončení a restart.
3. ESP dev.46 i aktivní mapování scén zůstávají; po restartu se načtou znovu.

Přijetí příkazu stále krátce zvýrazní scénu. Trvalé označení skutečně aktivní
scény není v této revizi doplněné. Ostatní obrazovky jsou nadále mimo HOME
milník. Stávající pravá návrhová bezpečnostní rezerva zůstává; přesná poslední
viditelná LCD souřadnice zatím není fyzicky změřená.

## První použití scén v Home Assistantu

U konkrétního zařízení v Nastavení → Zařízení a služby → ESPHome →
Konfigurovat povol **Allow the device to perform Home Assistant actions**.
Do mapování scén patří ID existujících HA scén; změny aktivuje původní
ULOŽIT A AKTIVOVAT MAPOVÁNÍ / RESTART. Samotné zobrazení senzorů nebo
event entity toto oprávnění nedokládá.

## Stav ověření

Předchozí HOME byl vlastníkem funkčně přijat. Nový vzhled prošel nativním
save/close/reopen a kompilací0 errors/0 warnings v Nextion Editoru1.68.2,
čtením všech38 komponent/28 vazeb,54 příkazy UTF-8 v simulátoru, další
změnou času a press/release obou krajních scén. Všechny obrazové payloady,
Program.s/UART115200, směr270°, API2/build41001/feature512 a scene IDs29–32
zůstávají. Nové fonty/rozložení čekají na fyzické posouzení. Jde o DEV test,
nikoli STABLE release; HMI zdroj, debug soubory a domácí konfigurace zůstávají
soukromé. Starší neměnné TFT a ESP soubory jsou zachované.
