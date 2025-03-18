# Változók

A JavaScript alkalmazásoknak legtöbbször információkkal kell dolgozniuk. Íme két példa: 
1. Online bolt -- az információ tartalmazhatja az eladott árukat, és a kosarat.
2. Chat alkalmazás -- az információ tartalmazhatja a felhasználókat, üzeneteket és még sok egyebet.

Az információk tárolásához változókat használunk.

## Változók

A [változó](https://hu.wikipedia.org/wiki/V%C3%A1ltoz%C3%B3_(sz%C3%A1m%C3%ADt%C3%A1stechnika))) az adatok "elnevezett tárolója". Változókat használhatunk édességek, látogatók és egyéb adatok tárolására.

Változó létrehozásához JavaScriptben használd a "let" kulcsszót.

Az alábbi utasítás létrehoz (másszóval: *deklarálás*) egy változót aminek a neve "message".

```js
let message;
```

Most hozzáadunk néhány adatot a `=` operátor használatával:

```js
let message;

*!*
message = 'Hello'; // eltároljuk az értéket
*/!*
```

A szöveg(string) most a változóhoz tartozó memóriába kerül mentésre. Elérhetjük a használt változó nevével:

```js run
let message;
message = 'Hello!';

*!*
alert(message); // megmutatja a változó értékét
*/!*
```

Az egyszerűsítés kedvéért alakítsuk át egy sorba:

```js run
let message = 'Hello!'; // definiáljuk a változót, és hozzárendelünk egy értéket

alert(message); // Hello!
```

Egy sorba több változót deklarálhatunk.

```js no-beautify
let user = 'John', age = 25, message = 'Hello';
```

Egyszerűbbnek tűnhet, de nem ajánlatos. Az átláthatóság kedvéért használjunk egy változót soronként.

A többsoros változók hosszabbak, de könnyebb elolvasni:

```js
let user = 'John';
let age = 25;
let message = 'Hello';
```

Vannak emberek akik több változót is deklarálnak ebben a többsoros stílusban:
```js no-beautify
let user = 'John',
  age = 25,
  message = 'Hello';
```

...Vagy akár a  "comma-first" stílus:

```js no-beautify
let user = 'John'
  , age = 25
  , message = 'Hello';
```

A változók ugyanazt csinálják, ez csak egyéni ízlés és esztétikum kérdése.

````smart header="`var` a `let` helyett"
Néhány régebbi szkriptekben másik kulcsszót is megtalálhatunk: `var` a `let` helyett:

```js
*!*var*/!* message = 'Hello';
```

A `var` kulcsszó *közel* hasonló, mint a `let`. Ez is deklarál egy változót, csak egy kicsit "old-school" módon.

A `let` és `var` között vannak különbségek, de ez egyenlőre minket nem érint. Részletesseben a <info:var> fejezetben írunk.
````

## Valós analógia

Könnyen megérthetjük a "változó" fogalmát, ha az adatok "dobozonként" képzeljük el, rajta egy egyedi nevű matricával.

Például a "message" változó elképzelhető egy "üzenet" feliratú dobozként, amelyben a "Hello!"" érték szerepel:

![](variable.svg)

Bármilyen értéket tehetünk a dobozba.

Bármennyiszor megváltozhatjuk az értéket, amikor akarjuk:
```js run
let message;

message = 'Hello!';

message = 'World!'; // az értéket megváltoztatjuk

alert(message);
```

Amikor az érték megváltozik, a régi adatok törlődnek a változóból:

![](variable-change.svg)

Két változót is deklarálhatunk, és adatokat másolhatunk egyikből a másikba.

```js run
let hello = 'Hello world!';

let message;

*!*
// lemásoljuk a 'Hello world' értéket a hello változóból a message változóba
message = hello;
*/!*

// most mindkét változó ugyanazt az értéket kapta
alert(hello); // Hello world!
alert(message); // Hello world!
```

````warn header="A kétszeri deklarálás hibát vált ki"
Egy változót csak egyszer kell deklarálni.

Ugyanazon változó ismételt deklarálása hiba:

```js run
let message = "This";

// ismétlődő 'let' hibára fut
let message = "That"; // SyntaxError: 'message' has already been declared
```
Egyszer kell deklarálnunk egy változót, majd hivatkoznunk kell rá a `let` szó nélkül
````

```smart header="Funkcionális nyelvek"
Érdekes megjegyezni, hogy léteznek úgynevezett tiszta [funkcionális](https://en.wikipedia.org/wiki/Functional_programming) programozási nyelvek, mint például a [Haskell]([https://en.wikipedia.org/wiki/Haskell](https://hu.wikipedia.org/wiki/Haskell_(programoz%C3%A1si_nyelv))), amelyek tiltják a változóértékek megváltoztatását.

Az ilyen nyelveken, ha az értéket „a dobozban” tárolják, az örökre ott van. Ha valami mást kell tárolnunk, akkor a nyelv új doboz létrehozására kényszerít (új változó deklarálására). A régit nem tudjuk újra felhasználni.

Bár első látásra kissé furcsának tűnik, ezek a nyelvek komoly fejlődésre képesek. Ráadásul vannak olyan területek, mint például a párhuzamos számítások, ahol ez a korlátozás bizonyos előnyökkel jár.
```

## Vátlozó elnevezése [#variable-naming]

A JavaScript változóneveinek két korlátozása van:

1. A név csak betűket, számokat vagy `$` és `_` szimbólumokat tartalmazhat.
2. Az első karakter nem lehte szám.

Példa létező változónevekre:

```js
let userName;
let test123;
```

Amikor a név több szót tartalmaz, [camelCase](https://hu.wikipedia.org/wiki/CamelCase) kifejezést gyakran használják. Lényegében: a szavak egymás után következnek, minden utána lévő szó nagybetű, kivéve az első: `azEnHosszuNevem`.

Ami érdekes - a `'$'` dollárjel és az aláhúzásjel `'_'` is használható a nevekben. Szabályos szimbólumok, akárcsak a betűk, különösebb jelentés nélkül.

Ezek a nevek érvényesek:

```js run untrusted
let $ = 1; // deklarálunk egy változót az alábbi névvel "$"
let _ = 2; // most egy másikat az alábbi névvel "_"

alert($ + _); // 3
```

Példák nem elfogadható változóneveknek:

```js no-beautify
let 1a; // nem kezdődhet számmal

let my-name; // a '-' nem engedélyezett a változó nevében
```

```smart header="Különbségek"
Változók nevei, mint az `alma` és `alMa` két különböző változó.
```

````smart header="A nem latin betűk megengedettek, de nem ajánlott"
Bármilyen nyelv használható, beleértve a cirill betűket vagy akár a hieroglifákat is, például:

```js
let имя = '...';
let 我 = '...';
```

Technikailag nincs hiba benne. Az ilyen nevek engedélyezettek, de létezik egy nemzetközi egyezmény az angol nyelv használatára a változónevekben. Még ha egy kis szkriptet is írunk, sok ideig fennmaradhat. Az embereknek más országokból néhányszor el kell majd olvasni.
````

````warn header="Fenntartott nevek"
Megtalálható egy [lista a fenntartott szavaknak](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords), amelyek nem használhatók változónévként, mert maga a nyelv használja őket.

Például: `let`, `class`, `return`, és a `function` fenntartottak.

Az alábbi kód szintaktikai hibát ad:

```js run no-beautify
let let = 5; // nem lehet a változó neve "let", hiba!
let return = 5; // nem lehet a változó neve "return", hiba!
```
````

````warn header="Egy hozzárendelés nélkül `use strict`"

Általában definiálnunk kell egy változót használat előtt. De a régi időkben technikailag lehetséges volt változót létrehozni pusztán az érték hozzárendelésével a "let" használata nélkül. Ez most is működik, ha nem helyezzük el a "use strict" szót a szkriptjeinkben, hogy fenntartsuk a kompatibilitást a régi szkriptekkel.

```js run no-strict
// megjegyzés: nincs "use strict" használva ebben a példában

num = 5; // a változó "num" létrejön, ha nem létezne

alert(num); // 5
```

Íme egy rossz gyakorlás, ami hibát fog eredményezni "strict" módban:

```js
"use strict";

*!*
num = 5; // error: num is not defined
*/!*
```
````

## Konstans

Konstans (megváltozhatatlan) deklarálásához használjuk a `const` kulcssszót a `let` helyett:

```js
const myBirthday = '18.04.1982';
```

A `const` használatával deklarált változókat `konstansoknak` nevezzük. Ezek nem rendelhetők mégegyszer. Egy példa, ami hibát fog visszaadni:

```js run
const myBirthday = '18.04.1982';

myBirthday = '01.01.2001'; // hiba, nem lehetséges rendelhetni mégegyszer!
```

Mikor a programozó biztos abban, hogy a változó soha nem fog változni, akkor a `const` változóval garantálják és egyértelműen közlik mindenkivel.

### Nagybetűs konstans

Széles körben elterjedt gyakorlat, hogy konstansokat használnak álnévként olyan nehezen megjegyezhető értékekhez, amelyek a végrehajtás előtt ismertek.

Az ilyen konstansokat nagybetűkkel és aláhúzásjelekkel nevezzük el.

Például készítsünk konstansokat a színekhez úgynevezett "web" (hexadecimális) formátumban:

```js run
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...mikor választanunk kell színt
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

Előnyök:

- `COLOR_ORANGE` könnyebben megjegyezhető, mint a `"#FF7F00"`.
- Könnyebben elírható a `"#FF7F00"`, mint a `COLOR_ORANGE`.
- Mikor olvasunk egy kódot, `COLOR_ORANGE` jobban érthetőbb, mint a `#FF7F00`.

Mikor használjunk nagybetűket konstansként és mikor nevezzük normálisan? Tegyük világossá.

A "konstans" csak azt jelenti, hogy egy változó értéke soha nem változik. Vannak azonban olyan konstansok, amelyek a végrehajtás előtt ismertek (például a vörös hexadecimális értéke), és vannak olyan állandók, amelyek futási időben, a végrehajtás során *ki vannak számítva*, de nem változnak a kezdeti hozzárendelésük után.

Például:
```js
const pageLoadTime = /* a weboldal betöltéséhez szükséges idő */;
```

A `pageLoadTime` értéke nem ismert az oldal betöltése előtt, ezért a neve normális. De ez még mindig állandó, mert a hozzárendelés után nem változik.

Más szavakkal, a nagybetűs konstansokat csak a "kemény kódolt" értékek álneveként használják.

## Jó elnevezések

Ha a változókról beszélünk, van még egy rendkívül fontos dolog.

A változó neve legyen tiszta, egyértelmű, és leírja, hogy milyen adatokat tárol.

A változók elnevezése az egyik legfontosabb és legösszetettebb a programozásban. Egy gyors pillantás a változónevekre felfedheti, hogy melyik kódot írta kezdő vagy tapasztalt fejlesztő.

Egy valós projekten a legtöbb idő azzal telik, hogy módosításával és bővítésével töltik, ahelyett, hogy valami teljesen különállót írnának. 
In a real project, most of the time is spent modifying and extending an existing code base rather than writing something completely separate from scratch. Ha visszatérünk valamilyen kódhoz, miután valami mást csináltunk egy ideig, sokkal könnyebb megtalálni a jól felcímkézett információkat. Vagy más szóval, amikor a változóknak jó neve van.

Kérlek szánj időt a jó nevekhez, mielőtt deklarálod. Ha így tesz, jócskán megtérül.

Néhány jó betartandó szabály:

- Használjon ember által olvasható neveket, pl. `userName` vagy `shoppingCart`.
- Kerüld az olyan rövidítéseket, vagy rövid neveket, mint az `a`, `b`, `c`, ha csak nem igazán tudod, hogy mit csinál.
- Legyen a nevek maximálisan leíró és tömör. Példák a rossz nevekre: `data`és `value`. Az ilyen nevek nem mondanak semmit. Csak akkor szabad ezeket használni, ha a kód kontextusa kivételesen nyilvánvalóvá teszi, hogy a változó melyik adatra vagy értékre hivatkozik.
- Állapodjon meg a feltételekben a csapaton belül és saját fejében. Ha egy webhely látogatóját "user"-nek nevezik, akkor a kapcsolódó változókat `currentUser` vagy `newUser` néven kell neveznünk a `currentVisitor` vagy `newManInTown` helyett.

Egyszerűen hangzik? Valóban az, de leíró és tömör változónevek létrehozása a gyakorlatban nem. Hajrá.

```smart header="Újrahasználat, vagy új?"
És az utolsó megjegyzés. Vannak olyan lusta programozók, akik ahelyett, hogy új változókat deklarálnának, hajlamosak a meglévő változókat újra felhasználni.

Ennek eredményeként a változóik olyanok, mint a dobozok, amelyekbe az emberek különféle dolgokat dobnak anélkül, hogy megváltoztatnák a matricáikat. Mi van most a dobozban? Ki tudja? Közelebb kell mennünk és ellenőrizni kell.

Az ilyen programozók keveset takarítanak meg a változó deklarációján, de tízszer többet veszítenek a hibakeresés során.

Egy extra változó jó, nem ördögtől való.

A modern JavaScript-minifikátorok és böngészők kellően jól optimalizálják a kódot, így nem okoznak teljesítménybeli problémákat. A különböző értékekhez különböző változók használata akár a kód optimalizálását is segítheti a motornak.
```

## Összegezve

Az adatok tárolására szolgáló változókat deklarálhatunk a `var`, `let`, or `const` kulcsszavakkal.

- `let` -- egy modern változó deklaráció.
- `var` -- egy "old-school" változó deklarációja. Normális esetben egyáltalán nem haszáljuk, de a különbségeket a `let` változóval az alábbi fejezetben <info:var> fejtünk ki bővebben.
- `const` -- hasonló, mint a `let`, de az értéke a változónak nem változtatható.

A változókat úgy kell elnevezni, hogy könnyen megérthessük, mi van bennük.
