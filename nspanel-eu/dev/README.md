# NODIUM NSPanel EU — DEV

**HOME vzhledová revize 02, 31. 10. 2026.** Odstraněné vnitřní okraje
a rámeček, větší karty scén a navigace, rovnoměrně zvětšené ikony.
Pracovní oblast kandidáta je 450 × 320 px; celý nativní raster zůstává
480 × 320 px. Pravý okraj x449 je pokus pro tento kus, nikoli změřená
viditelná hranice. Podsvícení aktivní navigace dosahuje na řádky 318–319.
Scény mají 98 × 117 px a popisky 20 px, navigace 90 × 64 px a popisky 16 px.

ESP zůstává **0.2.0-dev.46-home-frame-recovery-experiment**.
Tato aktualizace mění pouze TFT. ESP obraz i manifest zůstávají byte-identické;
09.04/09.05 proto kvůli nové grafice nenabídnou vyšší ESP verzi.
Rozpracované ESP dev.47/dev.48 nejsou součástí tohoto zveřejnění.

## Instalace na panel s funkční dev.46

1. V sekci 06 ponech v **06.46 · DEV · HMI TFT URL** tuto adresu:

   ```text
   https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/display.tft
   ```

2. Jednou stiskni **DEV · NAHRÁT HMI TFT · AUTO**. Zachovej napájení
   a počkej na dokončení přenosu a restart.
3. Po restartu zkontroluj okraje HOME, spodní lištu a dotyk všech čtyř scén.
   ESP dev.46 a uložené mapování scén zůstávají zachované.

Nový neměnný TFT: `home-41001-uart115200-c65f1d9d9ca6.tft`,
712 440 B, SHA-256:
`c65f1d9d9ca6866d97723d99811c5c5f63a8f983f2b768f385d2048b31f07ba3`.
Původní revize 01 zůstává dostupná jako
`home-41001-uart115200-d3aaf1b834dd.tft`.

Přijetí příkazu stále krátce zvýrazní scénu. Trvalé označení skutečně aktivní
scény tato vzhledová revize nepřidává. Ostatní obrazovky zůstávají mimo HOME milník.

## První použití scén v Home Assistantu

U konkrétního zařízení v Nastavení → Zařízení a služby → ESPHome →
Konfigurovat povol **Allow the device to perform Home Assistant actions**.
Do mapování scén patří ID existujících HA scén; změny aktivuje původní
ULOŽIT A AKTIVOVAT MAPOVÁNÍ / RESTART.

## Stav ověření

**Software-validated; DEV kandidát pro vlastní panel.** Nativní
Save/Close/Reopen a kompilace v Nextion Editoru skončily 0 errors / 0 warnings.
Záznam ověření dokládá 38 ID, 28 vazeb, 54 potvrzených renderovacích příkazů
a press/release všech čtyř scén (ID 29–32). Nextion RAM zůstává 924 B.
HMI API2/build41001/feature512, UART115200 a směr270° zůstávají zachované.

Nové fyzické okraje a dotyk zatím nejsou ověřené na panelu; fyzická přejímka
zůstává otevřená. Nejde o STABLE release. HMI zdroj, domácí konfigurace a
debug soubory zůstávají soukromé. Starší neměnné TFT i ESP soubory jsou zachované.
