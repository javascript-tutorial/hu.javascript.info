
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
Also, if you're in developing for the browser, then there are other specifications covered in the [second part](info:browser-environment) of the tutorial.
>>>>>>> 97ef86242f9f236b13152e1baf52a55c4db8728a

## Leírások

<<<<<<< HEAD
- A **Mozilla Developer Network (MDN) JavaScript Referencia** egy mélyreható, széleskörű, példákkal illusztrált leírás a nyelv működéséről, a nyelvi elemekről, a beépített függvényekről és a böngészőben elérhető egyéb technológiákról.
=======
- **MDN (Mozilla) JavaScript Reference** is the main manual with examples and other information. It's great to get in-depth information about individual language functions, methods etc.
>>>>>>> 97ef86242f9f236b13152e1baf52a55c4db8728a

    A referencia a <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference> oldalon található.

<<<<<<< HEAD
    Az MDN közvetlen böngészése helyett az esetek többségében célszerűbb egy "MDN [kulcsszó]" alakú keresést indítani, például, ha a `parseInt` függvényről akarunk olvasni: <https://google.com/search?q=MDN+parseInt>.


- **MSDN** – A Microsoft technikai dokumentáció gyűjteménye. Egyebek mellett JavaScript leírások is találhatóak rajta (többnyire JScript megnevezéssel). Internet Explorerrel kapcsolatos kérdések esetén a legjobb forrás. <http://msdn.microsoft.com/>.

    Az MDN-hez hasonlóan, itt is hatékonyabban kereshetünk közvetetten, például "RegExp MSDN" vagy "RegExp MSDN jscript".
=======
Although, it's often best to use an internet search instead. Just use "MDN [term]" in the query, e.g. <https://google.com/search?q=MDN+parseInt> to search for `parseInt` function.
>>>>>>> 97ef86242f9f236b13152e1baf52a55c4db8728a

## Kompatibilitási táblázatok

A JavaScript eszköztára folyamatosan bővül.

Az alábbi linkeken összefoglaló táblázatokat találhatunk az egyes nyelvi funkciók különböző környezetekben való támogatottságáról:

- <http://caniuse.com> - konkrét funkciók szerinti bontás; például a modern titkosítási eljárások támogatottsága: <http://caniuse.com/#feat=cryptography>.
- <https://kangax.github.io/compat-table> - részletes támogatottsági adatok specifikáció verzió szerint.

A mindennapi munkánk során gyakran fogjuk böngészni ezeket az oldalakat. 

Jegyezzük meg őket és ismerkedjünk meg velük alaposan, hogy könnyen el tudjunk igazodni, amikor válaszokat keresünk kérdéseinkre.
