# NODIUM NSPanel EU — DEV

Experimentální instalační obrazy a manifesty pro odděleně aktualizovaný ESP32 a Nextion. Zdrojový kód, HMI projekt, ladicí symboly ani nastavení domácí instalace se zde nezveřejňují.

První sada se připravuje. Instalujte až po zveřejnění odpovídajícího manifest.json a bundle.json. Tento kanál není STABLE. Kompilace a kontrola souborů nenahrazují ověření na fyzickém panelu.

Trvalé adresy po zveřejnění sady:

- Firmware DEV manifest: https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/manifest.json
- TFT alias: https://raw.githubusercontent.com/lukasveselycz/nodium-updates/main/nspanel-eu/dev/display.tft
- Verze a SHA-256 obou obrazů: bundle.json

V NODIUM Setup nastavte 09.02 DEV manifest URL, zvolte 09.03 DEV, stiskněte 09.04 Zjistit novou verzi a potom 09.05 Aktualizovat firmware. Pro přímé HTTPS nahrání TFT je potřeba dev.43 nebo novější z odpovídající experimentální větve. Teprve po jeho restartu nastavte 06.46 DEV HMI TFT URL a jednou stiskněte DEV NAHRÁT HMI TFT AUTO.

Pokud původní TFT startuje na 9600, první přenos může trvat přibližně deset minut. Nechte panel napájený a vyčkejte na dokončení. Opravené HOME TFT startuje na 115200, API 2 / feature 512 / build 41001. Aktivní jsou hlavní scény po jejich přiřazení a připojení Core; spodní navigace v tomto HOME experimentu zatím není zapojená.

Neměnné soubory obsahují verzi/build a část SHA-256 v názvu. Staré obrazy se zachovávají; nový manifest a TFT alias se zveřejňují společně. Aktualizace obou procesorů stále vyžaduje dva výslovné kroky.
