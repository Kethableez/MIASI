# Notatki na egzamin

## Logika
Jest to nauka argumentowalna oraz jedna z głównych dziedzin matematyki która służy do matematycznego opisu rzeczywistości.

**Logika zdań** - zbiór praw logicznych, który nadaje logiczny stan dla każdego zdania i powala na wnioskowanie o prawdziwości danego zdania.

**Logika modalna** - jest to klasyczna logika zdań określona matematycznie.

## Logika modalna
**Wyrażenie atomowe** - jest to wyrażenie którego nie można podzielić na inne wyrażenia.  
Generowanie formuł na podstawie reguł:
* **S1:** - każde wyrażenie $p \in WA$ jest formułą
* **S2:** - jeśli $p$ i $q$ są formułami to $p \land q$ i $\lnot p$ też są formułami 

### Podstawowe relacje logiczne:
| Relacja | Symbol | Zapis |
| - | - | - |
Koniunkcja | $ \land $ | $ p \land q $
Negacja | $ \lnot $ | $ \lnot p $
Alternatywa | $ \lor $ | $ p \lor q $
Implikacja | $ \implies $ | $ p \implies q $
Równoważność | $ \iff $ | $ p \iff q $

## Czas:
Jest to nieprzestrzenne kontinuum, w którym zdarzenia zachodzą w nieodwracalnej kolejności od przeszłości, przez teraźniejszość do przyszłości.

* **Ciągły** - dla każdych dwóch momentów istnieje pewien moment między nimi.

* **Dyskretny** - istnieją dwa takie momenty, że nie istnieje żaden moment między nimi.

* **Lewostronnie skończony** - przeszłość jest ograniczona do pewnego momentu.

* **Prawostronnie skończony** - przyszłość jest ograniczona do pewnego momentu.

* **Obustronnie skończony** - przyszłość oraz przeszłość są ograniczone do pewnego momentu.

* **Nieskończony** - przeszłość oraz przeszłość są nieograniczone.

* **Liniowy** - istnieje tylko jeden wariant przepływu czasu

* **Rozgałęziony** - istnieją róœne warianty przepływu czasu które mają wspólą część ze sobą

* **Punktowy** - struktura czasowa składa się tylko z punktów.

* **Przedziałowy** - struktura czasowa składa się tylko z przedziałów.

## Logika temporalna:
Pozwala na wnioskowanie z uwzględnieniem czasu. Operuje na wyrażeniach logiki modalnej.

* **LTL** *(Linear Temporal Logic)* - dyskretny, lewostronnie skończony, liniowy, punktowy

* **CTL** *(Computation Tree Logic)* - czas: dyskretny, lewostronnie skończony, rozgałęziony (lewostronnie liniowy), punktowy

* **RTCTL** *(Real-Time Computation Tree Logic)* - wersja CTL, gdzie wartości czasu dane są ilościowo jako stałe

* **PRTCTL** *(Parametrised Real-Time Computation Tree Logic)* - wersja CTL, gdzie wartości czasu dane są ilościowo jako zmienne

* **TCTL** *(Timed Computation Tree Logic)* - wersja CTL, gdzie wartości czasu dane są ilościowo jako stałe

* **CTL*** *(Full Branching Computation Tree Logic)* - wersja CTL o większej ekspresji, zawierającej też ekspresję LTL

* **ITL** *(Interval Temporal Logic)* - dyskretny, skończony lub nieskończony, liniowy, przedziałowy

* **DC** *(Duration Calculus)* - wersja ITL, gdzie mierzy się prawdziwość wyrażenia w odcinku czasu

**Logika temporalna** ma swoje zastosowanie głównie w modelowaniu oraz weryfikacji systemów współbieżnych oraz reaktywnych.

## Linear Temporal Logic *(LTL)*

* Czas jest punktowy, liniowy, lewostronnie skończony
* Służy do opisu i analizy deterministycznych algorytmów oraz właściwości niedeterministycznych algorytmów lub gdzie nie ma różnych wariantów przepływu czasu.

### Generowanie formuł na podstawie reguł:
* **S1:** - każde wyrażenie $p \in WA$ jest formułą
* **S2:** - jeśli $p$ i $q$ są formułami to $p \land q$ i $\lnot p$ też są formułami
* **S3:** - jeśli $p$ i $q$ są formułami to $pUq$ i $Xp$ też są formułami

**Operatory temporalne** pozwalają na przypisywanie wyrażeniom wartości w strukturze czasowej.

### Podstawowe operatory temporalne:
* **U** *(dopóki)* - q jest prawdziwe w pewnym momencie, jeśli to moment przyszły to w każdym wcześniejszym momencie p jest prawdziwe.
* **X** *(następnie)* - p jest prawdwziwe w następnym momencie.
* **G** *(zawsze)* - p jest prawdziwe w każdym momencie.
* **F** *(kiedyś)* - p jest prawdziwe w pewnym momencie.

### Dualność operatorów:
* $ Gp \iff \lnot F \lnot p $
* $ Fp \iff \lnot G \lnot p $
* $ X \lnot p \iff \lnot Xp $

### Dualność par operatorów:
* $GF \lnot p \iff \lnot FGp$
* $FG \lnot p \iff \lnot GFp$

### Przestawność operatora X
* $GXp \iff XGp $
* $FXp \iff XFp $

## Computation Tree Logic *(CTL)*

* Czas jest punktowy, rozgałęziony (lewostronnie), lewostronnie skończony
* Służy do opisu i analizy deterministycznych i niedeterministycznych algorytmów oraz ich własności a także wykorzystuje się go tam gdzie mogą być różne warianty przepływu czasu.

### Generowanie formuł na podstawie reguł:
* **S1:** - każde wyrażenie $p \in WA$ jest formułą
* **S2:** - jeśli $p$ i $q$ są formułami to $p \land q$ i $\lnot p$ też są formułami
* **S3:** - jeśli $p$ i $q$ są formułami to $A(pUq)$, $E(pUq)$, $AXp$ i $EXp$ też są formułami:
    * $A(pUq)$ - dla każdej ścieżki...
    * $E(pUq)$ - dla pewnej ścieżki...
    * $AXp$ - jeśli dla każdej ścieżki...
    * $EXp$ - jeśli dla pewnej ścieżki...

**Operatory temporalne** pozwalają na przypisywanie wyrażeniom wartości w strukturze czasowej.

### Podstawowe operatory temporalne:
* **U** *(dopóki)* - q jest prawdziwe w pewnym momencie, jeśli to moment przyszły to w każdym wcześniejszym momencie p jest prawdziwe.
* **X** *(następnie)* - p jest prawdwziwe w następnym momencie.
* **A** *(zawsze)* - p jest prawdziwe dla każdej ścieżki
* **E** *(kiedyś)* - p jest prawdziwe dla pewnej ścieżki

## Real-Time Computation Tree Logic *(RTCTL)*

* Czas jest punktowy, rozgałęziony (lewostronnie), lewostronnie skończony, określony ilościowo
* Służy do opisu i analizy deterministycznych i niedeterministycznych algorytmów oraz ich własności a także wykorzystuje się go tam gdzie mogą być różne warianty przepływu czasu, dodatkowo słuzy do opisu zależności czasowych nie tylko jakościowo

### Generowanie formuł na podstawie reguł:
* **S1:** - każde wyrażenie $p \in WA$ jest formułą
* **S2:** - jeśli $p$ i $q$ są formułami to $p \land q$ i $\lnot p$ też są formułami
* **S3:** - jeśli $p$ i $q$ są formułami to $A(pUq)$, $E(pUq)$, $AXp$ i $EXp$ też są formułami:
    * $A(pUq)$ - dla każdej ścieżki...
    * $E(pUq)$ - dla pewnej ścieżki...
    * $AXp$ - jeśli dla każdej ścieżki...
    * $EXp$ - jeśli dla pewnej ścieżki...
* **S4:** - jeśli $p$ i $q$ są formułami $m \in N_{ \geq 0} $ to $A(pU^{\leq m}q)$ i $E(pU^{\leq m}q)$ (dla każdej ścieżki, dla pewnej ściezki)

*Operatory temporalne F i G są z ograniczeniem czasowym*

## Parametrized Real-Time Computation Tree Logic *(PRTCTL)*

* Czas jest punktowy, rozgałęziony (lewostronnie), lewostronnie skończony, określony ilościowo
* Służy do określenia zależności czasowych: czasowo (jak w CTL), ilościowo dla ustalonych ograniczeń (jak w RTCTL) oraz ilościowo dla zmiennych ograniczeń

## Timed Computation Tree Logic *(TCTL)*

* Czas jest punktowy, rozgałęziony (lewostronnie), lewostronnie skończony
* Służy do określenia zależności czasowych: czasowo (jak w CTL), ilościowo dla ustalonych ograniczeń (jak w RTCTL)

### Generowanie formuł na podstawie reguł:
* **S1:** - każde wyrażenie $p \in WA$ jest formułą
* **S2:** - jeśli $p$ i $q$ są formułami to $p \land q$ i $\lnot p$ też są formułami
* **S3:** - jeśli $p$ i $q$ są formułami to $A(pUq)$, $E(pUq)$, $AXp$ i $EXp$ też są formułami:
    * $A(pUq)$ - dla każdej ścieżki...
    * $E(pUq)$ - dla pewnej ścieżki...
    * $AXp$ - jeśli dla każdej ścieżki...
    * $EXp$ - jeśli dla pewnej ścieżki...
* **S4:** - jeśli $p$ i $q$ są formułami $m \in N_{ \geq 0} $ to $A(pU^{\leq m}q)$ i $E(pU^{\leq m}q)$ też są formułami (dla każdej ścieżki, dla pewnej ściezki)

*Operatory temporalne F i G są z ograniczeniem czasowym*

## Full Branching Computation Tree Logic *(CTL)* *

* Rozszerzenie logiki CTL która łączy ekspresję języków LTL i CTL
* Czas jest punktowy, rozgałęziony (lewostronnie), lewostronnie skończony
* Zastosowanie jak w CTL oraz LTL

### Generowanie formuł na podstawie reguł:
* **S1:** - każde wyrażenie $p \in WA$ jest formułą
* **S2:** - jeśli $p$ i $q$ są formułami to $p \land q$ i $\lnot p$ też są formułami
* **S3:** - jeśli $p$ i $q$ są formułami to $Ap$ i $Ep$ są formułami


## Modelowa weryfikacja systemu:
**Program współbieżny** - to program który składa się z procesów gdzie:
* procesy wykonywane są w tym samym momencie
* procesy mogą współdzielić pewne zasoby
* procesy mogą wzajemnie oddziaływać na siebie

### Typowe własności:
* **Bezpieczeństwo** - q jesdt spełnione w każdym momencie: $ \phi = Gq $
* **Osiągalność** - q jest spełnione w pewnym momencie: $ \phi = Fq $
* **Odpowiedź** - q jest spełnione od czasu do czasu: $ \phi = GFq $
* **Trwałość** - od pewnego momentu q jest spełnione w każdym momencie: $ \phi = FGq $
* **Żywotność** - q jest osiągalne jako skutek p : $ \phi = G(p \implies Fq) $

**Automat skończenie stanowy** - to abstrakcyjna maszyna stanowa któ©a składa się ze skończonej liczby stanów oraz przejść między nimi. Ma stany początkowe, może mieć stany końcowe, a przejścia między stanami odpalane są deterministycznie.

Automat $ A = \{ \sum, S, S_0 \rho, F \} $ definiowany jest przez:
* $\sum$ - alfabet jako zbiór stanów programu
* $S$ - zbiór stanów automatu
* $S_0$ - zbiór stanów początkowych
* $\rho$ - funkcja przejścia
* $F$ - zbiór stanów końcowych

**Dane wejściowe** - to własności które muszą być spełnione przez system, dane jako formuły logiki termporalnej.
**Dane wyjściowe** - to odpowiedź czy system spełnia dane właściwości.

### Najważniejsze własności do weryfikacji:
* Osiągalność - pożądany stan systemu w końcu zostanie osiągnięty
    * **LTL:** $Fp$
    * **CTL:** $EFp$
* Bezpieczeństwo - niechciany stan systemu nigdy nie zostanie osiągnięty
    * **LTL:** $G \lnot p$
    * **CTL:** $AG \lnot p$

## Temporalna baza danych
Jest to baza danych która zawiera informacje o czasie ważności danych i niekiedy o czasie transferu danych.

* Zwykle przechowuje dane jak nietemporalna baza danych
* Przechowuje czas ważności dla danych
* może przechowywać znaczniki czasu dla każdej akcji wykonanej w bazie do zapamiętania kiedy dana akcja miała miejsce
* Może umożliwiśc dostęp do danych używają temporalnego języka w zapytaniach

### Podział
* Historyczna - przechowuje tylko czas ważności, nie przechowuje znaczników czasu
* Bitemporalna - przechowuje czas ważności i znaczniki czasu.

### Czas w TBD
* Dyskretny
* Gęsty
* Ciągły

Możemy definiować w logice temporalnej reguły działania systemu zarządzania bazą danych oraz sam język zapytań.

Przykładami zastosowania mogą być:
* Zarządzanie archiwami biurowymi/biznesowymi
* Zarządzanie danymi finansowymi, medycznymi
* Zarządzanie systemami rezerwacji biletów, pokoi hotelowych,
* Zarządzanie systemem komputerowym

Ogólne zastosowania:
* Aby pamiętać akcje wykonywane w bazie,
* Aby pamiętać zmiany dokonane na danych
* Aby sprawdzać właściwości czasowe danych

### Logika LTL-
Jest to logika temporalna LTL dla czasu przeszłego używająca operatorów temporalnych: $U^- X^- G^- F^-$