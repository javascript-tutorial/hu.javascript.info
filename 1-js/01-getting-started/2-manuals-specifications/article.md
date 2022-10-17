
# Kézikönyvek és specifikációk

<<<<<<< HEAD
A jelen könyv egy *útmutató*. A célja a JavaScript ismertetése. Az alapok ismeretén túl egyéb segédanyagokra is szükségünk lesz.
=======
This book is a *tutorial*. It aims to help you gradually learn the language. But once you're familiar with the basics, you'll need other resources.
>>>>>>> bf7d8bb1af3b416d393af1c15b03cb1352da1f9c

## Specifikáció

Az [ECMA-262](https://www.ecma-international.org/publications/standards/Ecma-262.htm) specifikáció a létező legrészletesebb, hivatalos és formális leírása a JavaScript nyelvnek.

Minthogy egy formális specifikációról van szó, elsőre igencsak nehéznek bizonyulhat az olvasása. Ha garantáltan megbízható választ keresünk valamely nyelvi kérdésünkre, a specifikációban érdemes kutakodnunk, de jó, ha tudjuk, hogy nem kimondottan a mindennapi használatra szánták.

<<<<<<< HEAD
Minden évben új ECMAScript verzió jelenik meg. A soronkövetkező verzió aktuális tervezetét a <https://tc39.es/ecma262/> oldalon találjuk.
=======
A new specification version is released every year. Between these releases, the latest specification draft is at <https://tc39.es/ecma262/>.
>>>>>>> bf7d8bb1af3b416d393af1c15b03cb1352da1f9c

A legújabb nyelvi lehetőségekről és a szabványossá válás előtt álló, úgynevezett 3-as szintű előterjesztésekről a <https://github.com/tc39/proposals> oldalon tájékozódhatunk.

<<<<<<< HEAD
Böngészoldali programok írásához további specifikációkkal ismerkedhetünk meg a [második részben](info:browser-environment).
=======
Also, if you're developing for the browser, then there are other specifications covered in the [second part](info:browser-environment) of the tutorial.
>>>>>>> bf7d8bb1af3b416d393af1c15b03cb1352da1f9c

## Leírások

- A **Mozilla Developer Network (MDN) JavaScript Referencia** egy mélyreható, széleskörű, példákkal illusztrált leírás a nyelv működéséről, a nyelvi elemekről, a beépített függvényekről és a böngészőben elérhető egyéb technológiákról.

<<<<<<< HEAD
    A referencia a <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference> oldalon található.

Az MDN közvetlen böngészése helyett az esetek többségében célszerűbb egy "MDN [kulcsszó]" alakú keresést indítani, például, ha a `parseInt` függvényről akarunk olvasni: <https://google.com/search?q=MDN+parseInt>.
=======
    You can find it at <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference>.

Although, it's often best to use an internet search instead. Just use "MDN [term]" in the query, e.g. <https://google.com/search?q=MDN+parseInt> to search for the `parseInt` function.
>>>>>>> bf7d8bb1af3b416d393af1c15b03cb1352da1f9c

## Kompatibilitási táblázatok

A JavaScript eszköztára folyamatosan bővül.

Az alábbi linkeken összefoglaló táblázatokat találhatunk az egyes nyelvi funkciók különböző környezetekben való támogatottságáról:

<<<<<<< HEAD
- <http://caniuse.com> - konkrét funkciók szerinti bontás; például a modern titkosítási eljárások támogatottsága: <http://caniuse.com/#feat=cryptography>.
- <https://kangax.github.io/compat-table> - részletes támogatottsági adatok specifikáció verzió szerint.

A mindennapi munkánk során gyakran fogjuk böngészni ezeket az oldalakat. 
=======
- <https://caniuse.com> - per-feature tables of support, e.g. to see which engines support modern cryptography functions: <https://caniuse.com/#feat=cryptography>.
- <https://kangax.github.io/compat-table> - a table with language features and engines that support those or don't support.

All these resources are useful in real-life development, as they contain valuable information about language details, their support, etc.
>>>>>>> bf7d8bb1af3b416d393af1c15b03cb1352da1f9c

Jegyezzük meg őket és ismerkedjünk meg velük alaposan, hogy könnyen el tudjunk igazodni, amikor válaszokat keresünk kérdéseinkre.
