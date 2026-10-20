# Památky Prahy 2 — hotový web pro GitHub Pages

## Co je připraveno

- 139 hlavních záznamů s původním označením: 6 národních kulturních památek, 93 nemovitých kulturních památek / Nové Město, 29 / Vinohrady a 11 / Vyšehrad.
- 241 fotografických karet včetně částí souborů, mapové výřezy a texty z dodaného katalogu.
- Původní číselník se žlutým, modrým a šrafovaným označením; filtrování podle tohoto označení.
- Vyhledávání bez ohledu na diakritiku, řazení, samostatné odkazy na detail, zobrazení úplných původních stran.
- Kvíz s výběrem skupiny, počtu otázek, hlavních objektů nebo i částí souborů. Vyhodnocení a procvičení chyb. Nejlepší procentní výsledek se ukládá pouze v daném prohlížeči.
- Rozvržení pro počítače i mobily, klávesnicové ovládání a tisk detailu.

Barevnost (#fcbd00, #dc3332, #191919) a písmo Figtree vycházejí z praha2.cz. Projekt je samostatná statická stránka. Nepřebírá navigaci ani redakční systém městského webu.

## Vyzkoušení před zveřejněním

1. ZIP nejprve celý rozbalte.
2. Ve složce `praha2-pamatky` otevřete soubor `index.html` v Chrome, Edge nebo Firefoxu.
3. Vyzkoušejte vyhledání objektu, otevření detailu a kvíz.

Web nepotřebuje instalovat žádné balíčky, spouštět server ani zadávat API klíč. Fotografie, mapky i písmo jsou součástí balíčku. Odkaz na web městské části samozřejmě vyžaduje internet.

## Zveřejnění — doporučený postup pomocí GitHub Desktop

Protože web obsahuje stovky obrazových souborů, nejpohodlnější je vložit je přes GitHub Desktop. ZIP se na GitHub nenahrává jako jeden soubor: GitHub Pages potřebuje rozbalený obsah.

### Nový samostatný web

1. Přihlaste se na https://github.com a vytvořte nový repozitář tlačítkem **New repository**. Název může být `pamatky-praha2`. Zvolte **Public** a vytvoření README. Klikněte na **Create repository**.
2. Nainstalujte GitHub Desktop z https://desktop.github.com/ a přihlaste se stejným účtem.
3. V GitHub Desktop zvolte **File → Clone repository**, vyberte nový repozitář a uložte jej do počítače.
4. Přes **Repository → Show in Explorer** otevřete jeho složku.
5. Do této složky zkopírujte celý OBSAH rozbalené složky `praha2-pamatky`. Soubor `index.html` musí být přímo v kořeni repozitáře, vedle složek `assets` a `stranky`.
6. V GitHub Desktop uvidíte seznam změn. Do **Summary** napište například `Přidání katalogu památek Prahy 2`. Klikněte na **Commit to main**, potom **Push origin**.
7. Na webu GitHub otevřete repozitář a zvolte **Settings → Pages**.
8. V části **Build and deployment** nastavte **Source: Deploy from a branch**.
9. Vyberte větev **main**, složku **/ (root)** a klikněte na **Save**.
10. Po dokončení publikace se v této části zobrazí skutečný odkaz na web. Obvyklý tvar je `https://UZIVATEL.github.io/pamatky-praha2/` — slovo UZIVATEL nahraďte názvem svého účtu.

### Přidání do existujícího webu s poznávačkami

1. V GitHub Desktop naklonujte stávající repozitář. Pokud už ho máte v počítači, nejprve použijte **Fetch origin / Pull origin**.
2. V jeho složce vytvořte podadresář `pamatky`.
3. Do podadresáře vložte celý obsah rozbalené složky `praha2-pamatky`. Původní úvodní `index.html` existujícího webu ponechte.
4. Proveďte **Commit to main → Push origin**. Nastavení GitHub Pages již nemusíte měnit, pokud web funguje z této větve.
5. Nová stránka bude na původní adrese webu doplněné o `/pamatky/`.
6. Z úvodní stránky na ni můžete odkázat běžným HTML odkazem: `<a href="pamatky/">Památky Prahy 2</a>`.

Pokud máte publikaci nastavenou ze složky `/docs`, vložte nový podadresář do `docs/pamatky`.

Oficiální postup GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Drobné úpravy a aktualizace

- `index.html`: struktura stránky a úvodní texty.
- `style.css`: vzhled, barvy, velikosti a mobilní rozvržení.
- `app.js`: katalog, filtrování, detail a kvíz.
- `data.js`: obsah všech hlavních záznamů a částí souborů. Jde o JavaScript s daty ve formátu JSON za výrazem `window.CATALOG =`.
- `assets/`: fotografie, mapové výřezy a soubor písma.
- `stranky/`: reprodukce všech 214 stran původního katalogu.
- `index-data.json`: pomocný datový přepis úvodního číselníku. Web samotný načítá `data.js`.
- `.nojekyll`: pomocný soubor pro přímé hostování statického webu.

Při dalších úpravách zachovejte všechny složky a názvy souborů včetně velikosti písmen. Po změně vždy opět proveďte commit a push.

## Zdroj a ověření

Obsah vychází z dodaného PDF „Katalog NKP Praha 2 (1).pdf“, vydání 2025. Katalog zahrnuje také nemovité kulturní památky, proto je tento rozdíl zachován i v názvech skupin. Části souborů nemají přidělená nová čísla číselníku. Údaje nejsou průběžně aktualizovaným registrem.

Fotografie, mapky, popisy a označení jejich zdrojů zůstávají zachovány také na původních katalogových stranách. Mapy jsou statické mapové výřezy, nikoli interaktivní geodatová vrstva. Místy obsahuje zdrojový katalog překlepy či rozdíly mezi souhrnným přehledem a detailní kartou; obě původní podoby jsou přístupné.

Byla ověřena úplnost číselníku, existence obrazových souborů, syntaxe JavaScriptu a logika vyhledávání, filtrů, otevírání detailů, kvízu a výsledků v testovacím prostředí. Vizuální kontrola přímo v prohlížeči v tomto prostředí nebyla dostupná. Před veřejným spuštěním doporučujeme stránku otevřít podle postupu výše a prohlédnout ji na počítači i telefonu.
