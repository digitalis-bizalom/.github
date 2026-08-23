# GOVERNANCE.md

## 1. A dokumentum célja

Ez a dokumentum a `digitalis-bizalom` GitHub organization és közös repositoryjai működésének alapvető szabályait rögzíti.

A governance kanonikus helye:

```text
digitalis-bizalom/.github/GOVERNANCE.md
```

A cél, hogy világosan elváljon egymástól:

```text
repository ownership
!= source authorship
!= authorship
!= contribution
!= merge
!= endorsement
!= signature
```

Az organization- és repository-szintű technikai jogosultságok önmagukban nem keletkeztetnek szerzőséget, támogatást vagy nyilvános egyetértést a Manifestóval vagy más közös dokumentummal.

## 2. Az organization és a repositoryk szerepe

A `digitalis-bizalom` olyan nyilvános szakmai infrastruktúrának készül, amelyben különválik:

```text
rövid, nyilvánosan vállalható szakmai minimum
+
részletes, ellenőrizhető szakmai alapok
+
közös működési és hozzájárulási szabályok
```

A fő repositoryk szerepe:

```text
.github
    = organization-szintű governance,
      contribution rules és landing/profile surface

manifesto
    = rövid, nyilvánosan vállalható szakmai minimum

alapok
    = követelmények, bizonyítékok, mércék és tesztek
```

Az organization és repositoryjai:

- nem politikai párt vagy kampány infrastruktúrája;
- nem állami vagy piaci szervezet hivatalos felülete;
- nem minősítési vagy tanúsítási rendszer;
- nem tesznek automatikusan közös állítássá egyetlen résztvevő korábbi szövegét sem;
- nem emelnek automatikusan referenciamegoldássá egyetlen résztvevő saját technológiáját, termékét, cégét vagy platformját sem.

## 3. Szerepek

### 3.1 Organization owner

Az organization owner technikai és adminisztratív jogosultsággal rendelkezik.

Az owner státusz:

```text
owner
!= author
owner
!= signatory
owner
!= endorser
```

### 3.2 Source author

Source author az, akinek korábbi, önálló munkája érdemi forrásként szolgál egy új dokumentum elkészítéséhez.

A korábbi forrásanyag felhasználása önmagában nem keletkeztet szerzőséget az új dokumentumon.

```text
source author
!= author
```

Jelentős eredeti forráshozzájárulás ugyanakkor megalapozhatja a co-author státuszt, ha az érintett a konkrét új dokumentum szerzőségét és az ezzel járó felelősséget explicit elfogadja.

### 3.3 Contributor

Contributor az, aki issue-val, pull requesttel, forrással, javítással vagy más dokumentált hozzájárulással részt vesz a munkában.

A contribution:

```text
contribution
!= endorsement
contribution
!= authorship
```

### 3.4 Author

Author az, akit egy adott publikált dokumentum vagy dokumentumverzió szerzőjeként kifejezetten feltüntetünk, az érintett előzetes beleegyezésével.

A szerzői státusz a konkrét dokumentumhoz kapcsolódik, és nem következik automatikusan korábbi forrásanyagból, organization-szerepből vagy technikai hozzájárulásból.

### 3.5 Signatory

Signatory az, aki egy meghatározott Manifesto-verzió nyilvános állításait kifejezetten, saját nevével vállalja.

A signatory státusz mindig explicit és verzióspecifikus.

```text
author
!= signatory
signatory
!= owner
```

A signatory státuszt a `manifesto/SIGNATORIES.md` módosítására irányuló pull request rögzíti.

A pull request csak dokumentálja a vállalást; önmagában nem helyettesíti az érintett explicit beleegyezését a pontos Manifesto-verzióhoz.

Az explicit beleegyezés történhet például:

- az érintett saját pull requestjével;
- GitHub issue- vagy pull-request-kommentben;
- más dokumentált kommunikációs csatornán.

Ha a beleegyezés nem GitHubon történik, a megfelelő pull requestet egy owner vagy contributor készítheti el, a consent tényének rögzítésével.

## 4. Szerzőség és endorsement

A repositoryban szereplő változtatás elfogadása nem jelenti automatikusan, hogy minden owner, contributor, author vagy későbbi signatory egyetért a változtatás teljes tartalmával.

Ezért:

```text
merge
!= endorsement
```

A Manifesto publikálásra szánt változatánál a névvel való szerzőség és a signatory státusz külön, explicit döntés.

## 5. Publikáció

Egy szöveg csak akkor tekinthető közös, névvel vállalt Manifesto-verziónak, ha:

1. a közzétenni kívánt pontos verzió rögzített;
2. a publikációs státusz egyértelmű;
3. a feltüntetett szerzők ezt a konkrét verziót explicit szerzőként elfogadták;
4. a feltüntetett signatoryk ezt a konkrét verziót explicit vállalták;
5. a szükséges forrás- és tényellenőrzés megtörtént;
6. a publikációs kockázatok felülvizsgálata megtörtént.

A repository nyilvános volta önmagában nem jelenti azt, hogy minden benne lévő branch, issue, proposal vagy draft közös álláspont.

## 6. Név visszavonása publikáció előtt

Bármely érintett kérheti, hogy a nevét a még nem véglegesített vagy még nem publikált közös változatról eltávolítsák.

A név visszavonása nem igényel indokolást.

A már publikált történeti verziók támogatottságának későbbi megváltozását új commitban, új státuszban vagy új verzióban rögzítjük.

## 7. Publikált Git-history és javítások

A közös repositoryk publikált `main` branchének történetét normál működésben nem írjuk át.

Javítás, visszavonás vagy álláspontváltozás:

- új committal;
- revert-tel;
- vagy új dokumentumverzióval

történik, nem korábbi publikált commitok módosításával vagy eltávolításával.

```text
correction
!= history rewrite
```

Kivételes history rewrite csak indokolt rendkívüli esetben elfogadható, például:

- véletlenül commitolt secret vagy credential;
- személyes adat vagy más védendő információ véletlen közzététele;
- súlyos security incident;
- jogi kötelezettség.

Az ilyen beavatkozást — amennyiben ez a kivétel céljával összeegyeztethető — külön dokumentálni kell.

A repositoryk merge-policyjének célja a jól követhető provenance. A public közös munkában alapértelmezettként a pull request + explicit merge commit modellt használjuk.

A repository-beállításokban ezért a tervezett public működés:

```text
Allow merge commits: ON
Allow squash merging: OFF
Allow rebase merging: OFF
force push to protected main: OFF
```

A `Require linear history` szabályt ehhez a modellhez nem használjuk.

## 8. Saját technológiák és implementation candidates

Egy résztvevő saját:

- cége;
- terméke;
- platformja;
- politikai vagy civil infrastruktúrája;
- technológiai stackje;
- architekturális megoldása

nem válik attól közös referenciamegoldássá, hogy az érintett source author, author, contributor, signatory vagy organization owner.

Általános szabály:

> **Követelmény != implementáció.**

Egy implementation candidate csak ugyanazon nyilvános követelmények alapján vizsgálható, mint bármely más megoldás.

## 9. Nagy governance-döntések

Amíg az organizationnek egyetlen ownere van, a bootstrap-döntéseket az aktuális owner hozza meg.

A tervezett három-owner működés kialakulásáig, ha átmenetileg két owner van, a nagy governance-döntéseket — a harmadik tervezett owner meghívásának kivételével — csak mindkét owner egyetértésével hozzuk meg.

Ha három owner van, az alábbi döntésekhez legalább **két owner előzetes egyetértése** szükséges:

- owner hozzáadása vagy eltávolítása;
- organization átnevezése vagy törlése;
- repository törlése vagy más account alá transzferálása;
- repository public/private visibility megváltoztatása;
- a jelen governance szabályainak érdemi módosítása;
- a Manifesto publikációs státuszának megváltoztatása;
- új hivatalos publication surface létrehozása;
- kivételes history rewrite jóváhagyása;
- olyan technikai vagy szervezeti változtatás, amely érdemben megváltoztatja a projekt kontrollját vagy nyilvános jelentését.

Negyedik organization owner hozzáadása előtt a jelen governance owner-döntési szabályait felül kell vizsgálni.

A 2-of-3 szabály governance-kötelezettség; a GitHub technikailag nem feltétlenül kényszeríti ki minden owner-műveletnél.

## 10. Hétköznapi repository-műveletek

A hétköznapi szerkesztési, dokumentációs és hibajavítási műveleteket nem kell governance-döntéssé emelni.

A cél:

```text
low friction for ordinary work
+
explicit consent for consequential change
```

### Pull requestek review-ja és merge-elése

GitHubon a pull request szerzője saját pull requestjét nem approve-olhatja.

Attól kezdve, hogy a repositoryban egynél több, review-ra jogosult személy van:

> **A pull request szerzője nem merge-elheti a saját pull requestjét.**

A merge előtt legalább egy másik, megfelelő repository-jogosultsággal rendelkező személy jóváhagyása szükséges.

```text
PR author != approving reviewer
PR author != merger
organization owner != exclusive merger
```

Az approving reviewer és a merger lehet ugyanaz a másik személy, ha a repository szabályai ezt megengedik.

Az organization owner szerep önmagában nem kizárólagos merge-jogosultság: a merge lehetőségét a repository-jogosultságok és az alkalmazott branch/ruleset szabályok határozzák meg.

Ez a szabály technikai kontroll és eljárási norma egyszerre: több résztvevős működésben senki nem fogadja el és nem juttatja be egyedül a saját változtatását a közös `main` branchbe.

A későbbi branch/ruleset és review-szabályokat a repository nyilvánossá tétele és a több-owner működés stabilizálása után lehet szigorítani.

## 11. Tényállítások és források

Személyre, intézményre, eseményre, konkrét rendszerre vagy aktuális magyar helyzetre vonatkozó erős tényállításhoz megfelelő forrás szükséges.

A normatív állításokat és a leíró diagnózist el kell választani.

```text
normative requirement
!= factual diagnosis
```

A vitatott tényállításokat nem kezeljük pusztán szerzői tekintély alapján eldöntött kérdésként.

## 12. Politikai semlegesség a működésben

A projekt tárgya közpolitikai és állami, ezért politikai következményei lehetnek. Ettől azonban az organization és repositoryjai működése nem válhat párt- vagy kampányszervezéssé.

A szakmai követelményeket elvileg azonos mércével kell alkalmazni:

- a mindenkori kormányra;
- állami intézményekre;
- beszállítókra;
- auditáló és felügyeleti szervekre;
- releváns piaci és civil szereplőkre.

## 13. Kanonikus dokumentumok és repositoryk kapcsolata

A közös dokumentumok kanonikus példánya mindig az abban a repositoryban verziózott fájl, amelynek az adott dokumentum a tárgya.

```text
.github/GOVERNANCE.md
    = governance kanonikus példánya

manifesto/manifesto.md
    = Manifesto kanonikus példánya

alapok/**
    = részletes szakmai Alapok kanonikus példányai
```

A landing page, organization profile, későbbi weboldal vagy más presentation surface ezeket **bemutathatja és linkelheti**, de önmagában nem válik külön, eltérő normatív forrássá.

```text
presentation surface
!= canonical document
```

Ha valamely presentation surface teljes dokumentumszöveget is megjelenít, annak kanonikus forrása továbbra is a megfelelő repository-fájl.

## 14. Landing page és későbbi webes publication surface

Az organization elsődleges GitHub-landing page-e a `.github/profile/README.md`.

Ennek feladata:

- röviden megmondani, mi a `Digitális Bizalom`;
- a `manifesto` és az `alapok` repositorykhoz irányítani;
- az aktuális publication státuszt közérthetően jelezni;
- a governance és contribution szabályokhoz linkelni;
- kerülni a kanonikus dokumentumok szükségtelen duplikálását.

A landing page ezért **navigációs és bemutatkozó surface**, nem önálló harmadik fő dokumentum.

A repositoryk nyilvánossá válása után a `manifesto` és az `alapok` kiemelhető az organization profilján.

Ha később önálló weboldal készül, annak javasolt GitHub-helye egy külön:

```text
digitalis-bizalom/digitalis-bizalom.github.io
```

repository.

A későbbi weboldal presentation layer legyen:

```text
website
    -> manifesto/manifesto.md
    -> alapok/**
    -> .github/GOVERNANCE.md
```

A weboldal lehetőleg ne tartson fenn kézzel szerkesztett, önálló másolatokat a kanonikus dokumentumokról. Ha később automatizált publikáció készül, annak forrása a kanonikus repository-tartalom legyen.

Amíg nincs erre külön, auditált publication workflow, az organization profile README + a GitHub által renderelt Markdown-dokumentumok elegendő public webes surface-t adnak.

## 15. Módosítás

A jelen dokumentum maga is verziózott és módosítható.

A governance lényegi módosítása nem történhet úgy, hogy az észrevétlenül megváltoztassa:

- a source authorship jelentését;
- a szerzőség jelentését;
- az endorsement jelentését;
- a signature jelentését;
- a publication státuszt;
- az owneri kontrollt;
- az implementation-neutrality elvét;
- a publikált history megőrzésének szabályát;
- a kanonikus dokumentumok és presentation surface-ek viszonyát.
