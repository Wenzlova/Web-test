# Plán dalšího rozvoje webu

Aktualizováno: 11. 7. 2026

## Kontext projektu

- Produkční web: `https://wenzlovakristyna.cz/`
- Produkční repozitář: `Wenzlova/Web-test`, větev `main`
- Vývojová větev: `codex/redesign-v2`
- Náhledový repozitář: `Wenzlova/web_preview`, větev `main`
- Náhledová adresa: `https://wenzlova.github.io/web_preview/`

## Aktuální stav a provedený audit

- Stránka je statická, bez frameworku a bez procesu sestavení.
- Desktop ani mobil nemají horizontální přetékání.
- Mobilní menu se otevírá, správně aktualizuje `aria-expanded` a po volbě odkazu se zavře.
- Galerie se otevírá v nativním dialogu, přebírá správný obrázek a alternativní text a lze ji zavřít.
- V konzoli nejsou při základním průchodu chyby ani varování.
- Kontaktní e-mail používá funkční `mailto:` odkaz a Instagram se otevírá v nové kartě bezpečným způsobem.
- Nadpisy používají správnou hierarchii `h1` → `h2` → `h3`.
- Číslování bylo rozděleno na úroveň sekcí (`Sekce 01 / 03`) a projektů (`Projekt 01 / 02`).
- Typografie používá jednu sdílenou stupnici místo samostatných velikostí pro každou sekci.
- Alternativní text úvodního obrázku byl opraven tak, aby jej správně popisoval jako půdorys.

## P0 — před zveřejněním na hlavní doméně

### Obsah a důvěryhodnost

- [ ] Ověřit, zda je portrét `images/pic01.jpg` finální a zda je možné jej veřejně použít.
- [ ] Doplnit místo působnosti (město / region / celá ČR).
- [ ] Doplnit IČO a případně telefon, pokud mají být veřejné.
- [ ] U každého projektu doplnit rok, lokalitu, rozsah práce, stav projektu a autorství fotografií.
- [ ] Ověřit názvy a popisy projektů s autorkou.
- [ ] Doplnit jasný rozsah služeb a průběh spolupráce.
- [ ] Přidat konkrétní výzvu k úvodní konzultaci.

### Technická kontrola

- [ ] Otestovat finální web v Safari, Chrome a Firefoxu.
- [ ] Otestovat na skutečném telefonu, nejen v simulovaném viewportu.
- [ ] Ověřit všechny odkazy a e-mail po nasazení.
- [ ] Zkontrolovat kontrast a navigaci pouze klávesnicí.
- [ ] Změřit Core Web Vitals a Lighthouse po optimalizaci obrázků.
- [ ] Před přesunem na produkci odstranit případné `noindex` nastavení náhledu.

## P1 — SEO

- [ ] Doplnit kanonickou adresu `https://wenzlovakristyna.cz/`.
- [ ] Doplnit Open Graph a Twitter Card metadata pro sdílení.
- [ ] Připravit samostatný obrázek pro sdílení alespoň 1200 × 630 px.
- [ ] Přidat favicon a ikonu pro Apple zařízení.
- [ ] Přidat `robots.txt` a jednoduchý `sitemap.xml`.
- [ ] Registrovat produkční web v Google Search Console a Bing Webmaster Tools.
- [ ] Přidat JSON-LD. Preferovaný typ bude vybrán podle skutečných údajů:
  - `Person` pro osobní portfolio,
  - `ProfessionalService` nebo vhodný podtyp `LocalBusiness`, pokud existuje veřejné sídlo a místní služby.
- [ ] Přidat do strukturovaných dat pouze ověřitelné údaje: jméno, URL, e-mail, oblast působnosti, Instagram, případně IČO, telefon a adresa.
- [ ] Zvážit samostatné URL pro jednotlivé projekty. Jedna dlouhá stránka omezuje možnost cílit vyhledávání na konkrétní realizace.
- [ ] Rozšířit texty o přirozené a konkrétní formulace, například „návrh interiéru bytu“, „interiérový design komerčních prostor“ a lokalitu. Nepřidávat mechanické seznamy klíčových slov.

## P1 — dohledatelnost v AI a LLM systémech

- [ ] Zachovat důležité informace jako viditelný text v HTML, ne pouze v obrázcích.
- [ ] Používat konkrétní názvy, lokality, typy prostorů, roky a rozsah práce.
- [ ] Zajistit, aby `robots.txt` neblokoval `OAI-SearchBot` ani běžné vyhledávací roboty.
- [ ] Udržovat konzistentní identitu mezi webem, Instagramem, případným Google Business Profile a dalšími veřejnými profily.
- [ ] Vytvářet samostatné, odkazovatelné stránky projektů s jasným názvem a stručným souhrnem.
- [ ] Přidat strukturovaná data JSON-LD; pomáhají strojům rozlišit osobu, službu a projekt.
- [ ] Volitelně přidat `/llms.txt` až po dokončení obsahu. Jde zatím o komunitní návrh, nikoli zavedený standard ani záruku citování.
- [ ] Neprodukovat skryté „AI texty“, duplicitní stránky ani obsah napsaný pouze pro roboty.

## P1 — anonymní statistika návštěvnosti

### Doporučená varianta: Plausible Analytics

- Bez cookies a persistentních identifikátorů.
- Agregovaná statistika návštěv, zdrojů, zařízení, zemí a nejnavštěvovanějších stránek.
- Data hostovaná v EU a dostupná smlouva o zpracování dat.
- Placená služba, ale administrativně nejčistší varianta pro malý profesionální web v EU.

Postup:

- [ ] Založit účet a přidat doménu `wenzlovakristyna.cz`.
- [ ] Vložit jediný měřicí skript do produkční verze.
- [ ] Přidat krátké informace o anonymní analytice do zásad ochrany soukromí.
- [ ] Měřit pouze zobrazení stránek a maximálně několik užitečných událostí, například kliknutí na e-mail a Instagram.
- [ ] Neodesílat do názvů událostí osobní údaje ani obsah formulářů.
- [ ] Po nasazení ověřit, že služba nevytváří cookies ani lokální úložiště.

### Bezplatná alternativa: Cloudflare Web Analytics

- Bezplatná a podle dokumentace Cloudflare bez sběru či použití osobních dat návštěvníků.
- Lze vložit do GitHub Pages pomocí JavaScriptového beaconu bez přesunu DNS ke Cloudflare.
- Před nasazením ověřit aktuální podmínky, zpracovatele, umístění dat a požadavky českého/EU práva.

Poznámka: absence cookies sama o sobě automaticky neřeší všechny informační povinnosti. I při anonymní analytice je vhodná krátká a srozumitelná stránka o soukromí. Toto není právní posouzení.

## P1 — výkon a obrázky

- [ ] Převést fotografie do moderního formátu WebP nebo AVIF.
- [ ] Připravit více velikostí a používat `srcset` a `sizes`.
- [ ] Úvodní obrázek ponechat prioritní; fotografie níže načítat líně.
- [ ] Zmenšit extrémně velké originály, zejména soubory v rozlišení 3840–7680 px.
- [ ] Odstranit metadata EXIF z veřejných optimalizovaných kopií.
- [ ] Nastavit rozumnou kompresi a vizuálně porovnat kvalitu.
- [ ] Nepřepisovat archivní originály; optimalizované verze držet samostatně.

## P2 — další profesionální prvky

- [ ] Přidat sekci „Jak probíhá spolupráce“ ve 3–5 krocích.
- [ ] Přidat stručný přehled služeb.
- [ ] Zvážit reference klientů pouze s výslovným souhlasem.
- [ ] Přidat vlastní stránku 404.
- [ ] Přidat základní bezpečnostní hlavičky, pokud to zvolený hosting umožní.
- [ ] Nastavit ochranu větve `main` a před nasazením používat pull request.
- [ ] Přidat automatickou kontrolu odkazů a HTML v GitHub Actions.

## Potřebné podklady od majitelky webu

- Finální profesní označení.
- Město a oblast působnosti.
- IČO, případně telefon a veřejná adresa.
- Rozsah nabízených služeb.
- Průběh spolupráce.
- Finální profilová fotografie.
- Rok, lokalita, stav a autor fotografií u každého projektu.
- Souhlas s publikací fotografií a názvů klientů.
- Preferovaná služba analytiky a e-mail vlastníka účtu.

## Doporučený začátek příští práce

1. Získat chybějící obsahové podklady.
2. Dokončit sekce služby a průběh spolupráce.
3. Optimalizovat obrázky a změřit výkon.
4. Doplnit produkční SEO metadata, JSON-LD, favicon, `robots.txt` a `sitemap.xml`.
5. Nasadit Plausible nebo Cloudflare Web Analytics.
6. Provést finální kontrolu, sloučit přes pull request a ověřit produkční doménu.

## Referenční dokumentace

- Google Search Central — SEO a strukturovaná data: https://developers.google.com/search/docs
- OpenAI — informace pro vydavatele a OAI-SearchBot: https://help.openai.com/
- Plausible Data Policy: https://plausible.io/data-policy
- Cloudflare Web Analytics: https://developers.cloudflare.com/web-analytics/about/
- Návrh `llms.txt`: https://llmstxt.org/
