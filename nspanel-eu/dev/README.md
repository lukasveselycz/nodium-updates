# NODIUM NSPanel EU — DEV

**1. listopadu 2026: ESP 0.2.0-dev.52-navigation-router-experiment.**
Vlastník schválil přípravu aktualizace přes stávající GitHub DEV kanál.
Stav ESP je Software-validated; fyzická instalace a přejímka této verze čekají.

## Aktualizace ESP přes GitHub

1. Před aktualizací exportuj současnou zálohu nastavení (dev.48 používá v7).
2. V **09.02 · DEV manifest URL** ponech:
   ```text
   https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/manifest.json
   ```
3. V **09.03 · Kanál aktualizací NODIUM** zvol **DEV**.
4. Stiskni **09.04 · Zjistit novou verzi** a ověř nabídnutou **dev.52**.
5. Stiskni **09.05 · Aktualizovat firmware**, zachovej napájení a vyčkej na restart.
6. Znovu otevři web panelu a ověř projektovou verzi. Při starém webu obnov stránku.

Tento krok aktualizuje pouze ESP. Přijatý `display.tft` zůstává build41001
visual02. TFT znovu nenahrávej jen kvůli této aktualizaci ESP. Dev.52 zachovává
původní 41001 cestu i uložené preference; nové zálohy exportuje ve v8 a čte v1–v8.

## Co obsahuje dev.52

- Správa členů čtyř logických světel: přidat/upravit/odebrat jednotlivé HA
  entity, zachování staré HA group, deduplikace a potvrzení všech členů.
- Rozdílné či neznámé stavy členů a ochrana souběhu překrývajících se slotů.
  Jeden slot podporuje nejvýše čtyři členy, celkem osm jedinečných endpointů
  a 255 UTF-8 bajtů na mapovací pole.
- Nové výchozí názvy Scéna 1–4 / Světlo 1–4. Existující vlastní názvy zůstávají.
- Čtyři volby ikon scén a čtyři volby ikon světel ze společného katalogu
  20+14 stabilních významů, včetně trvalého uložení a v8 zálohy/obnovy.
- Společný navigační touch router zachovává 39 přechodů a šest current-tab
  no-opů; proti dev.51 šetří 7 856 B statické DRAM.

## Volitelný test nativních LIGHTS — TFT41003

Samostatný neměnný soubor `home-lights-41003-uart115200-8b06031fe123.tft`
je určen pro navazující fyzický test stejného panelu. Má API2/build41003/
features1537, 480×320, směr270°, UART115200. Výchozí `display.tft` se na něj
automaticky nepřepíná. Pokud už panel hlásí41003, znovu jej nenahrávej.

Nejprve dokonči ESP update a ověř zachovaný HOME. Teprve při samostatném
rozhodnutí testovat LIGHTS zadej do **06.46 · DEV · HMI TFT URL**:
```text
https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/home-lights-41003-uart115200-8b06031fe123.tft
```
Potom jednou použij **DEV · NAHRÁT HMI TFT · AUTO** a vyčkej na úplné dokončení.
Jiná nebo neznámá HMI identita vyžaduje nejprve ověřit kompatibilitu.
Nová 41003 dvojice je Software-validated, fyzická přejímka čeká.

## Známé hranice

Volba univerzální ikony je uložená a zálohovaná, ale 41001 ani41003 ještě
neobsahují novou univerzální Picture banku. Původní ikony jsou očekávané.
BLE proxy ani přímé ESP-NOW ovládání nejsou součástí tohoto obrazu.
Uložená přímá reference žárovky nepředstavuje bezpečné rádiové párování.

## Přejímka

Ověř názvy a mapování po OTA/rebootu, HOME a pravý okraj, spodní navigaci,
tři HA žárovky v jednom slotu, jas a mixed stav, nedostupného člena a ACK2/3,
ochranu souběhu sdílených členů, HOLD/stop, reconnect a v8 export/obnovu.
Statická DRAM je 136 512 B; provozní minimum heapu zůstává k měření.

Přijatá HOME visual02 má SHA-256
`c65f1d9d9ca6866d97723d99811c5c5f63a8f983f2b768f385d2048b31f07ba3`.
Starší neměnné ESP/TFT soubory zůstávají zachované. Zdrojový kód, HMI zdroj,
soukromá konfigurace, klíče a diagnostické logy se na veřejný kanál nepublikují.

