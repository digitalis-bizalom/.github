# CONTRIBUTING.md

Köszönjük a hozzájárulást a `digitalis-bizalom` munkájához.

Ez a dokumentum a közös repositorykban végzett munka gyakorlati menetét írja le. A szerepekre, szerzőségre, signatory státuszra, owneri kontrollra, publikációra és más governance-kérdésekre a [`GOVERNANCE.md`](GOVERNANCE.md) az irányadó.

## 1. Mielőtt hozzájárulsz

A projekt célja nem egyetlen technológia, intézmény vagy politikai szereplő támogatása, hanem nyilvánosan vizsgálható szakmai követelmények kialakítása a megbízható digitális államhoz.

A közös munka alapelve:

```text
állítás
-> indoklás
-> evidencia
-> mérce
-> teszt
```

A hozzájárulás akkor a leghasznosabb, ha világos, hogy:

- mit állít vagy változtat;
- miért szükséges;
- milyen forrás vagy evidencia támasztja alá, ha tényállításról van szó;
- milyen következménye lenne az elfogadásának;
- és hol van a megfelelő helye a repository-struktúrában.

## 2. Mi hova tartozik?

```text
.github/
    közös governance, contribution rules
    és organization-level presentation

manifesto/
    rövid, nyilvánosan vállalható szakmai minimum

alapok/
    részletes követelmények, evidenciák,
    mércék, tesztek és módszertan
```

A `manifesto` és az `alapok` nem egymás másolatai.

A Manifesto rövid normatív állításokat tartalmaz. Az ezekhez szükséges szakmai kibontás, bizonyíték, mérce és teszt elsődleges helye az `alapok`.

## 3. Hozzájárulási formák

Hozzájárulás lehet például:

- issue;
- pull request;
- hibajavítás;
- új vagy pontosabb forrás;
- ellenpélda;
- követelmény vagy teszt javítása;
- új szakmai terület javaslata;
- implementation candidate dokumentálása;
- módszertani vagy governance-javaslat.

A contribution önmagában nem jelent szerzőséget, endorsementet vagy signatory státuszt. Ezeket a `GOVERNANCE.md` külön kezeli.

## 4. Issue vagy pull request?

Kisebb, egyértelmű javításhoz közvetlenül készíthető pull request.

Issue különösen akkor célszerű előbb, ha a változtatás:

- új szakmai irányt nyit;
- több dokumentumot érint;
- lényegi normatív állítást módosít;
- governance-kérdést vet fel;
- új implementation candidate-et vezet be;
- vagy jelentős vita várható róla.

Az issue célja nem kötelező előengedély megszerzése, hanem annak elkerülése, hogy nagyobb munka rossz irányba induljon.

## 5. Pull requestek

Egy pull request lehetőleg egy világosan körülhatárolható változtatást tartalmazzon.

A PR leírásából derüljön ki:

1. mi változik;
2. miért;
3. mely dokumentumokat érinti;
4. van-e új tényállítás vagy forrás;
5. van-e governance-, publication- vagy implementation-neutrality következménye.

Nagyobb módosításnál célszerű külön jelezni:

```text
NORMATIVE CHANGE:
YES / NO

NEW FACTUAL CLAIM:
YES / NO

NEW IMPLEMENTATION ASSUMPTION:
YES / NO

GOVERNANCE IMPACT:
YES / NO
```

Ez nem kötelező űrlap, hanem review-segédeszköz.

## 6. Review és merge

A bootstrap-szakaszban, amíg az organizationnek egyetlen ownere van, közvetlen commit is használható.

Attól kezdve, hogy egy repositoryban egynél több review-ra jogosult személy van, a közös `main` branchre kerülő érdemi változtatások alapértelmezett útja:

```text
branch
-> pull request
-> review
-> approval
-> merge commit
-> main
```

A pull request szerzője:

- saját PR-ját GitHubon nem approve-olhatja;
- több résztvevős működésben saját PR-ját nem merge-elheti.

A merge előtt legalább egy másik, megfelelő repository-jogosultsággal rendelkező személy jóváhagyása szükséges.

A tervezett merge-policy:

```text
merge commits: ON
squash merging: OFF
rebase merging: OFF
force push to protected main: OFF
```

A cél a jól követhető provenance, nem a mesterségesen lineáris történet.

## 7. Tényállítások és források

Személyre, intézményre, eseményre, jogszabályra, konkrét rendszerre vagy aktuális helyzetre vonatkozó erős tényállítást megfelelő forrással kell alátámasztani.

A forrás lehetőleg:

- elsődleges;
- ellenőrizhető;
- pontosan hivatkozható;
- és az állítás időbeli hatályához megfelelően friss legyen.

A normatív állítást és a leíró diagnózist külön kell kezelni:

```text
normative requirement
!= factual diagnosis
```

Ha egy állítás vitatott vagy bizonytalan, ezt a szövegben vagy a kapcsolódó evidenciában jelezni kell.

## 8. Követelmény és implementáció

A projekt alapvető szabálya:

> **Követelmény != implementáció.**

Technológia, termék, platform, architektúra vagy intézményi megoldás javasolható és vizsgálható, de nem válik automatikusan közös referenciamegoldássá.

Implementation candidate esetén világosan el kell választani:

```text
milyen követelményt próbál teljesíteni
!=
mi maga a javasolt megoldás
```

A saját vagy kapcsolt termékhez, céghez, platformhoz vagy projekthez fűződő lényeges érdekeltséget a releváns contributionben fel kell tüntetni.

## 9. Az `alapok` követelményeinek formája

Az `alapok` konkrét követelményeinél a cél az egységes, ellenőrizhető szerkezet.

Alapértelmezett mezők:

```text
KÖVETELMÉNY
EVIDENCIA
MÉRCE
TESZT
FAILURE CONDITION
FORRÁS
STATUS
```

Egy új követelménynek nem feltétlenül kell az első PR-ban minden mezőben teljesnek lennie, de a hiányzó részeket láthatóan kell jelölni.

A részletes módszertani szabályokat az `alapok/00-modszertan/` dokumentumai határozzák meg.

## 10. A Manifesto módosítása

A `manifesto.md` rövid közös szakmai minimum, ezért módosítása különösen érzékeny.

Manifesto-módosításnál a PR-ben célszerű megmutatni:

- mely állítás változik;
- milyen szakmai probléma indokolja;
- hogyan kapcsolódik az `alapok` követelményeihez;
- és változik-e miatta a már publikált verzió jelentése.

A Manifesto szerzősége és signatory státusza nem keletkezik contributionből vagy merge-ből; ezek explicit, verzióspecifikus státuszok a `GOVERNANCE.md` szerint.

## 11. Commitok

A commitok legyenek lehetőleg kicsik, értelmezhetőek és egyértelműen elnevezettek.

Javasolt példák:

```text
Clarify evidence requirements
Add recovery test criterion
Document implementation-candidate policy
Fix terminology in manifesto
```

Kerüljük az olyan commit message-eket, mint:

```text
update
changes
fix
misc
```

ha ennél pontosabban megnevezhető a változás.

A publikált `main` history utólagos átírását a `GOVERNANCE.md` szabályozza.

## 12. Érzékeny vagy nem publikálható anyag

A repositoryk történetét úgy kezeljük, mintha később nyilvánossá válhatna.

Ezért ne kerüljön commitba:

- secret, credential vagy token;
- szükségtelen személyes adat;
- bizalmas levelezés;
- nem publikálható belső értékelés;
- harmadik fél olyan anyaga, amelynek közzétételére nincs megfelelő jog;
- olyan belső munkadokumentum, amely nem része a public szakmai felületnek.

Ha ilyen tartalom véletlenül commitba kerül, azt azonnal jelezni kell egy organization ownernek.

## 13. Vita és ellenvélemény

A szakmai vita a projekt normális működésének része.

Egy javaslat elutasítása vagy módosítása lehetőleg az állításra, evidenciára, mércére, tesztre vagy governance-következményre hivatkozzon, ne a hozzájáruló személyére.

Ha nincs konszenzus, a vitatott kérdés:

- nyitva maradhat;
- visszakerülhet további evidenciagyűjtésre;
- több alternatív javaslatra bontható;
- vagy elutasítható.

A merge nem cél önmagában.

## 14. Governance-módosítás

A `GOVERNANCE.md` módosítására is a jelen contribution workflow alkalmazandó, de a lényegi governance-változások elfogadására a `GOVERNANCE.md` külön owner-döntési szabályai irányadók.

Ha a jelen dokumentum és a `GOVERNANCE.md` között ellentmondás van, a `GOVERNANCE.md` az irányadó.
