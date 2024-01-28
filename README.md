# Podstawy automatyki - notatki na egzamin
by Maciej, 2023-01-04, v2
Część obrazków ukradnięte z prezentacji dr inż. Nowaka, prof. Urbaniaka, materiałów z Podstawy Automatyki z AGH, czy też z notatek innych osób

Przypomnienie greckiego alfabetu:
$\omega$ - omega, $\phi$ - phi, $\xi$ - ksi, $\kappa$ - kappa, $\tau$ - tau

**Transformacja Laplace'a** jest metodą przejścia z funkcji f(t) w dziedzinie czasu na funkcji F(s) w dziedzinie operatorowej. Transformata Laplace'a to funkcja F(s) po przeprowadzeniu transformacji z f(t). 

**Transmitancja operatorowa** to stosunek transformaty Laplace’a sygnału wyjściowego (odpowiedzi) do transformaty Laplace’a sygnału wejściowego (wymuszenia) przy zerowych warunkach początkowych.
$$G(s) = \frac{Y(s)}{X(s)}$$gdzie X(s) to sygnał wejściowy, G(s) to transmitancja badanego obiektu, Y(s) to sygnał wyjściowy. 

Transmitancję operatorową możemy zastosować dla układów opisanych liniowymi równaniami różniczkowymi. $Y(s)$ oraz $X(s)$ przyjmują wtedy postać wielomianów zmiennej s.
$$G(s) = \frac{b_ms^m + b_{m-1}s^{m-1} + \ldots  + b_1s}{a_ns^n + a_{n-1}s^{n-1} + \ldots  + a_1s}$$

W układzie realizowalnym fizycznie stopień $n$ mianownika (wielomianu wejściowego $X(s)$), musi być większy lub równy od stopnia $m$ licznika (wielomianu wyjściowego $Y(s)$).
$$stopień_{mianownik} \ge stopień_{licznik}$$

---

**Charakterystyka czasowa** to przebieg czasowy wielkości wyjściowej wywołany danym sygnałem wejściowym (wymuszeniem). Rozróżniamy dwie charakterystyki czasowe - skokową oraz impulsową.

Do wyznaczenia charakterystyk czasowych posłużymy się definicją transmitancji operatorowej:
$$Y(s) = X(s) \cdot G(s)$$
Gdzie X(s) będzie stanowił sygnał wejściowy w postaci charakterystyki skokowej lub impulsowej.

---

**Charakterystyka skokowa $h(t)$** to odpowiedź układu na wymuszenie w postaci skoku jednostkowego $1(t)$ przy zerowych warunkach początkowych. 

$1(t)$ przyjmuje wartość 0 dla $t < 0$ oraz 1 dla $t \ge 0$.
Transformata Laplace'a dla 1(t) wynosi $1(s) = \frac{1}{s}$
$$Y(s) = \frac{G(s)}{s} \implies y(t) = \int_0^t g(\tau) d\tau$$
Y(s), y(t) oznacza charakterystykę skokową h(t), G(s) oznacza transmitancję układu.

Charakterystyka skokowa stanowi tym samym całkę transmitancji operatorowej obiektu po czasie.

---

**Charakterystyka impulsowa $g(t)$** to odpowiedź układu na wymuszenie w postaci delty Diraca $\delta(t)$ przy zerowych warunkach początkowych. 

$\delta(t)$ przyjmuje wartość $\infty$ dla $t=0$ oraz 0 dla pozostałych wartości.
Transformata Laplace'a $\delta(t)$ wynosi $\delta(t) = 1$. Przyjmuje się również, że całka delty Diraca wynosi 1.  

$$Y(s) = G(s) \implies y(t) = g(t)$$
Y(s), y(t) oznacza charakterystykę impulsową g(t), G(s) oznacza transmitancję układu.

Znajomość odpowiedzi impulsowej pozwala przewidzieć odpowiedź układu na każde inne pobudzenie.

---

**Odpowiedź impulsowa jest pochodną odpowiedzi skokowej.**

---


**Transmitancja widmowa** układu to stosunek (w stanie ustalonym) wartości zespolonej sygnału wyjściowego (odpowiedzi) do wartości zespolonej sygnału wejściowego (wymuszenia), przy wymuszeniu sinusoidalnym.

Korzystamy z podstawienia $s = j\omega$:
$$G(j\omega) = \frac{Y(j\omega)}{X(j\omega)}$$
**Wyjaśnienie:**
Sinusoidalny sygnał wejściowy można opisać jako:
$$x(t) = A_x(\omega)e^{j\omega t}$$
Odpowiedź na sinusoidalny sygnał wyjściowy można opisać jako:
$$y(t) = A_y(\omega)e^{j\omega t + j\phi(\omega) }$$
Gdzie $A(\omega)$ oznacza amplitudę, a $\phi(\omega)$ oznacza przesunięcie fazowe. Obie wartości są zależne od pulsacji $\omega$.

Transmitancję widmową możemy tym samym zapisać:
$$G(j\omega) = \frac{A_y(\omega) \cdot e^{j\omega t} \cdot e^{j\phi(\omega) }}{A_x(\omega) \cdot e^{j\omega t}}$$
Po skróceniu $e^{j\omega t}$ oraz przeniesieniu $e^{j \phi(\omega)}$ poza licznik:
$$G(j\omega) = \frac{A_y(\omega)}{A_x(\omega)} \cdot e^{j\phi(\omega)}$$
Transmitancja widmowa tym samym jest wektorem, którego moduł oznacza stosunek amplitudy sygnału wyjściowego do sygnału wejściowego, a argument oznacza przesunięcie fazowe. 

**Przypomnienie z algebry liniowej:** 
Moduł na płaszczyźnie zespolonej to odległość punktu $x + yj$ od $0 + 0j$ (vide twierdzenie Pitagorasa). Argument to miara kąta pomiędzy osią rzeczywistą dodatnią (kreska od środka w prawo) a wektorem wodzącym (kreska od środka do punktu).

Liczbę zespoloną możemy zapisać nie tylko jako $x + yj$, ale także jako $e^{j \cdot \phi}$, gdzie $\phi$ stanowi kąt. $$e^{j \cdot \phi} = \cos \phi + j \cdot \sin \phi$$
Moduł takiej liczby wynosi 1 (vide jedynka trygonometryczna). Z tego powodu $e^{j\phi(\omega)}$ określa nam kąt, a $\frac{A_y(\omega)}{A_x(\omega)}$ określa odległość od punktu $0 + 0j$.

**Przekształcenie analityczne:**

Podstawiając $s = j\omega$ zademonstruję na przykładzie:

$$G(s) = \frac{1}{Ts + 1} \implies G(j\omega) = \frac{1}{1 + j\omega T}$$
A następnie pozbywamy się j z mianownika:
$$G(j\omega) = \frac{1}{1 + j\omega T} \cdot \frac{1 - j\omega T}{1 - j\omega T}$$
Po przekształceniach otrzymujemy:
$$G(j\omega) = \frac{1}{1 + \omega^2T^2} + j\frac{-\omega T}{1 + \omega^2 T^2}$$
Współczynnik przy części rzeczywistej to $P(\omega)$, przy części urojonej to $Q(\omega)$.

---

Charakterystyki częstotliwościowe:

**Charakterystyka amplitudowo-fazowa** (Nyquist'a) układu to wykres transmitancji widmowej na płaszczyźnie zespolonej (Gaussa). Wyznaczamy ją dla wartości pulsacji $\omega$ od $0$ do $\infty$. Na osi X znajduje się część rzeczywista liczby, a na osi Y znajduje się część urojona.

Część rzeczywistą (oś X) $Re(G(j\omega))$ zwyczajowo oznaczamy jako $P(\omega)$, natomiast część urojoną (oś Y) $Im(G(j\omega))$ zwyczajowo oznaczamy jako $Q(\omega)$.

**Charakterystyka amplitudowa** układu to wykres modułu transmitancji widmowej w funkcji pulsacji $\omega$.
$$X = \omega, Y = A(\omega)$$
**Charakterystyka fazowa** układu to wykres argumentu transmitancji widmowej w funkcji pulsacji $\omega$.$$X = \omega, Y =  \phi(\omega)$$
**Logarytmiczna charakterystyka amplitudowa** (1/2 charakterystyki Bodego):
$$X = \log_{10} \omega, Y = 20 \log_{10} A(\omega)$$
Po wprowadzeniu stałej $20$ oś Y wykorzystuje jednostkę decybeli $dB$.  

**Logarytmiczna charakterystyka fazowa** (2/2 charakterystyki Bodego):
$$X = \log_{10} \omega, Y = \phi(\omega)$$

---

**Człony układów sterowania** 

![[Pasted image 20230104005216.png]]

**Wzory**

Uwaga - pominąłem równania różniczkowe modelujące człony w domenie czasu. Pominąłem również jakieś pośrednie wzory, które doprowadzają nas do docelowej postaci transmitancji operatorowej obiektu.

Wykresy znajdują się na końcu pliku.

Sposób na zapamiętanie wzorów transmitancji operatorowej większości członów:

**Obiekty proporcjonalne:** $G(s) = k$
**Obiekty całkujące** $G(s) = \frac{k}{s}$
**Obiekty różniczkujące** $G(s) = k \cdot s$

Wzory przedstawiają obiekty idealne. W obiektach rzeczywistych występuje inercja, którą wprowadzamy dzieląc przez $1 + Ts$. Dla inercji II rzędu dzielimy przez $(1 + T_1s)(1 + T_2s).$

Przykładowo, obiekt całkujący rzeczywisty (czyli z inercją I rzędu):
$$G(s) = \frac{k}{s} \cdot \frac{1}{1 + Ts} = \frac{k}{s(1 + Ts)}$$
W obiektach całkujących możemy wprowadzić określenie $T_i = \frac{1}{k}$, które określa dla którego X wykres charakterystyki skokowej przyjmie wartość 1: $h(T_i) = 1$. 
Obiektu różniczkującego idealnego nie da się zrealizować fizycznie - stopień wielomianu $ks$ ma większy stopień w liczniku niż w mianowniku - $\frac{ks}{1}$

**Człon opóźniający** przyjmuje wzór: 
$$G(s) = ke^{-sT}$$Na wyjściu $y(t)$ powtarza sygnał wejściowy $x(t)$ opóźniony o stałą wartość T. 
Wzór w dziedzinie czasu: $y(t) = k \cdot x(t - T)$

**Człon oscylacyjny II rzędu** przyjmuje wzór: 
$$G(s) = k \cdot\frac{\omega^2}{s^2 + 2s\omega \cdot \xi + \omega^2}$$
$\omega$ to pulsacja oscylacji własnych
$\xi$ to względny współczynnik tłumienia w zakresie $0 < \xi < 1$

---
**Przykłady:**

**Człon proporcjonalny:** dzielnik napięcia, dźwignia
**Człon inercyjny I rzędu:** układ cewka rezystor (czwórnik RC), wypływ cieczy ze zbiornika, wzmacniacz rzeczywisty
**Człon inercyjny II rzędu:** wielokrążek, podwójny czwórnik RC
**Człon całkujący idealny:** idealny kondensator
**Człon całkujący rzeczywisty:** rzeczywisty kondensator
**Człon różniczkujący idealny:** -
**Człon różniczkujący rzeczywisty:** tłumik hydrauliczny, cewka indukcyjna, tarcie mechaniczne
**Człon opóźniający:** taśma podajnikowa, transporter taśmowy
**Człon oscylacyjny:** siłownik pneumatyczny, wahadło

---

**Schemat układu regulacji**

**Układ otwarty**

![[Pasted image 20230103203520.png]]


**Układ zamknięty**

![[Pasted image 20230103203528.png]]

**Uchyb regulacji** to różnica między wartością zadaną sygnału a wartością sygnału wyjściowego.
$$e(t) = x(t) - y(t)$$
**Zadaniem układu regulacji** jest minimalizacja wartości sygnału uchybu, idealnie:
$$\lim_{t \to \infty} e(t) = 0$$
**Uchyb statyczny (ustalony)** to wartość uchybu regulacji w stanie ustalonym.
$$e_u = \lim_{t \to \infty} e(t)$$
**Układ statyczny** to **otwarty** układ regulacji automatycznej, którego uchyb w stanie ustalonym, przy wymuszeniu skokowym, jest różny od zera i proporcjonalny do amplitudy wymuszenia.


![[Pasted image 20230103204755.png]]

**Przeregulowanie** to stosunek drugiej do pierwszej amplitudy uchybu, wyrażony w procentach. Jest to parametr określający jakość odpowiedzi skokowej. Może występować w wyniku niekorzystnych warunków lub złych nastaw regulatora.
$$\kappa_{względne} = \frac{e_{p2}}{e_{p1}} \cdot 100 \; [\%]$$$$\kappa_{bezwzględne} = \frac{e_{p1}}{e_{p0}} \cdot 100 \; [\%]$$
![[Pasted image 20230103210444.png|400]]

**Czas regulacji** to czas, po którym wartość sygnału wyjściowego nie będzie odbiegać od wartości w stanie ustalonym o więcej niż 1 - 5%.

**Zapas stabilności amplitudy** to wartość $\Delta_k$, o jaką musi wzrosnąć wzmocnienie układu otwartego przy niezmienionej fazie, aby układ zamknięty znalazł się na granicy stabilności. $L \; [dB] = 20 \cdot log_{10}(\Delta_k)$

**Zapas stabilności fazy** to wartość $\Delta_\phi$, o jaką musi wzrosnąć faza układu otwartego przy niezmienionym wzmocnieniu, aby układ znalazł się na granicy stabilności.

---

**Transmitancja operatorowa regulatorów**

Regulator P rzeczywisty: $\frac{k_p}{1 + Ts}$
Regulator I idealny: $\frac{1}{T_is}$
Regulator I rzeczywisty: $\frac{1}{T_is(1 + Ts)}$
Regulator D idealny: $T_ds$ (nierealizowalny)
Regulator D rzeczywisty: $\frac{T_ds}{1+Ts}$

Regulator PI rzeczywisty: $\frac{k_p}{1 + Ts}(1 + \frac{1}{T_is})$
Regulator PD rzeczywisty: $\frac{k_p}{1 + Ts}(1 + T_ds)$

Regulator PID idealny: $k_p(1 + \frac{1}{T_is} + T_ds)$
Regulator PID rzeczywisty: $\frac{k_p}{1 + Ts}(1 + \frac{1}{T_is} + T_ds)$

Sygnał sterujący dla PID:
$$u(t) = k_p \cdot (e(t) + \frac{1}{T_i}\int_0^t e(\tau)d\tau + T_d\frac{de(t)}{dt})$$

$T_i$ - stała czasowa zdwojenia
$T_d$ - stała czasowa wyprzedzenia
$u(t)$ - sygnał sterujący
$e(t)$ - uchyb regulacji (błąd sterowania)
  
---

**Nastaw regulatorów**

**Metoda Zieglera - Nicholsa** - empiryczna metoda ustalenia nastaw regulatora. Należy przełączyć regulator w tryb działania proporcjonalnego P oraz zwiększać wzmocnienie aż do osiągnięcia granicy stabilności. W układzie pojawią się drgania o stałej amplitudzie i okresie.
Zapisujemy wartość wzmocnienia jako $k_r$, a okres jako $T_r$. 

Nastaw regulatora P: $K_p = 0.5k_r$
Nastaw regulatora I: $K_p = 0.45k_r, T_i = 0.85T_r$
Nastaw regulatora D: $K_p = 0.6k_r, T_i = 0.5T_r, T_d = 0.12T_kr$


**Badanie stabilności układu**

**Stabilność** jest właściwością układu regulacji automatycznej polegającą na powrocie do stanu równowagi stałej po ustaniu działania wymuszenia, które wytrąciło układ ze stanu równowagi, lub osiągnięcia nowego stanu równowagi stałej, jeśli wymuszenie pozostało na stałym poziomie.

**Równanie charakterystyczne układu zamkniętego** $G_z(s) = \frac{L(s)}{M(s)}$ to mianownik $M(s) = 0$.

**Równanie charakterystyczne dla układu otwartego** $G_o(s) = \frac{L(s)}{M(s)}$ to po przekształceniu na układ zamknięty $G_z(s) = \frac{G_o(s)}{1 + G_o(s)}$, równanie charakterystyczne to suma $L(s) + M(s) = 0$.

**Jeśli wszystkie pierwiastki równania charakterystycznego układu mają ujemną część rzeczywistą, to układ jest stabilny**. Jest to warunek konieczny i dostateczny. Jeśli pojedyncze pierwiastki znajdują się na osi urojonej, to układ zamknięty jest na granicy stabilności. W praktyce jednak ta metoda jest często uciążliwa. Stąd powstały różne kryteria stabilności, jak algebraiczne kryterium Routha i Hurwitza, czy też częstotliwościowe kryterium Nyquista.

**Kryterium Nyquista** pozwala na badanie stabilności **układu zamkniętego** na podstawie wykresu funkcji $G_O(j\omega)$ **układu otwartego** na płaszczyźnie zmiennej zespolonej.
Podkreślam - należy zbadać charakterystykę amplitudowo-fazową układu otwartego!

Badamy obejmowanie punktu $(-1, 0j)$. 

![[Pasted image 20230103222004.png|500]]

Powyższa metoda ma zastosowanie tylko jeśli układ otwarty jest stabilny. Jeśli układ otwarty jest niestabilny, to występuje dodatkowy warunek - przekleję go z Wikipedii. Raczej tego nie będzie na kolokwium, ale dla kompletności:

Układ zamknięty będzie stabilny wtedy i tylko wtedy, gdy charakterystyka amplitudowo-fazowa układu otwartego obejmuje $\frac{k}{2}$ razy punkt $(-1, 0j)$ na płaszczyźnie zespolonej. Inaczej: promień wodzący wychodzący od punktu $(-1, 0j)$ i skierowany w stronę charakterystyki zakreśla kąt $\frac{k}{2\pi}$przy $\omega$ zmieniającej się od $0$ do $\infty$. $k$ oznacza liczbę biegunów układu w prawej półpłaszczyźnie zespolonej.

**Kryterium Hurwitza**
Warunkiem koniecznym i dostatecznym stabilności układu liniowego i stacjonarnego jest, aby wszystkie współczynniki wielomianu charakterystycznego transmitancji tego układu istniały i były dodatnie a ponadto, ażeby wyznacznik $\Delta_n$ zwany wyznacznikiem Hurwitza oraz jego podwyznaczniki $\Delta_2$, $\Delta_3$, ..., $\Delta_{n-1}$ były dodatnie.

Jeśli którykolwiek współczynnik jest ujemny lub równy zeru,
albo którykolwiek podwyznacznik jest ujemny
to układ jest niestabilny.

Jeśli dowolny z podwyznaczników jest równy zeru to oznacza, że równanie charakterystyczne układu jest na granicy stabilności.

Tak się tworzy wyznacznik dowolnego stopnia: 

![[Pasted image 20230103224908.png]]
  
**Elementy pomiarowe**

**Termometry:**

**Termistor** to opornik półprzewodnikowy, którego opór zależy od temperatury. 

Opór termistora NTC (Negative Temperature Coefficient) maleje wraz ze wzrostem temperatury. Wykonane m.in. z CrO (tlenek chromu), CoO (tlenek kobaltu)

Opór termistora PTC (Positive Temperature Coefficient) rośnie wraz ze wzrostem temperatury.
W termistorze CTR (Critical Temperature Resistor) wzrost temperatury powyżej parametr $T_{kryt}$ wywoła gwałtowną zmianę oporu. Wykonane m.in. z BTO (tytanian baru)

Dla niezbyt dużych różnic temperatur zależność oporu od temperatury możemy przybliżyć jako liniową: 
$$R = R_0 \cdot (1 + \alpha (T - T_0))$$
$R$ - rezystancja termistora w temperaturze $T$ 
$R_0$ - rezystancja termistora w temperaturze odniesienia $T_0$
$\alpha$ - główny współczynnik temperaturowy odniesienia

Dla termistorów CTR zależność oporu od temperatury T wyraża się wzorem:
$$R = R_0 \cdot \exp \frac{W}{2kT}$$
$R_0$ - stała termistora
$W$ - szerokość pasma zabronionego półprzewodnika
$k$ - stała Boltzmanna
$T$ - temperatura w kelwinach
$R$ - rezystancja termistora CTR w temperaturze T

Zmiana temperatury wewnętrznej termistora może być wywołana zmianą temperatury otoczenia, ale też zmianą natężenia prądu płynącego przez termistor. Termistory wykorzystuje się jako:
- czujniki temperatury
- elementy kompensujące zmianę oporności innych elementów elektronicznych
- ograniczniki natężenia prądu w np. ładowarkach do telefonów

**Pirometr** służy do bezdotykowego pomiaru temperatury poprzez analizę promieniowania cieplnego emitowanego przez ciało, w zakresie widma widzialnego oraz bliskiej podczerwieni. Jako przykład: ciało doskonale czarne emituje promieniowanie zależne tylko od temperatury.

**Termopara** generuje napięcie zależne od temperatury mierzonego przewodnika, dzięki czemu można ją wykorzystać do pomiaru temperatury. Napięcie powstaje przez zjawisko Seebecka: pomiędzy dwoma końcami tego samego przewodnika o różnej temperaturze powstanie napięcie. 
![[Pasted image 20230103232924.png]]


**Pomiar natężenia przepływu**

**Indukcyjny czujnik magnetyczny** polega na pomiarze siły elektromagnetycznej indukcji, która powstaje na skutek doprowadzenia strumienia magnetycznego prostopadle do cieczy. Pozwala to uzyskać zależność liniową pomiędzy otrzymanym napięciem a prędkością przepływu. Stosowane są dla żrących cieczy oraz przy niemożliwości zwężenia.

**Czujniki ultradźwiękowe** na przemian wysyłają i odbierają sygnały ultradźwiękowe, mierząc jednocześnie czas przejścia sygnału. Dźwięki płynące pod prąd zajmują więcej czasu niż płynące z prądem. Różnica czasów jest bezpośrednio proporcjonalna do natężenia przepływu. Druga grupa czujników polega na wykorzystaniu efektu Dopplera. Czujniki można zamontować na zewnątrz rury lub zintegrować je z rurą.

**Pomiar ciśnieniowy** - najbardziej rozpowszechniony, opiera się na zasadzie różnicy ciśnień na odpowiednio ukształtowanej zwężce.

**Metoda kalorymetryczna, przepływomierz cieplny** - do cieczy o cieple właściwym $c$ doprowadza się ciepło $Q$ i na podstawie pomiaru przyrostu temperatury $\Delta_t$ wyznacza się masowe natężenie przepływu $M$. Metoda jest słuszna dla $c = const$. 

![[Pasted image 20230103234832.png]]
  

**Mierniki**

**Czujnik ciśnienia**
Klasyczne rozwiązania czujników ciśnienia oparte były na wykorzystaniu właściwości sprężystych blaszanych mieszków oraz membran (zwykle metalowych), które pod wpływem ciśnienia ulegały odwracalnemu odkształcaniu. 

Nowoczesne czujniki piezorezystancyjne korzystają z membrany wykonanej przez chemiczne, głębokie wytrawianie krzemu. Grubość membrany określa zakres pomiarowy
sensora. Wymagany jest układ mikroprocesorowy.

**Czujnik poziomu cieczy**
W najprostszych czujnikach pływakowych wykorzystane jest zjawisko wyporu cieczy.
Czujnik może być podłączony na zewnątrz poprzez dźwignię do tensometra. Innym sposobem pomiaru jest badanie przesunięcia pomiaru pływaka.

Innym sposobem pomiaru jest czujnik pneumatyczny - powietrze jest jednocześnie wtłaczane pod stałym ciśnieniem do rurki w kształcie U z cieczą i do badanego pojemnika przez rurkę zanurzoną na danej głębokości. Gdy wzrasta poziom cieczy w badanym zbiorniku - wzrasta ciśnienie wywierane na powietrze wtłaczane, więc wzrasta ciśnienie wywierane na ciecz w U-rurkę - która zmienia swój poziom, wskazując nowy poziom cieczy.

Inny sposób to wykorzystanie ciśnienia na dnie zbiornika.

Można również zastosować czujniki pomiaru osiągnięcia danego poziomu - ciecz dochodząc do danego poziomu zwiera czujnik i sygnalizuje osiągnięcie danego poziomu.

**Przetworniki**
Przetwornik - urządzenie dokonujące przekształcenie danej wielkości w inną.

**Tensometr** 
Tensometr to miernik służący do pomiaru naprężenia. W praktyce mierzy się odkształcenie i oblicza naprężenie w oparciu o przyjęty związek fizyczny (np. prawo Hooke’a). Rezystancja zmienia się wraz ze zmianą wymiarów.
Wykorzystywane są różne stopy w celu uzyskania optymalnych własności w różnych warunkach.

Istnieją tensometry oporowe jak i półprzewodnikowe. Różnica jest w wykorzystanym materiale. 

**Przetwornik magnetyczny**
Wykorzystuje zmianę strumienia magnetycznego, a tym samym napięcia indukowanego w obwodzie wskutek działań mechanicznych.

**Przetwornik pojemnościowy**
Wykorzystuje zmianę pojemności układu elektrod tworzących kondensator pod wpływem
przemieszczania elektrod lub zmiany stałej dielektrycznej przestrzeni między elektrodami.
Najczulsze przetworniki przemieszczeń.

**Przetwornik fotoelektryczny**
Wykorzystuje zmiany strumienia promieniowania w zależności od zmian składu chemicznego, stężenia, zapylenia, zawiesin itp. ośrodka, przez który przechodzi promieniowanie

---

**Wykresy członów automatyki**

![[Pasted image 20230104005403.png|500]]
![[Pasted image 20230104005417.png|500]]
![[Pasted image 20230104005434.png|500]]
![[Pasted image 20230104005450.png|500]]
![[Pasted image 20230104005501.png|500]]
![[Pasted image 20230104005531.png|500]]
![[Pasted image 20230104005544.png|500]]
![[Pasted image 20230104005606.png|500]]
![[Pasted image 20230104005725.png|500]]

---

**Wykresy regulatorów**

Oznaczenia na wykresach:
![[Pasted image 20230104010228.png|400]]
![[Pasted image 20230104010339.png|400]]
![[Pasted image 20230104010329.png|400]]
![[Pasted image 20230104010312.png|400]]

![[Pasted image 20230104010254.png]]

![[Pasted image 20230104010144.png]]

![[Pasted image 20230104010055.png]]
