# NODIUM NSPanel EU — DEV

**ESP 0.2.0-dev.48-setup-ui-experiment; HOME visual02 přijatá vlastníkem 31. 10. 2026.**
Nový ESP přináší přehledný lokální Setup a zahrnuje zpětnou vazbu HOME z dev.47.
Přijatý TFT se nemění a při této aktualizaci ESP se znovu nenahrává.

## Aktualizace z funkční dev.46

1. V **09.02 · DEV manifest URL** ponech:
   ```text
   https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/manifest.json
   ```
2. V **09.03 · Kanál aktualizací NODIUM** zvol **DEV**.
3. Stiskni **09.04 · Zjistit novou verzi** a ověř nabídnutou **dev.48**.
4. Stiskni **09.05 · Aktualizovat firmware**. Zachovej napájení a počkej na restart.
5. Znovu otevři web panelu. Při starém vzhledu znovu načti stránku.

Konfigurace zůstává ve formátu v7 a tabulka flash oddílů se nemění.
Uchování skutečného nastavení po této OTA je součástí cílené přejímky na panelu.

## Nový Setup

- **Místnost:** identita panelu a místnosti; názvy, entity a testy světel pohromadě.
- **Scény:** DEN / VEČER / TV / NOC; název, akční scéna, volitelný stavový
  binary_sensor a test. Odeslaný povel se nevydává za ověřený stav.
- **Ovládání a displej:** dlouhý stisk, stmívání, zvuk, jasy, ztlumení a korekce teploty.
- **Servis:** přehled skutečných stavů. **Všechna nastavení** otevře původní úplné UI.

Klient používá původní autentizaci a jediné sdílené SSE spojení.
Hlavní mapování a světla 3–4 mají své původní samostatné aktivace.
Nastavení není závislé na externích fontech nebo vzdáleném frontendu.
Dev.47 přidává podklady pro skutečné ověřování aktivní scény; odpovídající
stavové binary_sensor entity je potřeba nastavit v Home Assistantu a Setupu.

## Ověření a přejímka

**ESP: Software-validated, vlastník povolil DEV testovací distribuci.**
Prošlo 12 cílených kontraktů klienta, ověření 54 vazeb proti SDK,
validace konfigurace, společný ESP32 build a kontrola integrity výsledného OTA.
ESPHome 2026.7.4 / ESP-IDF 5.5.5.
OTA 1458688 B; rezerva app oddílu 376320 B.
Statická RAM 139856 B (+64 B proti dev.47); provozní volná RAM není změřená.
Skutečný browser, přihlášení, ukládání, aktivace, reconnect a zachování konfigurace
po nové OTA čekají na ověření na panelu. Nejde o STABLE release.

**HOME visual02: fyzická přejímka vzhledu potvrzená vlastníkem.**
Odstraněné okraje a pravá hrana odpovídají představě i rámečku konkrétního panelu.
Nativní raster zůstává 480 × 320; obsah HOME 450 × 320.
Tato přejímka není univerzální měření bezpečné oblasti jiných panelů.

Přijatý TFT má SHA256
`c65f1d9d9ca6866d97723d99811c5c5f63a8f983f2b768f385d2048b31f07ba3`.
Stávající `display.tft` i neměnný `home-41001-uart115200-c65f1d9d9ca6.tft`
zůstávají byte-identické. Starší neměnné ESP/TFT soubory jsou zachované.
Zdroje, HMI, domácí konfigurace a diagnostické soubory zůstávají soukromé.
