# STM32H750B-DK_BouncingBall

## UVOD
V sklopu predmeta Organizacija računalnikov smo imeli nalogo, da ustvarimo poljuben projekt na mikrokontrolerju STM32H750B-DK.
Cilj naloge je bil, da ustvarim igrico z uporabo zaslona na dotik mikrokontrolerja. Ustvaril sem Bouncing Ball.
Igra je bila napisana v okolu STM32CubeIDE v C/C++. Za inicializacijo zaslona sem si pomagal z projektom [STM32H750B-DK_BSP_C_Basic](https://github.com/LAPSyLAB/ORLab-STM32H7/tree/main/STM32H750B-DK_BSP_C_Basic).

## ZAGON PROGRAMA
V programskem okolju STM32CubeIDE odpremo workspace in dodamo projekt z File->Open project from File System. V Import source izberemo mapo z projektom.
V Project Explorer-ju izberemo projekt in ga najprej ```zgradimo```, nato ga še zaženemo kot ```1 STM32 C/C++ Application```.

## OPIS IGRE
Princip igre je, da žoga ostane v zraku čim več časa brez, da pade "izven zaslona". Deluje tako, da žoga zaradi gravitacije cel čas pada proti dnu in posledično izven zaslona, zato klikamo po njej, da jo odbije v zrak.
Žoga se giblje tudi horizontalno, smer je določena naključno. Če zadane levi, desni ali zgornji rob zaslona jo odbije v nasprotno smer, če gre pod spodnji rob zaslona se igra konča. Po končani igri se na zaslon izpiše število odbojev in čas igranja.

## DELOVANJE IGRE

## VIDEO
