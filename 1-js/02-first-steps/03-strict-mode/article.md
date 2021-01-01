# Modern üzemmód, "use strict"

A JavaScript hosszú ideig kompatibilitási nehézségek nélkül fejlődött. A nyelv új elemekkel bővült, a meglévőek pedig változatlanok voltak.

A nyelv újabb verziói így kompatibilisek maradtak a korábban írt programokkal, cserébe viszont együtt kellett élni a nyelv tervezésekor hozott rossz döntésekkel.

Ez volt a tényállás, mígnem 2009-ben megjelent az ECMAScript 5 (ES5), amely nem csak bővítette a nyelvet, hanem néhol meg is változtatta a működését. Annak érdekében, hogy ezek a változások ne okozzanak gondot a régebben írt programokban, e változtatások alapértelmezetten ki vannak kapcsolva, az engedélyezésükhöz pedig egy speciális "use strict" diektívát kell elhelyezni a kódban.

## "use strict"

Ez a direktíva ránézésre egy átlagos szöveg (string): "use strict", vagy 'use strict'. A szkript tetejére helyezve azonban arra utasítja a JS motort, hogy a szkriptet modern üzemmódban futtassa.

Példa:

```js
"use strict";

// a kód modern üzemmódban fog működni
...
```

Hamarosan szó lesz a függvényekről (JS parancsok csoportosításának egy módja). Elöljáróban elég annyit megjegyeznünk, hogy a "use strict" egy függvény elején elhelyezve csak az adott függvényen belül engedélyezi a modern üzemmódot. Általában azonban az egész szkriptre szokták használni a "use strict"-et.

````warn header="Győződj meg róla, hogy a \"use strict\" mindig a szkript tetején van!"
Fontos, hogy a `"use strict"` **mindig** a szkript elején legyen, különben a modern mód nem lesz bekapcsolva.

Ebben a példában a `"use strict" hibás elhelyezkedése miatt a modern mód nem lesz bekapcsolva`:

```js no-strict
alert("valami");
// az alábbi "use strict" érvénytelen -- a szkript legtetején kell elhelyezni
"use strict";

// a strict üzemmód nincs engedélyezve
```

A `"use strict"` felé csak kommenteket szabad tenni.
````

```warn header="A `use strict`-et nem lehet utólag kikapcsolni"
Nincsen olyan direktíva, mint például egy "no use strict", ami visszaállítaná a motort az alapértelmezett üzemmódra.

Ha egyszer bekapcsoltuk a strict üzemmódot, nincs visszaút.
```

## Használat a böngésző konzolban

Ha a [fejlesztői konzolt](info:devtools) használod kód futtatására, fontos tudni, hogy alapértelmezetten nem strict üzemmódot használ.

Bizonyos esetekben a "use strict" használatával nem várt eredményeket kaphatunk.

De egyáltalán hogyan használjuk a use strict-et a konzolban?

Először próbáljuk meg a Shift+Enter gombok lenyomásával több sorba írni a kódot, majd a legelejére odatenni a use strict-et. Valahogy így:

```js
'use strict'; <Shift+Enter, hogy új sort kezdjünk>
//  ...a kódod
<Nyomjunk entert a futtatáshoz>
```

Ez a legtöbb böngészőben (mint például a Chrome vagy a Firefox) működik.

Ha ez nem működne (például régi böngészőben), akkor egy megbízható megoldás az alábbi konstrukció használata:

```js
(function() {
  'use strict';

  // ...a futtatandó kódunk...
})()
```

## Használjuk-e a "use strict"-et?

Habár a kérdés egyértelműnek hangzik, nem az.

Okkal gondolhatnánk, hogy mindig érdemes használni a "use strict"-et, de erre nincs szükség.

A modern JavaScript egyes nyelvi elemei, mint az osztály (class) és a modul (module) - ezeket később részletezzük - alapértelmezetten strict üzemmódban futnak, így ezeknek a nyelvi elemeknek a használatakor a "use strict" elhagyható.

**Egyelőre jó, ha használjuk a "use strict"-et, de később, amikor a kódunk modulokból és osztályokból áll, elhagyhatjuk.**

Jelenleg, az alapok miatt jó tudni a `use strict` létezéséről. 

A következő fejezetekben tanulunk majd egy kicsit a nyelvi funckiókról és az új és régi módok közti különbségekről. Szerencsénkre az utóbbiakból nincsen sok, és azok amik vannak azok is csak a mi dolgunkat fogják könnyíteni.

Az ebben a fejezetben lévő példák, ha nincs másként feltüntetve, strict üzemmódot feltételeznek.
