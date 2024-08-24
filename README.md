# STM32H750B-DK_BouncingBall

## UVOD
V sklopu predmeta Organizacija računalnikov smo imeli nalogo, da ustvarimo poljuben projekt na mikrokontrolerju STM32H750B-DK.
Cilj naloge je bil, da ustvarim igrico z uporabo zaslona na dotik mikrokontrolerja. Ustvaril sem Bouncing Ball.
Igra je bila napisana v okolju STM32CubeIDE v C/C++. Za inicializacijo zaslona sem si pomagal z projektom [STM32H750B-DK_BSP_C_Basic](https://github.com/LAPSyLAB/ORLab-STM32H7/tree/main/STM32H750B-DK_BSP_C_Basic).

## ZAGON PROGRAMA
V programskem okolju STM32CubeIDE odpremo workspace in dodamo projekt z File->Open project from File System. V Import source izberemo mapo z projektom.
V Project Explorer-ju izberemo projekt in ga najprej ```zgradimo```, nato ga še zaženemo kot ```1 STM32 C/C++ Application```.

## OPIS IGRE
Princip igre je, da žoga ostane v zraku čim več časa brez, da pade "izven zaslona". Deluje tako, da žoga zaradi gravitacije cel čas pada proti dnu in posledično izven zaslona, zato klikamo po njej, da jo odbiva v zrak.
Žoga se giblje tudi horizontalno, smer je določena naključno. Če zadane levi, desni ali zgornji rob zaslona jo odbije v nasprotno smer, če gre pod spodnji rob zaslona se igra konča. Po končani igri se na zaslon izpiše število odbojev in čas igranja.

## DELOVANJE IGRE
V datoteki ```Main.c``` je vsa programska koda za igro. Najprej so deklarirane vse spremenljivke, metode in strukture, med drugimi tudi struktura ```Ball ball``` od katere je odvisna cela igra. Ima parametra ```x, y```, katera sta koordinati žoge, parametra ```vx, vy``` katera sta gravitacija horizontale in vertikale in še parameter ```radius```. V metodi ```main()```, se inicializira HAL, LCD, zaslon na dotik in žoga. Izrišejo se tudi osnovna navodila z metodo ```Display_InitialContent()``` in žoga z metodo ```DrawBall()```.
V zanki ```while(1)``` se preverja ali je izrisana žoga bila dotaknjena. Če je bila, se začne beležiti čas igranja z uporabo metode ```HAL_GetTick()``` in klicana je metoda ```PlayGame()``` v kateri je vsa logika igre. Najprej se v metodi določijo meje generatorja naključnih števil, kateri se uporablja za določanje horizontalne gravitacije, kar premika žogo levo ali desno. Nato, če se je zgodil dotik zaslona dobimo položaj dotika, z uporabo metode ```BSP_TS_GetState(0, &TS_State)``` iz BSP knjižnice. Parameter ```TS_State``` je struktura, katero uporabljamo za inicializacijo in upravljanje zaslona na dotik. Nato povečamo vertikalno gravitacijo za 1 (```ball.vy += 1```) in posodobimo položaj žoge tako, da prištejemo ```vx``` k ```x``` in ```vy``` k ```y```. Nato počistimo zaslon z metodo ```UTIL_LCD_Clear()``` in znova narišemo števec odbojev in žogo. Sledi preverjanje ali smo žogo dotaknili, če smo jo, spremenimo vertikalno gravitacijo, da jo dvigne (```ball.vy += -10```), horizontalno gravitacijo da jo pomakne v levo oz. desno stran (```ball.vx += random_number```) in števec odbojev se poveča. Preveriti moramo še, če je žoga zadela katerega od robov zaslona. Če je zadela levi, zgornji ali desno rob jo samo odbije v nasprotno smer. Če je zadela spodnji rob se igra konča in se vrnemo v ```main()``` metodo. Izračuna se čas igranja tako, da od trenutnega časa odštejemo začetni čas igranja. Nato stopimo iz zanke in še izpišemo čas igranja in število odbojev na zaslon.

## VIDEO
Kratek posnetek o delovanju [igre]().
