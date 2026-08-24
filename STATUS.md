# STATUS — digitális bizalom

Ez a dokumentum a `digitalis-bizalom` projekt aktuális munkaállapotát, a nyitott kérdéseket és a következő szakmai ellenőrzési lépéseket foglalja össze.

Nem helyettesíti a Manifesztót vagy az `Alapok` követelményeit, és nem tekinti lezártnak azokat a kérdéseket, amelyekhez még szakmai falszifikációt vagy gyakorlati próbát kérünk.

## Aktuális munkabázis

A projekt jelenlegi két fő munkadokumentuma:

- `digitalis-bizalom/manifesto/manifesto.md` — **A digitális bizalom 12 pontja — Manifesztó a megbízható digitális államról**
- `digitalis-bizalom/alapok/elso-kovetelmenykeszlet.md` — az `Alapok` első, tíz rekordos tényleges követelménykészlete

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

A Manifesztó és az első követelménykészlet első belső, kétirányú back-testje megtörtént.

A munka során több olyan pontosítás született, amely nem egyszerű szerkesztési javítás volt, hanem a követelményekre bontásból vált láthatóvá. Ilyen volt többek között:

- az állami működőképesség és a tágabb alkotmányos cél elválasztása;
- a kritikus állítások független ellenőrizhetőségének megerősítése;
- a teljes kilépés és a túlélési út megkülönböztetése kritikus függőségnél;
- a rendkívüli vagy degradált működésből a normál, jogszerű állapotba való visszatérés;
- a technikai jogosultság és a jogszerű közhatalom elválasztása;
- a szakmai kockázatjelzés útja a tényleges döntésig;
- a hosszú távú értelmezhetőség, migrálhatóság, kivezethetőség és archiválhatóság külön kezelése.

Ez fontos eredmény, de nem teljességi bizonyíték. A jelenlegi tíz követelmény szándékosan keresztmetszeti tesztkészlet, nem a teljes követelményrendszer és nem a „tíz legfontosabb” követelmény.

## Mi nincs még lezárva?

A Manifesztóban jelenleg is láthatóan nyitott kérdések:

1. **Támadói képességkorlát.**  
   A pontos kérdés az, hogyan lehet közérthetően kimondani: ha egy kritikus biztonsági állítás valamely feltételezett támadói képességkorláttól függ, ennek a korlátnak is megfelelően alátámasztottnak kell lennie.

2. **Tartós fenyegetettség és rendkívüli működés.**  
   Nyitott, hogy a Manifesztóban külön is szerepeljen-e az az elv, hogy a tartós fenyegetettség önmagában nem igazolja automatikusan a tartós rendkívüli állami működést.

3. **Élethelyzet / szolgáltatási nézőpont.**  
   Nyitott, hogy a Manifesztó főszövegének része legyen-e az az elv, hogy az állammal kapcsolatba kerülő embernek vagy szervezetnek ne az állam szervezeti térképét kelljen ismernie ahhoz, hogy jogát gyakorolja, kötelezettségét teljesítse vagy ügyét elintézze.

Ettől külön, az `Alapok` következő körének kiemelt kérdése:

4. **Mit jelent a kritikus képesség fölötti „tényleges kontroll”?**  
   Olyan operacionalizálás kell, amely megmutatja, milyen minimális állami képességeket szükséges megtartani, de nem vezet automatikusan tulajdonosi, hazai beszállítói vagy általános insourcing-kötelezettséghez.

## Mit kérünk most a szakmai review-tól?

A következő kör célja nem általános egyetértés vagy támogatás megszerzése, és még nem aláírásgyűjtés.

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

A jelenlegi dokumentumok munkaváltozatok.

A forrásként vagy szakmai előzményként megnevezett személy nem válik ettől automatikusan a követelmény szerzőjévé, támogatójává vagy jóváhagyójává.

Ugyanígy a review-ban való részvétel sem jelent automatikusan szerzőséget vagy későbbi aláírói státuszt.

A Manifesztó szerzői, közreműködői, forrásai és későbbi aláírói külön kategóriák.

## Következő kapu

A jelenlegi cél:

```text
current working pair
    ->
heterogén szakmai falszifikáció
    ->
2–3 dry run
    ->
Alapok revision
    ->
Manifesztó delta check
    ->
public-freeze candidate
```

A projekt ezen a ponton még nem állítja, hogy a követelményrendszer teljes, és nem kér végleges szakmai vagy politikai jóváhagyást.

A következő előrelépés feltétele az, hogy a jelenlegi állítások és követelmények valós szakmai kritikával és legalább néhány konkrét alkalmazási próbával is szembesüljenek.
