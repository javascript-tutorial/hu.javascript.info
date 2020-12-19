# Fejlesztői Console

A kód hajlamos az hibákra. Te magad is elég nagy valószínűséggel fogsz hibákat ejteni a kódban... Sőt, szinte *biztos* hogy te is fogsz hibákat ejteni, amennyiben ember vagy, és nem csak egy [robot](https://en.wikipedia.org/wiki/Bender_(Futurama)).

De a böngészőben alapból nem látjuk a hibákat. Tehát ha a szkriptben (script) valami probléma van nem fogjuk látni, és nem tudjuk majd mit kéne megjavítani.

Ahoz, hogy lássuk a hibákat, és egyéb hasznos információkat kaphassunk szkriptjeinkről, a böngészők beépítétettek valamit, amit mi "Developer Toolsnak", azaz fejlesztői sgédeszközöknek nevezünk.

A legtöbb fejlesztő a Chrome és a Firefox mellett áll, ha fejlesztésről van szó, mivel azok rendelkeznek a legjobb fejlesztői segédeszközökkel. Egyéb böngészők is kínálnak a Chrome és a Firfoxéhoz hasonló fejlesztői segédeszközöket, de az estek nagy részében, közelről sem olyan jók az előbbieknek. A legtöbb fejlesztőnek van egy kedvenc böngészője, és egy másikra váltanak ha csak egy bizonyos böngészőre exkluzív (browser-specific) problémát találnak.

A fejlesztői segédeszközök szinte nélkülözhetetlenek, tekintve a sok hasznos funkciót amit kínálnak. Először azt fogjukmegtanulni, hogy ezeket az eszközöket hogyan nyissuk meg, hogyan keressünk vele hibákat és futtassunk benne JavaScript parancsokat.

## Google Chrome

Nyisd meg a [bug.html](bug.html) oldalt.

Ezen az oldalon, a látogató szemei elől rejtve található egy hiba, úgyhogy nyissuk meg a fejlesztői segédeszközöket és nézzük meg mi lehet ez a hiba!

Nyomd meg a `F12` gombot, vagy ha Mac rendszert használasz, akkor a `Cmd+Opt+J`-t, hogy megnyisd a fejlesztői segédeszközök ablakot..

A fejlesztői segédeszközök ablak alabból a console résznél fog megnyílni.

Az utóbbinak, ha minden igaz így kell kinéznie:

![chrome](chrome.png)

A fejlesztői segédeszközök ablaknak a pontos kinézete Chrome verziótól függően változhat, de ha minden igaz ehez hasonlóan kéne hogy kinézzen.

- Itt láthatjuk piros színnel jelölve a hibaüzenetet. Ebben az esetben a hiba szerint a szkriptünk tartalmaz egy ismeretlen "lalala" nevű parancsot.
- A jobb oldalon láthatunk egy klikkelhető linket `bug.html:12` néven. Ebben a linkben a `bug.html` a fájlnak a neve ahol a hiba van és a `:12` az annak a sornak a száma amiben a hibát okozó parancs van.

A hibaüzenet alatt található kék `>` szimbólum az a parancssort azaz a "command line"-t jelzi ahova parancsokat írhatunk be, amit aztán az `Enter` billentyű használatatával futtathatunk.

Most, hogy látjuk a hibákat, egyelőre megállhatunk itt. Később még visszatérünk a fejlesztői segédeszközökhöz, és majd még mélyebbre merülünk a hibák elhárításában egy következő fejezetben <info:debugging-chrome>.

```smart header="Multi-line input"
Alapból, ha beírunk egy sor kódot a consoleba és megnyomjuk az Enter gombot, a parancs rögtön le is fut.

Ahoz hogy több sornban írjunk, nyomd meg a `Shift+Enter` gombkombinációt. Ez úton egy nagyabb adag JavaScript kódot is kénylemesen be lehet gépelni.
```

## Firefox, Edge, és egyéb ezekhez hasonló böngészők

A böngészők nagyrészénél az `F12` gomb lenyomásával lehet megnyitni a fejlesztői segédeszközök ablakot.

A kinézetük, felületük és használatuk legtöbbször nagyon hasonló, ezért ha az egyik böngészőjét megtanultad használni, a többi is már viszonylag könnyen fog menni.

## Safari

Safari, a Mac saját (Windows/Linux által nem támogatott) böngészője ezen a téren kicsit kiáll a sorból. Itt először saját magunkan kell bekapcsolnunk a fejlesztői menüt, más néven a "Develop Menü"-ot

Nyisd meg a preferenciák (Preferences) menüt, majd nyomj rá az "Advanced" menüpontra, aminek az alján fogsz látni egy kicsi jelölőnégyzetet, amit be is pipálhatunk.

![safari](safari.png)

Mostmár a `Cmd+Opt+C` gombkombinációval végre megnyithatjuk a consolet! Emellett, még észrevehető változás, hogy egy "Develop" névre hallgató fenti menüpont megjelent. Az utóbbiban még több hasznos funkciót tufunk majd elérni!

## Összesítés

- A fejlesztői segédeszközök sok dologban segítenek. Ezek között van például a hibák megtekintése és javítása, parancsok futtatása és még sok minden más is!
- Windowson a legtöbb böngészőben az `F12`, a Macre való Chromeban a `Cmd+Opt+J`-vel, a Safariban pedig a `Cmd+Opt+C` gombokkal nyithatjuk meg (az utóbbiban először a beállításokban be kell kapcsolni).

Most, hogy a fejlesztői környezetünk készen áll, nekiállhatunk a JavaScript használatához!
