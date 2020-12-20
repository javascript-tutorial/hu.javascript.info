# A modern mode, "use strict"

Egy hosszú ideig a JavaScript kompatibilitási hibák nélkül fejlődött. Új dolgok funkciók folyamatosan jöttek be, a régiek viszont sosem változtak.

Ennek nagy előnye volt, hogy a kódot bármikor is írták mindig helytálló maradt, ám viszont azzal hogy a régi dolgok sosem változtak azzal az a nagy baj, hogy bármilyen imperfekciót is ejtettek a JavaScript készítői, az örökre a nyelvben ragadt.

Ez volt a helyzet, míg 2009-ben meg nem jelent az ECMAScript 5 (ES5). Az ES5 sok új funkciót hozott a JS-be és sok régit is megváltoztatott. Ahoz hogy a régi kód továbbá is működőképes maradhasson, ezeknek a változtatásoknak nagy részét alapból kikapcsolták. Ezeket a funciókat egy különleges diretívával kapcsolhattad be, a `"use strict"`-el.

## "use strict"

Ez a direktíva pontosan úgy néz ki mint egy átlagos szöveg: `"use strict"`, vagy `'use strict'`. Mikor ezt a direktívát a szkript tetejére hejezed, akkor az a szkriptet arra utasítja, hogy a "modern módon" működjön.

Példa:

```js
"use strict";

// ez a kód a modern úton fog működni
...
```

Nemsokára külön tanulni fogunk a függvényekről (egy mód parancsok csoportosítására), de előre lefektethetjük, hogy a `"use strict"`-et tudjuk használni függvények elején. Ezzel azt érhetjük el, hogy csak azon a függvényen belül fusson modern módon a kód. De általában az egész szkriptre szokták használni a `"use strict"`-et.

````warn header="Győződj meg róla, hogy a \"use strict\" mindig a szkript tetején van!"
Fontos, hogy a `"use strict"` **mindig** a szkript elején legyen, különben a modern mód nem lesz bekapcsolva.

Ebben a példában a `"use strict" hibás elhelyezkedése miatt a modern mód nem lesz bekapcsolva`:

```js no-strict
alert("some code");
// a "use strict"-et ignorálja a kód, hacsak nem a szkript, vagy egy függvény legelején van.

"use strict";

// a strict mode ki van kapcsolva
```

A `"use strict"` felé csak kommenteket szabad tenni.
````

```warn header="A `use strict`-et nem lehet utólag kikapcsolni"
Nincsen olyasmi direktíva, mint például egy `"no use strict"`, ami visszaállítani a motort a régi viselkedési módra.

Ha egyszer bekapcsoltad a strict modeot, nincs visszaút.
```

## Használat a böngészők konzoljain belül

Ha a [fejlesztői consolet](info:devtools) használod kód futtatására, akkor fontos, hogy az alapból nem használ `strict mode`-ot.

Bizonyos alkalmakkor, amikor a `use strict` különbséget tesz, akkor nem kívánt eredményeket kaphatsz.

De, akkor hogyan is használjuk helyesen a `use strict`-et a consoleban?

Először is, megpróbálhatod a `Shift+Enter` gombok lenyomásával több sorba írni a kódot, majd az egész legetetejére odatenni a `use strict`-et. Az utóbbi valahogy így fog kinézni:

```js
'use strict'; <Shift+Enter, hogy új sort kezdj>
//  ...a kódod
<Nyomd meg az entert a futtatáshoz>
```

Ez a legtöbb böngészőben (mint például a Chrome vagy a Firefox) működik.

Ha esetleg mégse (például egy régi böngészőben), akkor van egy csúnya, de megbízható megoldsé a `use strict` használatára. Egy ilyesmi kód blokkra lesz szükségünk:

```js
(function() {
  'use strict';

  // ...a kód hátralévő része...
})()
```

## Használjuk-e a "use strict"-et?

Ez a kérdés, míg először eléggé egyértelműnek hangzik, a valóságban nem az.

Ugye, azt egyesek azt ajánlanák, hogy használd előszeretettel a `"use strict"`-et ...De tudod mi itt a menő dolog?

A modern JavaScript támogat olyanokat mint például a "class"-ek és a "module"-ok (majd azokat is tanulni fogjuk), amik automatikusan engedélyezik a `"use strict"`-et. Tehát ha ilyenekn vannak a kódunkban, a `"use strict"`-et nyugodtan nélkülözhetjük.

**Tehát egyelőre a `"use strict";` az csak egy kis extra a szkriptjeink elején. Később, amikor a kódunk tele lesz modulokkal és classokkal, már nyugodtan kihagyhatjuk a `"use strict"`-et.**

Jelenleg, az alapok miatt jó tudni a `use strict` létezéséről.

A következő fejezetekben tanulunk majd egy kicsit a nyelvi funckiókról és az új és régi módok közti különbségekről. Szerencsénkre az utóbbiakból nincsen sok, és azok amik vannak azok is csak a mi dolgunkat fogják könnyíteni.

Az ebben a fejezetben lévő példák mind elvárják a "strict" mode használatát, hacsak ennek az állításnak hamisságát nem fejeztük ki előre.
