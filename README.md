Domel Laser Transparency Detector (980 nm)

Naprava meri transmisivnost kosa pri 980 nm in prikaže rezultat na LCD zaslonu ter z barvno signalno lučko (releji).

Statusi:

🟢 OK – transmisija je nad pragom za zeleno (kos ustreza)

🔵 ? – mejno območje (kos je blizu meje / potreben dodatni pregled)

🔴 NOK – transmisija je prenizka (kos ne ustreza)

1) Hiter začetek (Quick Start)

Vklopi napravo.

Po potrebi izvedi kalibracijo (glej poglavje Kalibracija).

Izberi pravilen jarem/kos v meniju (Izbira jarma).

Po potrebi nastavi pragove (BLUE in GREEN) za izbran jarem (Nastavitve pragov).

V načinu RUN odčitaj rezultat:

LCD prikazuje napetost, transmisijo (%) in status (OK / ? / NOK).

Signalna lučka pokaže isto informacijo z barvo.

2) Zaslon v načinu RUN

V načinu RUN se prikazujejo ključni podatki:

U: napetost na vhodu (V)

T: transmisivnost (%)

Status: OK, ?, NOK

dodatno še: A0, D (dark), R (ref), ter pragovi za BLUE/GREEN (odvisno od verzije zaslona)

Če se izpiše CAL NEEDED, je kalibracija neveljavna ali manjkajoča.

3) Upravljanje (enkoder + tipka)

Enkoder ima:

Vrtenje: spreminjanje izbire/vrednosti

Kratek pritisk (Click): potrditev / naslednja izbira

Dolg pritisk ~1 s (Hold): povratek / vstop v kalibracijo (odvisno od menija)

Zelo dolg pritisk ~5 s (Hold 5s): Factory reset (samo v RUN)

Opomba: naprava uporablja filtriranje signala in časovne zakasnitve, zato se LED ne preklaplja “hipno”, ampak kontrolirano.

4) Meniji in navigacija
4.1 RUN → (Click)

Kratek pritisk v RUN odpre meni YOKE (izbira jarma).

4.2 YOKE (izbira jarma)

Vrtenje: izbira jarma (npr. Jarem 758, Jarem 759, …)

Click: prehod v THR (nastavitve pragov)

Hold ~1 s: nazaj v RUN

4.3 THR (nastavitve pragov)

Vrtenje: spreminja trenutno izbrani prag

Click: preklop med nastavitvijo GREEN in BLUE

Hold ~1 s: nazaj v YOKE

Pomembno pravilo:

BLUE mora biti vedno nižji od GREEN.

5) Statusna logika (LED + status na LCD)

Barve so določene glede na transmisivnost T in prage za izbran jarem:

🟢 GREEN / OK: T ≥ GREEN_prag

🔵 BLUE / ?: BLUE_prag ≤ T < GREEN_prag

🔴 RED / NOK: T < BLUE_prag

Histereza in stabilnost

Da se releji in LED ne preklapljajo prehitro, sistem uporablja:

histerezo (majhen pas okoli praga, ki prepreči “cukanje”),

časovno stabilnost (nova barva mora biti stabilna kratek čas),

minimalni čas med preklopi (za varčevanje z releji).

6) Kalibracija (CAL)

Kalibracija določi referenčne točke:

DARK = “tema” (blokiran žarek / minimalen signal)

REF (100%) = prost žarek brez jarma (maksimalen signal)

6.1 Vstop v kalibracijo

V načinu RUN:

Hold ~1 s → vstop v CAL DARK

6.2 CAL DARK (zajem teme)

Blokiraj žarek ali prepreči osvetlitev detektorja.

Na zaslonu preveri stabilen A0.

Click → zajem DARK in prehod v CAL REF

6.3 CAL REF (zajem 100%)

Odstrani jarem/kos (prosta pot žarka).

Na zaslonu preveri stabilen A0.

Click → zajem REF in povratek v RUN

6.4 Preklic kalibracije

Med CAL DARK ali CAL REF:

Hold ~1 s → povratek v RUN brez ponovne kalibracije

7) Shranjevanje nastavitev

Naprava si samodejno shrani (v EEPROM):

izbran jarem,

pragove BLUE/GREEN za posamezni jarem,

kalibracijske vrednosti DARK/REF (če so v programu omogočene).

Shranjevanje je lahko z majhno časovno zakasnitvijo (npr. po 2 s mirovanja), da se EEPROM ne obrablja po nepotrebnem.

8) Tovarniški reset (Factory reset)

V načinu RUN:

Hold 5 s → reset na tovarniške nastavitve (default pragovi + default jarem + default kalibracija, če je tako nastavljeno v kodi)

Na zaslonu se lahko kratko prikaže RESET.

9) Pogoste težave (Troubleshooting)
“CAL NEEDED”

Kalibracija je neveljavna (premalo razlike med DARK in REF) ali še ni izvedena.

Izvedi kalibracijo (poglavje 6).

LED status “skače”

To je običajno znak, da je signal blizu praga.

Povečaj histerezo (če je omogočeno), ali nastavi pragove bolj primerno za ta jarem.

Preveri stabilnost mehanske postavitve (poravnava, vibracije).

Prenizka/ previsoka transmisija

Preveri poravnavo laser–detektor.

Preveri, ali je jarem pravilno v ležišču.

Preveri, ali je optika čista (prah/onesnaženje vpliva na transmisijo).

10) Verzija in spremembe

Manual: v1.0

Naprava/koda: (po potrebi dopolni z verzijo firmware-a)
