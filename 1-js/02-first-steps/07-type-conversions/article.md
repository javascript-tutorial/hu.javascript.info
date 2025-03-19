# Konverzió típusok

Legtöbbször operátorok és függvények automatikusan átalakítják az értéket a megfelelő típusra.


Mint például `alert` minden megadott értéket Stringnek alakít át, hogy megjelenítse. A matematikai műveletek az értékeket számokká alakítják.

Vannak esetek mikor nekünk kell kifejezetten átalakítani az értéket az elvárt típusra.

```smart header="Objektumokról még nem is beszélve"
Ebben a fejezeben nem  takarunk el objektumokat. Jelenleg csak a primitívekről beszélünk.

Később, miután beszélünk az objektumokról, a fejezetben <info:object-toprimitive> megnézzük hogy illeszkednek.
```

## String Konverziók

String konverzió történik mikor nekünk szükséges van egy érték string formájára.

Mint például `alert(value)` megmutatja az értéket.

Ugyanúgy meghívhatjuk a `String(value)` függvényt, ahhoz hogy stringgé alakítsuk:

```js run
let value = true;
alert(typeof value); // boolean

*!*
value = String(value); // most az érték string "true"
alert(typeof value); // string
*/!*
```

String konverzió legtöbbször egyértelmű. A `false` változik `"false"`-ra, `null` változik `"null"`-ra, stb.

## Szám Konverziók

Szám konverzió történik a matematikai függvényekben és kifejezésekben automatikusan.

Mint például amikor osztunk `/` nem számokra is vonatkozik:

```js run
alert( "6" / "2" ); // 3, stringek átalakítva számokká
```

Használhatjuk `Number(value)` függvényt, hogy átalakítsuk a `value` számmá:

```js run
let str = "123";
alert(typeof str); // string

let num = Number(str); // átváltozik számmá 123

alert(typeof num); // szám
```

Explicit konverzió akkor szükséges mikor mi olvasunk egy értéekt a string-alapú forrásból, pl. egy szöveges űrlapból olvasunk ki egy értéket, de számot írtunk be.

Mikor a string nem valós szám, az eredmény átalakítás eredménye `NaN`. Mint például:

```js run
let age = Number("an arbitrary string instead of a number");

alert(age); // NaN, átalakítási hiba
```

Szám átalakítási szabály:

| Value |  Becomes... |
|-------|-------------|
|`undefined`|`NaN`|
|`null`|`0`|
|<code>true&nbsp;and&nbsp;false</code> | `1` and `0` |
| `string` | Szóközöket az elejéről és hátuljáról eltávolítjuk.Mikor a többi maradt string üres, az eredmény `0`. Különben a szám "olvasható" a stringből. A hiba pedig `NaN`-t ad vissza.

Például:

```js run
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN (számként nem tudja beolvasni a "z"-t)
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

Kérjük, vedd figyelembe, hogy a `null` és `undefined` másképp viselkedik: `null` átalakul nullává, miközben az `undefined` átalakul `NaN` értékké.

A legtöbb matematikai operátor is végez ilyen átalakítást, amit a következő fejezetben megnézünk.

## Boolean Konverziók

Boolean conversion is the simplest one.

It happens in logical operations (later we'll meet condition tests and other similar things) but can also be performed explicitly with a call to `Boolean(value)`.

A konverzió szabály:

- Értékek intuitív módon "empty" értékűek, mint a `0`, egy üres string, `null`, `undefined`, és `NaN`, átalakul `false` értékké.
- Más értékek pedig `true` értékűek.

Mint például:

```js run
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("hello") ); // true
alert( Boolean("") ); // false
```

````warn header="Vedd figyelembe: a string 0-val `\"0\"` az `true`"
Néhány nyelvek (pl. PHP) a `"0"` az `false`. De JavaScriptben a nem üres string az mindig `true`.

```js run
alert( Boolean("0") ); // true
alert( Boolean(" ") ); // spaces, also true (any non-empty string is true)
```
````

## Összegzés

A három legszélesebb körben használt típuskonverzió a stringre, számra és boolean értékre.

**`String Konverziók`** -- Akkor fordul elő, ha valamit kiadunk. A `String(value)` paraméterrel hajtható végre. A stringre átalakítás általában nyilvánvaló primitív értékek esetén.

**`Szám Konverziók`** -- A matematikai műveletekben fordul elő. A `Number(value)` paraméterrel hajtható végre.

A konverziók az alábbi szabályt használják:

| Value |  Becomes... |
|-------|-------------|
|`undefined`|`NaN`|
|`null`|`0`|
|<code>true&nbsp;/&nbsp;false</code> | `1 / 0` |
| `string` | A string "as is" mindkét oldalon figyelmen kívül hagyja a szóközöket. Egy üres string visszaadja a `0` értéket. Egy hiba pedig `NaN` értéket. |

**`Boolean Konverziók`** -- Logikai műveletekben fordul elő. A `Boolean(value)` paraméterrel hajtható végre.

Kövesd a szabályt:

| Value |  Becomes... |
|-------|-------------|
|`0`, `null`, `undefined`, `NaN`, `""` |`false`|
|any other value| `true` |


A szabályok többsége könnyen érthető és megjegyezhető. A figyelemre méltó kivételek, ahol az emberek általában hibáznak, a következők:

- `undefined` az `NaN` mint szám, nem `0`.
- A `"0"` és a csak a szóközt használok stringek pl. `"   "` logikai értékként igazak.

Az objektumokat nem érintettük a fejezetben. Később a <info:object-toprimitive> fejezetben beszélünk róla, amely kizárólag az objektumoknak van szentelve, miután további alapvető dolgokat tanultunk a JavaScriptről.
