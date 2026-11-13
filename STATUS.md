# STATUS — digitális bizalom

Ez a dokumentum a `digitalis-bizalom` projekt aktuális munkaállapotát, a nyitott kérdéseket és a következő szakmai ellenőrzési lépéseket foglalja össze.

Nem helyettesíti a Manifesztót vagy az `Alapok` követelményeit, és nem tekinti lezártnak azokat a kérdéseket, amelyekhez még szakmai falszifikációt vagy gyakorlati próbát kérünk.

## Aktuális munkabázis

A projekt jelenlegi két fő nyilvános szakmai alapja:

- [`digitalis-bizalom/manifesto/manifesto.md`](https://github.com/digitalis-bizalom/manifesto/blob/v1.0/manifesto.md) — **A digitális bizalom 12 pontja — Manifesztó a megbízható digitális államról**, a közzétett **v1.0** változat. A kiadási oldal: [`v1.0`](https://github.com/digitalis-bizalom/manifesto/releases/tag/v1.0).
- [`digitalis-bizalom/alapok/elso-kovetelmenykeszlet.md`](https://github.com/digitalis-bizalom/alapok/blob/main/elso-kovetelmenykeszlet.md) — az `Alapok` első, tíz rekordos, továbbra is felülvizsgálható követelménykészlete.

A Manifesztó v1.0 közzétett szövege rögzített kiadási alap; a későbbi szakmai vita vagy a `main` ág módosítása nem változtatja meg visszamenőleg a v1.0 tartalmát. Az `Alapok` ehhez képest továbbfejleszthető, nem lezárt követelményrendszer.

A két dokumentum egymást ellenőrzi:

```text
Manifesztó
    ->
követelmények
    ->
BIZONYÍTÉK + mérce + teszt + failure condition
    ->
visszateszt a Manifesztóra
    ->
pontosítás
```

A cél nem az, hogy a Manifesztó minden részletet tartalmazzon. A Manifesztó az irányt és a vállalt elveket rögzíti; az `Alapok` feladata, hogy ezekből ellenőrizhető követelmények legyenek, és hogy a részletes operacionalizálás visszafelé is jelezze, ha egy elv túl gyenge, túl erős vagy többféleképpen értelmezhető.

## Hol tartunk?

A Manifesztó v1.0 nyilvánosságra került. A közzététel a Manifesztó adott verziójának állapotát rögzíti, nem tanúsítja az `Alapok` követelményrendszerének teljességét, és nem jelenti az online aláírásgyűjtés élesítését.

A Manifesztó és az első követelménykészlet első belső, kétirányú back-testje korábban megtörtént.

A munka során több olyan pontosítás született, amely nem egyszerű szerkesztési javítás volt, hanem a követelményekre bontásból vált láthatóvá. Ilyen volt többek között:

- az állami működőképesség és a tágabb alkotmányos cél elválasztása;
- a kritikus állítások független ellenőrizhetőségének megerősítése;
- a teljes kilépés és a túlélési út megkülönböztetése kritikus függőségnél;
- a rendkívüli vagy degradált működésből a normál, jogszerű állapotba való visszatérés;
- a technikai jogosultság és a jogszerű közhatalom elválasztása;
- a szakmai kockázatjelzés útja a tényleges döntésig;
- a hosszú távú értelmezhetőség, migrálhatóság, kivezethetőség és archiválhatóság külön kezelése.

Ez fontos eredmény, de nem teljességi bizonyíték. A jelenlegi tíz követelmény szándékosan keresztmetszeti tesztkészlet, nem a teljes követelményrendszer és nem a „tíz legfontosabb” követelmény.

## Mely követelményeket kell még operacionalizálni és vizsgálni?

A Manifesztó v1.0 a következő négy kérdésben **már kifejezett elveket rögzít**. Ezek nem a közzétett szöveg azonosított hiányai. Nyitott viszont, hogyan fordíthatók le ellenőrizhető, falszifikálható `Alapok`-követelményekre, milyen bizonyítékokkal teljesíthetők, és milyen ellenpéldák tárhatják fel a megfogalmazásuk korlátait.

1. **Támadói képességfeltételezés — 3. pont.**  
   A v1.0 már kimondja, hogy nem elég a támadót lassabbnak vagy kevésbé intelligensnek feltételezni, és a kritikus biztonsági feltételezéseket alá kell támasztani. Az `Alapok` feladata ennek ellenőrzési módját tisztázni: mely feltevések nélkülözhetetlenek az adott biztonsági állításhoz, milyen bizonyíték támasztja alá őket, és mi történik, ha nem teljesülnek.

2. **Tartós fenyegetettség és rendkívüli működés — 5. pont.**  
   A v1.0 már megköveteli a rendkívüli állami működés szükségességének, arányosságának és jogalapjának rendszeres felülvizsgálatát, valamint a normál, jogszerű állapotba való visszatérést. Nyitott operacionalizálási kérdés, ki, mikor, milyen bizonyíték alapján ellenőriz, milyen korlátok érvényesülnek, és milyen feltételek mellett történhet újraindítás vagy visszaállás.

3. **Élethelyzet-alapú szolgáltatási nézőpont — 1. pont.**  
   A v1.0 már előírja, hogy az állami szolgáltatások kiindulópontja az ember vagy szervezet élethelyzete legyen, és az ügyintézéshez ne kelljen ismerni az állam szervezeti térképét. Az `Alapok`-ban azt kell vizsgálni, hogyan mérhető a tényleges felhasználói hozzáférhetőség úgy, hogy közben megmaradjon a hatásköri és felelősségi rend rekonstruálhatósága.

4. **A kritikus képesség fölötti tényleges kontroll — 12. pont, összefüggésben a 6. ponttal.**  
   A v1.0 már megköveteli a tényleges kontrollt az alkotmányos hatásköri és felelősségi rend szerint, miközben nem teszi kötelezővé a teljes állami önellátást vagy a hazai tulajdont. Az `Alapok` feladata meghatározni az ellenőrizhető minimális képességeket, döntési és kilépési lehetőségeket, illetve a beszállítói függőség mellett is fennmaradó működési kontrollt.

Egy későbbi Manifesztó-módosítás **nem előfeltétele** e kérdések részletesebb kidolgozásának. Új verzió szükségessége csak akkor merülhet fel külön döntésként, ha a szakmai tesztek valódi szövegszintű hiányt, ellentmondást vagy nem szándékolt normatív következményt mutatnak ki.

## Mit kérünk most a szakmai review-tól?

A következő szakmai review célja nem általános egyetértés vagy támogatás megszerzése. A Manifesztóhoz történő csatlakozás ettől külön folyamat; az online aláírásgyűjtés megnyitása önálló üzemeltetési és adatkezelési feltételektől, valamint külön élesítési döntéstől függ.

Kifejezetten **falszifikációt** kérünk.

A legértékesebb visszajelzés az, amely megmutatja, hogy egy állítás vagy követelmény:

- nem mérhető;
- nem tesztelhető;
- túl erős;
- túl gyenge;
- könnyen kijátszható;
- önigazolással teljesíthető;
- rejtetten konkrét technológiát vagy szervezeti modellt ír elő;
- jogi, szervezeti vagy technikai szempontból hibás feltételezésre épül;
- fontos failure mode-ot vagy szereplőt kihagy;
- vagy olyan következményhez vezet, amelyet a szöveg szerzői feltehetően nem akartak vállalni.

A review-nak nem kell egységes álláspontra jutnia. Az egymással ellentétes szakmai kritikák is hasznosak, ha világossá teszik, hol van valódi választási pont vagy feloldatlan feszültség.

## Mely követelményeket érdemes először kipróbálni?

A következő körben legalább 2–3 tényleges vagy realisztikus dry runt szeretnénk.

Első jelöltek:

### `R-0002` — független ellenőrizhetőség

Válasszunk egy konkrét kritikus működési állítást, és próbáljuk meg megmutatni:

- mi a BIZONYÍTÉK;
- mi a mérce;
- mi a teszt;
- ki tudja ellenőrizni;
- és valóban létezik-e az eredeti állítástól érdemben független ellenőrzési út.

A cél annak vizsgálata, hogy a „független ellenőrzés” követelménye valódi képességet jelent-e, vagy könnyen adminisztratív formalitássá válhat.

### `R-0008` — támadói képességfeltételezés

Válasszunk egy konkrét kritikus biztonsági állítást, és bontsuk ki:

```text
biztonsági állítás
    ->
threat model
    ->
szükséges támadói képességkorlát
    ->
a korlát BIZONYÍTÉKA
    ->
mi történik, ha a korlát nem áll fenn?
```

A cél annak vizsgálata, hogy ez a követelmény valóban ellenőrizhető-e, és nem hoz-e létre új önigazolási kört.

### `R-0009` — szakmai kockázatjelzés és döntés

Egy múltbeli, valós vagy szimulált döntési helyzetben rekonstruáljuk:

```text
szakmai kockázatjelzés
    ->
BIZONYÍTÉK / bizonytalanság
    ->
eszkaláció
    ->
tényleges döntési szint
    ->
döntés
    ->
kockázat vállalása esetén indok + felelős
```

A cél annak vizsgálata, hogy a követelmény megőrzi-e a szakmai információ és a döntési authority különbségét, miközben megakadályozza a lényeges kockázatjelzés szervezeti eltűnését.

Más követelmény kipróbálása ugyanilyen értékes lehet, ha valaki ahhoz tud jó valós esetet vagy ellenpéldát hozni.

## Milyen szakmai nézőpontokat keresünk?

Nem egyetlen szakmai iskola vagy két meglévő álláspont közötti választást szeretnénk.

Különösen hasznosak lehetnek egymástól részben független nézőpontok:

- kiberbiztonság, security engineering;
- system safety, resilience, incident és recovery gyakorlat;
- közigazgatási jog, közjog, hatáskör és hivatalos aktus;
- digitális közigazgatás, szolgáltatástervezés, élethelyzet-alapú működés;
- kritikus infrastruktúra és fizikai folytonosság;
- beszállítói függőség, migráció, exit és hosszú távú üzemeltetés;
- adatvédelem és állami adatintegráció;
- archívum, provenance és hosszú távú digitális megőrzés;
- tényleges állami vagy nagyvállalati üzemeltetési tapasztalat.

Nem szükséges, hogy minden résztvevő az egész dokumentumot véleményezze. Egy szűk területen adott pontos ellenpélda vagy failure scenario többet érhet egy általános támogató véleménynél.

## Hogyan kezeljük a visszajelzést?

A visszajelzésből nem következik automatikusan Manifesztó-módosítás.

A következő különbséget tartjuk fenn:

```text
egy követelmény további részletezést igényel
    !=
a Manifesztóban lyuk van

a követelmény nem vezethető le koherensen
VAGY
az operacionalizálás nem szándékolt normatív következményhez vezet
    ->
lehetséges Manifesztó-delta
```

A következő körben ezért külön kezeljük:

- a Manifesztó szintjén szükséges változásokat;
- az `Alapok`-ban szükséges pontosításokat;
- a pusztán implementációs kérdéseket;
- és azokat az eseteket, ahol nincs szükség változtatásra.

## Nyilvánosság és BIZONYÍTÉK

A követelmények és a bizonyítékmódszertan nyilvánossága nem jelenti azt, hogy a konkrét kitöltött audit-, teszt-, függőség-, recovery-, authority- vagy security-recordoknak is nyilvánosnak kell lenniük.

A konkrét BIZONYÍTÉK külön biztonsági és publikációs felülvizsgálat tárgya. Titok, kulcs, sérülékenységi adat vagy más operatívan érzékeny információ nem kerül nyilvános repositoryba pusztán azért, mert valamely követelmény BIZONYÍTÉKOT kér.

## Szerzőség és közreműködés

A Manifesztó v1.0 közzétett, rögzített szöveg; az `Alapok` első követelménykészlete és a jelen státuszdokumentum továbbra is felülvizsgálható munkadokumentumok.

A forrásként vagy szakmai előzményként megnevezett személy nem válik ettől automatikusan a követelmény szerzőjévé, támogatójává vagy jóváhagyójává.

Ugyanígy a review-ban való részvétel sem jelent automatikusan szerzőséget vagy későbbi aláírói státuszt.

A Manifesztó szerzői, közreműködői, forrásai és későbbi aláírói külön kategóriák.

## Következő kapu

A v1.0 közzététele utáni szakmai munkafolyamat:

```text
publikált Manifesztó v1.0 + első Alapok-követelménykészlet
    ->
heterogén szakmai falszifikáció
    ->
2–3 dry run
    ->
Alapok revision
    ->
Manifesztó delta check
    ->
csak szükség esetén: külön döntés egy későbbi Manifesztó-verzióról
```

A Manifesztó v1.0 publikálása nem jelent követelményteljességi vagy műszaki tanúsítást. A következő szakmai előrelépés feltétele, hogy a követelmények valós kritikával és legalább néhány konkrét alkalmazási próbával is szembesüljenek.

Az online aláírási nyilvántartás élesítése ettől elkülönülő feladat. A csatlakozás aktuális állapotát és módját a [`manifesto/CSATLAKOZAS.md`](https://github.com/digitalis-bizalom/manifesto/blob/main/CSATLAKOZAS.md) tartalmazza; a Manifesztó kiadása önmagában nem jelenti, hogy az online aláírás már elérhető.
