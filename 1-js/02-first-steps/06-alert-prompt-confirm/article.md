# Interakciók: alert, prompt, confirm

Mivel a böngészőt fogjuk használni bemutató környezetünkként, nézzünk meg néhány függvényt a felhasználóval való interakcióhoz: `alert`, `prompt`, és `confirm`.

## alert

Már korábban láthattuk. Megmutatja az üzenetet, és várakozik addig, míg a felhasználó rányom, hogy "OK".

Például:

```js run
alert("Hello");
```

Az üzenetet tartalmazó kisablakot *modal window*-nak nevezzük. A szó "modal" azt jelenti, hogy a látogató nem tud az oldalon lévő többi dolgot elérni, megnyomni más gombokat, stb, amíg nem foglalkoztak az ablakkal. Ebben az esetben -- addig míg nincs megnyomva az "OK".

## prompt

A `prompt` függvénynek két paramétere lehet:

```js no-beautify
result = prompt(title, [default]);
```

Megjelenik egy modális ablak szöveges üzenettel, egy beviteli mező a látogató számára, és az OK/Mégse gombok.

`title`
: Az üzenet a látogató részére.

`default`
: Egy opcionális másodlagos paraméter, a beviteli mező kezdő értéke.

```smart header="Szögletes zárójelek a szintaxisban `[...]`"
A fenti szintaxisban a `default` körüli szögletes zárójelek azt jelentik, hogy a paraméter opcionális, és nem kötelező.
```

A látogató beírhat valamit a prompt beviteli mezőbe, és megnyomhatja az OK gombot. Ezután megkapjuk ezt a szöveget az `eredményben`. Vagy megszakíthatják a bevitelt a Mégse gomb megnyomásával vagy a `key:Esc` billentyű megnyomásával, ekkor a "null" értéket kapjuk az `eredményként`.

A `prompt` hívása a beviteli mező szövegét adja vissza, vagy a `null` értéket adja vissza, ha megszakították.

Például:

```js run
let age = prompt('Hány éves vagy?', 100);

alert(`Te ${age} éves vagy!`); // Te 100 éves vagy!
```

````warn header="Az IE-ben: mindig szükséges a `default` rész"
A második paraméter opcionális, de ha nem látjuk el, az Internet Explorer beszúrja az `"undefined"` szöveget a promptba.

Futtasd az IE-ben ezt a kódot:

```js run
let test = prompt("Test");
```

Tehát, hogy a promptok jól nézzenek ki az IE-ben, javasoljuk, hogy mindig adja meg a második paramétert.

```js run
let test = prompt("Test", ''); // <-- for IE
```
````

## confirm

A szintaxis:

```js
result = confirm(question);
```

A `confirm` funkció egy modális ablakot jelenít meg egy `question` és két gombbal : OK és Mégse.

Az eredmény `true`, amennyiben az OK-ra nyom, minden más esetben pedig `false`.

Például:

```js run
let isBoss = confirm("Te vagy a főnök?");

alert( isBoss ); // igaz, ha OK gombot nyomta
```

## Összegzés

Három böngésző-specifikus függvényt ismertettünk a látogatókkal való interakció érdekében:

`alert`
: megjelenít egy üzenetet.

`prompt`
: megjelenít egy üzenetet, és kér egy bemenetet a felhasználótól. Ez visszaadja a bemenetet, vagy ha rányom, hogy Mégse vagy `key:Esc` gombot használja, az érték `null`.

`confirm`
: megjelenít egy üzenetet, és felhasználótól várja, hogy "OK" vagy "Mégse". Visszaadja `true` értéket OK, és `false` amennyiben Mégse vagy `key:Esc` gombot használja.

Mindezek a módszerek modálisak: szüneteltetik a szkript végrehajtását, és nem teszik lehetővé a látogató számára, hogy interakcióba lépjen az oldal többi részével, amíg az ablakot el nem zárják.

Az összes fenti módszernek két korlátozása van:

1. A modális ablak pontos helyét a böngésző határozza meg. Általában a központban van.
2. Az ablak pontos megjelenése a böngészőtől is függ. Nem tudjuk módosítani.

Ez az egyszerűség ára. Vannak más módok is a szebb ablakok megjelenítésére és a látogatóval való gazdagabb interakcióra, de ha a "harangok és sípok" nem sokat számítanak, ezek a módszerek jól működnek.
