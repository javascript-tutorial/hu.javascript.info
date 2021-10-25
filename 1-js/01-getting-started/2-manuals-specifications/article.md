
# Kézikönyvek és specifikációk

A jelen könyv egy *útmutató*. A célja a JavaScript ismertetése. Az alapok ismeretén túl egyéb segédanyagokra is szükségünk lesz.

## Specifikáció

Az [ECMA-262](https://www.ecma-international.org/publications/standards/Ecma-262.htm) specifikáció a létező legrészletesebb, hivatalos és formális leírása a JavaScript nyelvnek.

Minthogy egy formális specifikációról van szó, elsőre igencsak nehéznek bizonyulhat az olvasása. Ha garantáltan megbízható választ keresünk valamely nyelvi kérdésünkre, a specifikációban érdemes kutakodnunk, de jó, ha tudjuk, hogy nem kimondottan a mindennapi használatra szánták.

Minden évben új ECMAScript verzió jelenik meg. A soronkövetkező verzió aktuális tervezetét a <https://tc39.es/ecma262/> oldalon találjuk.

A legújabb nyelvi lehetőségekről és a szabványossá válás előtt álló, úgynevezett 3-as szintű előterjesztésekről a <https://github.com/tc39/proposals> oldalon tájékozódhatunk.

<<<<<<< HEAD
Böngészoldali programok írásához további specifikációkkal ismerkedhetünk meg a [második részben](info:browser-environment).
=======
Also, if you're developing for the browser, then there are other specifications covered in the [second part](info:browser-environment) of the tutorial.
>>>>>>> 3699f73b4ccb2a57ac5ef990d2687bf31ccf564c

## Leírások

- A **Mozilla Developer Network (MDN) JavaScript Referencia** egy mélyreható, széleskörű, példákkal illusztrált leírás a nyelv működéséről, a nyelvi elemekről, a beépített függvényekről és a böngészőben elérhető egyéb technológiákról.

    A referencia a <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference> oldalon található.

Az MDN közvetlen böngészése helyett az esetek többségében célszerűbb egy "MDN [kulcsszó]" alakú keresést indítani, például, ha a `parseInt` függvényről akarunk olvasni: <https://google.com/search?q=MDN+parseInt>.

## Kompatibilitási táblázatok

A JavaScript eszköztára folyamatosan bővül.

Az alábbi linkeken összefoglaló táblázatokat találhatunk az egyes nyelvi funkciók különböző környezetekben való támogatottságáról:

- <http://caniuse.com> - konkrét funkciók szerinti bontás; például a modern titkosítási eljárások támogatottsága: <http://caniuse.com/#feat=cryptography>.
- <https://kangax.github.io/compat-table> - részletes támogatottsági adatok specifikáció verzió szerint.

A mindennapi munkánk során gyakran fogjuk böngészni ezeket az oldalakat. 

Jegyezzük meg őket és ismerkedjünk meg velük alaposan, hogy könnyen el tudjunk igazodni, amikor válaszokat keresünk kérdéseinkre.
