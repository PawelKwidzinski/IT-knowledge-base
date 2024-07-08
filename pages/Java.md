### Pytania rekrutacyjne
	- **Jakim językiem programowania jest JAVA (OOP, ale elementy funkcyjnego przy streamach)?**
	  collapsed:: true
		- JAVA jest współbieżnym, opartym na klasach, obiektowym językiem ogólnego zastosowania. Java jest językiem tworzenia programów źródłowych kompilowanych do kodu bajtowego wykonywanego przez wirtualną maszynę (JVM), która interpretuje/kompiluje na kod maszynowy.
		  
		  Podstawowe założenia:
		- WORA - Write Once Run Anywhere - wileoplatformowość
		- Sieciowość i obsługa programowania rozproszonego
		- Obiektowość
		- Niezawodność i bezpieczeństwo
		- Wydajność, wykorzystywanie procesorów wielordzeniowych
	- collapsed:: true
	  
	  **Co to jest JDK, JRE, JVM?**
		- **JDK (Java Development Kit)** - zawiera narzędzia dla programistów pozwalające na tworzenie aplikacji na platformę JVM. Jeżeli chcemy implementować lub chociażby kompilować programy napisane w Javie to potrzebujemy JDK.
		  **JRE (Java Runtime Environment)** - zawiera wyłącznie narzędzia niezbędne do uruchomienia aplikacji, tzw. Środowisko uruchomieniowe. Jeżeli chcemy tylko uruchamiać programy napisane w Javie to JRE nam wystarczy.
		  **JVM (Java Virtual Machine)** - wirtualny “komputer” opisany przez specyfikację (publicznie dostępną), która pozwala różnym producentom oprogramowania na tworzenie własnych maszyn wirtualnych pracujących pod kontrolą różnych środowisk i urządzeń. W Javie JVM sprawia, że kod źródłowy .java jest kompilowany do kodu bytowego .class, który jest uruchamiany przez JVM, która interpretuje/kompiluje na kod maszynowy.
	- **Gdzie lądują obiekty w JVM? Heap(sterta) czy Stack(Stos)**
	  collapsed:: true
		- Wszystkie tworzone obiekty są lokowane w stercie (heap). Dostęp do sterty odbywa się poprzez wskazanie komórki pamięci (przez referencje). Stertę współdzielą ze sobą wszystkie wątki programu.
		- W stosie (stack) są odkładane są zmienne lokalne (typy proste jak i referencyjne) oraz tworzone są ramki wywołań (czyli wywołań metod danego wątku). Dostęp do stosu realizowany jest jako pop i push. I każdy z wątków ma swój własny oddzielny stos. Dlatego zmienne zawarte na stosie nie mogą być współdzielone przez wątki.
	- **Co to jest i jak działa Garbage Collector w Javie?**
	  collapsed:: true
		- Garbage collector, inaczej GC, jest komponentem wirtualnej maszyny Javy, który działa w tle jest odpowiedzialny z czyszczenie sterty. Jeśli na stercie znajdą się obiekty, które już nie są używane zostaną one usunięte, aby zwolnić zwolnić miejsce dla nowych obiektów.
	- **Czym jest String Pool?**
	  collapsed:: true
		- String pool jest specjalnym miejscem w pamięci, do którego trafiają niektóre obiekty typu Stringi - dokładnie te, które nie są tworzone poprzez użycie operatora new.
		  String pool został stworzony w celu optymalizacji JVM, dzięki niemu wiele obiektów Stringów o tej samej wartości wskazują na ten sam obszar pamięci. Daje nam to mniejsze zużycie pamięci, gdyż String jest zazwyczaj najczęściej używanym typem w Javie. Dodatkowo przyspiesza to porównywanie Stringów - jest duże prawdopodobieństwo, że kilka obiektów wskazuje na ten sam obszar pamięci. Skoro mają tą samą referencje to dalsze porównywanie jest zbędne.
	- **Czym w Javie jest konstruktor?**
	  collapsed:: true
		- Konstruktor jest zawsze uruchamiany podczas tworzenie nowego obiektu za pomocą słowa **new**
		- Konstruktor nic nie zwraca i nie deklaruje typu zwracanego
		- Nazwa konstruktora musi byc taka sama jak nazwa klasy w której się znajduje
		- Jeśli nie utworzy konstruktora Java zrobi to za nas. Tworzy konstruktor domyślny który nic nie robi.
	- **Co oznacza programowanie obiektowe?**
	  collapsed:: true
		-
		- Wszystko jest obiektem. Programowanie obiektowe zakłada, że cały otaczający nas świat można przedstawić w postaci obiektów, które będą reprezentować uproszczony model świata rzeczywistego.
	- **Jakie są podstawowe założenia paradygmatu programowania obiektowego?**
	  collapsed:: true
		- Oto podstawowe założenia paradygmatu programowania obiektowego:
		- **Abstrakcja**: Abstrakcja polega na ukrywaniu szczegółów implementacji i pokazywaniu tylko funkcjonalności użytkownikowi. W praktyce oznacza to, że użytkownik interakcji z obiektem tylko poprzez jego metody, nie mając bezpośredniego dostępu do jego wewnętrznej struktury czy stanu.
		- **Hermetyzacja (enkapsulacja)**: Hermetyzacja to proces ukrywania szczegółów i danych obiektu. W praktyce oznacza to, że stan obiektu (jego dane) są chronione przed bezpośrednim dostępem, a dostęp do nich jest możliwy tylko poprzez metody obiektu.
		- **Dziedziczenie**: Dziedziczenie to mechanizm, który pozwala na tworzenie nowych klas na podstawie już istniejących (klas bazowych), przejmując ich atrybuty i metody. Dzięki temu możliwe jest tworzenie hierarchii klas i wielokrotne wykorzystanie kodu.
		- **Polimorfizm**: Polimorfizm to zdolność obiektu do przyjmowania wielu form. Najczęściej występuje, gdy klasa potomna dziedziczy metodę od klasy rodzica i następnie ją modyfikuje. Dzięki polimorfizmowi, metoda może być używana na różne sposoby w zależności od kontekstu.
	- **Przeciążanie metod (overloading) vs nadpisywanie metod (overriding)**
	  collapsed:: true
		- **Przeciążenie metody** oznacza utworzenie w klasie metody o tej samej nazwie, ale różnym zestawie parametrów ( różna liczba i/lub typie parametrów). Przeciążone metody mogą należeć do tej samej lub różnych klas (z których jedna pośrednio lub bezpośrednio dziedziczy inną)
		- **Nadpisywanie metod** - oznacza utworzenie w klasie pochodnej metody, która ma taką samą sygnaturę i typ wyniku co w klasie bazowej, ale inną definicję ciała metody.  Metody **prywatne i statyczne** nie mogą być nadpisywane oraz oznaczone słowem kluczowym **final**. Przy nadpisywaniu metod można rozszerzać dostęp, ale nie zawężać go (czyli zmienić z protected na public - ale nie odwrotnie). Odwołania do nadpisanych metod z poziomu metody podklasy realizowane są za pomocą wywołania - ***super.nazwa_metody({params})***
	- **Czy java jest czysto obiektowym językiem? (nie, typy proste)**
	  collapsed:: true
		- Java nie jest w pełni obiektowym językiem, typy proste lub zwane prymitywnymi nie są obiektami, pozostałe typy tak. To powoduje, że często jest potrzebne “opakowywanie” prostych zmiennych w obiekty-pojemniki.
	- **Jakie mamy typy proste?**
	  collapsed:: true
		- byte - rozmiar w pamięci: 1 bajt, zakres: od -127 do 128, znaczenie liczby całkowite
		- short - rozmiar w pamięci: 2 bajty, zakres: od -32768 do 32767, znaczenie liczby całkowite
		- int - rozmiar w pamięci: 4 bajty, zakres: od -2 147 483 648 14 do 2 147 483 647, znaczenie liczby całkowite
		- long - rozmiar w pamięci: 8 bajtów, zakres: od -2 do potegi 63 do 12 do potęgi 63, znaczenie liczby całkowite
		- float -  rozmiar w pamięci: 4 bajty, zakres: max około 7 liczb po przecinku, liczby rzeczywiste
		- double -  rozmiar w pamięci: 8 bajty, zakres: max około 15 liczb po przecinku, liczby rzeczywiste
		- char -  rozmiar w pamięci: 2 bajty, zakres: od 0 do 65556, liczbowe kody dla znaków Unicode
		- boolean - rozmiar w pamięci: 1 bajty, zakres: true, false, wartości logiczne
	- collapsed:: true
	  
	  **Jaka jest różnica pomiędzy klasami String, StringBuffer oraz StringBuilder?**
		- String jest niezmienny (immutable), w przeciwieństwie do StringBuffer i StringBuilder
		- StringBuffer jest thread safe i sychronized (tzn. Bezpiecznie wykorzystamy go w aplikacji wielowątkowej)
		- StringBuilder nie jest Thread Safe, w związku z tym jest szybszy niż StringBuffer
		- Konkatenacja String używa klasy StringBuffer lub StringBuilder
		- Do manipulowania Stringami w środowisku nie-wielowątkowym powinniśmy korzystać ze StringBuildera, w przeciwnym wypadku z StringBuffer
	- **Jakie znam inne paradygmaty programowania? (funkcyjne, proceduralne)**
	  collapsed:: true
		- **Paradygmat  programowania** - zbiór mechanizmów jakich programista używa pisząc program, i o to jak ów program jest następnie wykonywany przez komputer. Zatem paradygmat jest ogół oczekiwań programisty wobec języka programowania i komputera, na których będzie działał program.
		- **programowanie proceduralne** – zaleca dzielenie kodu na procedury, czyli ciągi instrukcji wykonujące ściśle określone operacje. Powinny one pobierać wszelkie przetwarzane dane jako parametry wywołania i zwracać wynik na ich podstawie.
		- **programowanie funkcyjne** – w programowaniu funkcyjnym, w odróżnieniu od programowania obiektowego, najważniejszym i zarazem jedynym narzędziem są funkcje. Funkcje mogą przyjmować na wejściu także funkcje oraz zwracać funkcje jako wynik. W programowaniu funkcyjnym musimy napisać co ma być zrobione a już kompilator zajmie się całą resztą.  W językach funkcyjnych także kod potrafi być od kilku do kilkudziesięciu razy zwięźlejszy i czytelniejszy niż analogiczny algorytm napisany w języku obiektowym. Wadą programowania funkcyjnego jest to, że bardzo często programy stworzone w językach funkcyjnych są po prostu wolne.
		- **programowanie funkcyjne (SDA)** ? Zamiast operować na stanach obiektów, definiujemy co faktycznie chcemy zrobić = co ma być osiągnięte.
	- **Z czym mi się kojarzy programowanie obiektowe?**
	  collapsed:: true
		- Programowanie obiektowe zakłada,że cały otaczający nasz świat można przedstawić za pomocą obiektów, które będą reprezentować uproszczony model świata rzeczywistego.
	- **Czym się różni obiekt od klasy?**
	  collapsed:: true
		- Klasa jest szablonem definiującym postać obiektu. Określa ona zarówno dane obiektu, jak i kod, który działa na tych danych. Java używa specyfikacji klasy podczas tworzenia obiektu. Obiekty są instancjami klasy. Innymi słowy, klasa jest zestawem planów określających sposób konstrukcji obiektu.
	- **Co może posiadać klasa?**
	  collapsed:: true
		- Definiując klasę, deklarujemy jej dokładną postać i zachowanie. W tym celu określamy zmienne, które zawiera klasa, i metody, które działają na tych zmiennych. Chociaż najprostsze klasy mogą zawierać tylko same metody bądź same zmienne składowe, to większość klas zawiera jedne i drugie. Klasę tworzymy przy użyciu słowa kluczowego class.
	- **Terminy ściśle związane z OOP**
	  collapsed:: true
		- **Stan obiektu** - zestaw atrybutów/cech (inaczej pola klasy), które są wspólne dla wszystkich obiektów danej klasy. Wartości pól są zawarte w obiektach (każdy obiekt ma swoje niezależne wartości!)
		  **Zachowanie obiektu** - zestaw operacji, które można wykonywać na obiektach klasy. Operacje klasy nazywamy metodami klasy. Są one wspólne dla wszystkich obiektów danej klasy.
		  **Metody dostępowe (gettery/settery)** - metody służące do ustawienia i pobierania wartości z pól obiektów. Pola są “ukrywane” przed innymi klasami, a dostęp do nich odbywa się przez metody dostępowe. Nie jest to wymóg języka tylko dobra praktyka tworzenia oprogramowania obiektowego.
		  **Konstruktor** - “specjalna” metoda w klasie, która służy (głównie) do inicjalizowania pól obiektu. Musi mieć taką samą nazwę jak klasa do której należy. Lista parametrów (rozdzielona przecinkami, opcjonalna). Ciało konstruktora posiada zestaw instrukcji, które inicjują pola obiektów i wykonują inne operacje potrzebne do utworzenia nowego obiektu tej klasy. Konstruktorów może być wiele (albo żadnego), muszą się różnić parametrami.
		  **Obiekty - tworzenie i używanie** - nowe obiekty tworzymy przez użycie słowa kluczowego “new” i podanie konstruktora z parametrami. Dostęp do metod i pól obiektu (o ile pozwala na to modyfikator dostępu) uzyskujemy przez znak kropki tzw. “Selektor”. Metody na obiektach możemy wywoływać wielokrotnie, zmieniają one tylko stan obiektu na rzecz którego są wywoływane (poprzez selektor). W nawiasach okrągłych podajemy parametry, które będą przekazane do metody.
	- **Modyfikatory dostępu, czym się różnią i co robią?**
	  collapsed:: true
		- Modyfikatory dostępu regulują dostęp do klas głównych oraz składowych klasy (pól, metod) oraz klas wewnętrznych.
		- Na poziomie składowych klasy wyróżniamy 4 modyfikatory:
		  **private** - prywatny, dostęp tylko w danej klasie
		  **[brak]** - przyjazny (pakietowy), dostępny tylko dla klas w danym pakiecie
		  **protected** - chroniony, dostęp z danej klasy, wszystkich klas dziedziczących oraz klas z danego pakietu.
		  **public** - publiczna, dostęp z każdego miejsca.
	- **Co oznacza static, na czym można go użyć i jak to wpływa na pola, metody czy klasy?**
	  collapsed:: true
		- **static** - słowo kluczowe static nie musi być łączone ze stałymi. Chcę jednak rozebrać je na czynniki pierwsze, ponieważ często spotyka się je razem z final w następujących konstrukcjach (ta akurat znów klasy String):
		  
		  private static final long serialVersionUID = -6849794470754667710L;
		  
		  Słowo “statyczny”, jako przeciwieństwo “dynamiczny” można w uproszczeniu rozumieć w ten sposób, że opisany nim byt do życia nie potrzebuje obiektów (tworzonych dynamicznie).
		- **Pole klasy static** - Jeśli pole klasy zostanie oznaczone jako static (jak w przykładzie bezpośrednio powyżej), oznacza to, że jest współdzielone przez wszystkie obiekty danej klasy. Można uzyskać do niego dostęp odwołując się do nazwy obiektu lub do nazwy klasy – efekt będzie ten sam. Pamięć jest przydzielana tylko raz, podczas ładowania klasy. W ten sposób można definiować ważne stałe albo różnego rodzaju liczniki (np. liczba egzemplarzy danej klasy – wówczas w konstruktorze zwiększamy wartość tego pola o 1).
		- **Metoda static** - metoda static jest współdzielona przez wszystkie obiekty, można ją także wywołać odnosząc się bezpośrednio do nazwy klasy, bez potrzeby tworzenia obiektu. Metoda ta ma dostęp jedynie do statycznych atrybutów (pól i metod) danej klasy. Co za tym idzie, nie może też używać słów this ani super. W ten sposób często definiuje się różne metody pomocnicze – na przykład większość metod w klasy [Math](https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html) . Najbardziej znana metoda statyczna to oczywiście main.
	- **Jak zdefiniować stałe pole w Javie?**
	  collapsed:: true
		- “Stałe” pola w Javie:
			- **final** - słowo “final” zmiania znaczenie w zależności od kontekstu, ale zawsze oznacza, że coś “ostateczne” i po utworzeniu nie da się już tego zmienić.
			- **Klasa final** - jeśli klasę oznaczymy słowem **final**, nie będzie można jej rozszerzać, czyli tworzyć jej podklas. Zatem będzie to “ostateczna” wersja klasy.
			- **Metoda final** - z metodami jest podobnie jak z klasami. Jeśli słowem **final** oznaczymy metodę, nie będzie można jej przesłaniać w klasach pochodnych - czyli mamy do czynienia z “ostateczną” wersją danej metody.
			- **Zmienna final** - jeśli jako **final** opiszemy zwykła zmienną w środku kodu, wartość (a dokładniej: wartość w przypadku typów prostych lub referencję w przypadku obiektów) będzie można jej przypisać maksymalnie raz.
			- **Pole klasy final** - jeśli słowem final oznaczymy pole klasy, będzie to oznaczało, że wartość (lub referencję) można mu nadać tylko raz - będzie ona ostateczna. Wartość tę można przypisać na dwa sposoby - albo “w miejscu”, przy definiowaniu klasy, albo w konstruktorze. Nie da się tego zrobić później. Jeśli pole final nie otrzyma wartości w żadnym z tych dwóch miejsc, kompilator zaprotestuje.
			- **Parameter final** - jeśli jako final oznaczymy parametr metody, zablokujemy możliwość zmiany jego wartości. I tak nie powinniśmy tego robić - to jedna z dobrych praktyk. Użycie słowa final oficjalnie nas do niej zobowiązuje.
	- **Interfejsy - co to?**
	  collapsed:: true
		- Jest to zestaw metod bez ich implementacji(bez kodu opisującego zachowanie metody). Właściwa implementacja metod danego interfejsu następuje w klasie implementującej dany interfejs.
		- Wszystkie metody zawarte w interfejsie domyślnie są publiczne, więc można ominąc słowo kluczowe **public** przed **interface**, nie jest ono potrzebne.
		- Inne pojęcie:
			- Specjalna konstrukcja w Javie (podobna do klasy), której celem jest wyeksponowanie funkcjonalności (sposób komunikacji) pomiędzy klasami, bibliotekami czy frameworkami. Wspomaga hermetyzację kodu i częściowo rozwiązuje problem wielodziedziczenia.
	- **Klasa abstrakcyjna - co to?**
	  collapsed:: true
		- Klasa w której zadeklarowano jakąkolwiek metodę abstrakcyjną, jest klasą abstrakcyjną.
		- Metoda abstrakcyjna nie ma implementacji (ciała) i powinna być zadeklarowana ze specyfikatorem **abstract**
		- Metody abstrakcyjne to takie, co do których nie wiemy jeszcze, jaka może być ich konkretna implementacja
		- Metody abstrakcyjne muszą mieć implementację w każdej konkretnej klasie bazowej
		- Klasa abstrakcyjna nie musi mieć metod abstrakcyjnych
		- Abstrakcyjność klasy oznacza, że nie można tworzyć jej obiektów (instancji)
		- Metody abstrakcyjne mogą być użyte w zwykłych metodach mimo, że nie mają jeszcze implementacji
	- **Interfejs vs klasa abstrakcyjna**
	  collapsed:: true
		- Klasy abstrakcyjne mogą dziedziczyć jak i można po niej dziedziczyć, mogą dostarczać ciała metod i mogą określać metody o innej widoczności niż ‘public’. Interfejsy z kolei mogą być dziedziczone wielokrotnie, mogą dostarczać domyślne ciała metod (ale nie mogą przesłaniać innych metod) i dotyczą tylko metod o widoczności public. Interfejs powinien mówić co można z daną klasą zrobić, a klasa abstrakcyjna powinna być narzędziem do budowy hierarchii klas.
	- **Co oznacza słowo kluczowe “volatile”? Podaj przypadek, w którym byś go użył.**
	  collapsed:: true
		- Słowo kluczowe **volatile** sprawia iż dana wartość będzie zapisana w danej pamięci tak szybko jak to możliwe. Np. Istnieją dwa wątki działające na tej samej zmiennej. Jeden wątek odpowiedzialny jest zmianę jest wartości, drugi za odczyt. By upewnić iż oba wątki mają aktualną wartość zmiennej korzystamy z **volatile**, które wymusi na wątku pierwszym by zwrócił wartość do głównej pamięci od razu po jej zmianie.
	- **Porównaj metody sleep() oraz wait() . Podaj przypadki, użycia tych metod.**
	  collapsed:: true
		- **sleep()** - każe czekać określoną ilość czasu w milisekundach przy tym wstrzymując działanie wątku np. sleep(2000) (2 sek.)
		- **wait()** - każe czekać maksymalnie do określonego czasu np. wait(2000)
		  
		  Rożnica jest taka iż wait może zostać przerwane np. Przez **notifyAll()**;
	- **Jakie są różnice pomiędzy throw oraz throws?**
	  collapsed:: true
		- **throw** jest używane w ciele metody by wyrzucić wyjątek
		- **throws** jest używane w sygnaturze metody by poinformować o wyjątku jaki może się pojawić
	- **Jakie są różnice między *****final*****, *****finally*****, *****finalize*****?**
	  collapsed:: true
		- **final** - jest słowem kluczowym, które użyte ze zmienną zmienia ją w stałą. Natomiast użyte wraz z metodą powoduje iż nie można jej nadpisać. Można również wykorzystać je wraz z klasą - wówczas blokuje ono możliwość dziedziczenia danej klasy
		- **finally** - jest elementem bloku *try-catch-finally.* Operacje zawarte w tej sekcji zostaną zawsze wykonane - niezależnie czy kod zawarty w sekcji **catch** zakończył się sukcesem, czy rzucił wyjątkiem
		- **finallize** - jest metodą klasy Object, która w teorii miała być wywoływana przed tym, gdy dany obiekt zostanie usunięty z pamięci przez garbage collector. W praktyce nie zawsze ( albo wręcz z reguły nie działa w 100%. Obecnie oznaczona jest jako deprecated i nie powinna być używana pod żadnym pozorem.
	- **Strumienie co to? Czemu są lazy?**
	  collapsed:: true
		- Strumienie są one odpowiedzialne za przetwarzanie danych w postaci strumieni oraz za operacje na wielu elementach. Do reprezentowania kolekcji w trakcie przetwarzania służy nowy interfejs **Stream<T>**. Na strumieniach możemy wykonać szereg operacji, aby na końcu pobrać wynik (metoda agregująca) tych operacji bez zmiany stanu samego strumienia.
		- Operacje na strumieniach można podzielić na dwa typy:
		  **Terminalne** (ang. terminal)
		  **Pośrednie**(ang. intermediate)
		- **Terminalne** - są to operacje, które zamykają strumień. Kończą one pracę ze strumieniem. Uwaga!  Może być tylko jedna operacja kończąca, w przeciwnym wypadku wystąpi wyjątek.
		  **Pośrednie** - czyli metody, które operują na strumieniu, ale go nie zamykają. Dzięki temu możliwy jest **chaining.**
		- Strumienie są **leniwie inicjowane **(ang. laziness-seeking), czyli operacje pośrednie wykonywane są dopiero wtedy, kiedy natrafiają na operację **terminalną.**
		- Wykonywanie operacji w łańcuchu (ang. chaining) jest możliwe dzięki metodom (wykonywanym na strumieniach), które zwracają przetworzony strumień.
		- Strumienie są “jednorazówkami” (ang. non reusable) , czyli nie wykorzystujemy ich kilka razy, ponieważ każde użycie strumienia musi być zakończone operacją terminalą(zamykającą strumień).
		- **Źródło:**  https://codecouple.pl/2016/02/15/strumienie-danych-w-javie-java-util-stream/
	- **Wymień kilka metod na strumieniach**
	  collapsed:: true
		- **filter** - zwraca strumień zawierający tylko te elementy do których filtr zwrócił wartość **true**
		- **map** - każdy z elementów może zostać zmieniony do innego typu, nowy obiekt zawarty jest w nowym strumieniu
		- **peek** - pozwala przeprowadzić operację, na każdym elemencie w strumieniu, zwraca strumień z tymi samymi elementami
		- **limit** - zwraca strumień ograniczony do zadanej liczby elementów, pozostałe są ignorowane.
		  
		  **Źródło:** [https://www.samouczekprogramisty.pl/strumienie-w-jezyku-java/](https://www.samouczekprogramisty.pl/strumienie-w-jezyku-java/)
	- **Wymień metody kończące na strumieniach**
	  collapsed:: true
		- Operacjami kończącymi są wszystkie, które zwracają typ inny niż **Stream**. Metody tego typu mogą także nie zwraca żadnych wartości.
		- **forEach** - wykonuje zadaną operację dla każdego elementu
		- **count** - zwraca liczbę elementów w strumieniu
		- **allMatch** - zwraca flagę informującą czy wszystkie elementy spełniają warunek. Przestaje sprawdzać na pierwszym elemencie, który tego warunku nie spełnia
		- **collect** - pozwala na utworzenie nowego typu na podstawie elementów strumienia. Przy pomocy tej metody można na przykład utworzyć listę. Klasa Collectors zawiera sporo gotowych implementacji.
	- **Co jest najwyżej w drzewie dziedziczenia i jakie metody musi miec kazdy obiekt**?
	  collapsed:: true
		- W Javie klasa Object jest najwyżej w hierarchii dziedziczą po niej wszystkie klasy.
		- Metody klasy Object:
		  toString()
		  equals()
		  hashCode()
		  
		  Źródło: [http://karolwojcik.net/java-class-design-67-nadpisywanie-metod-klasy-object/](http://karolwojcik.net/java-class-design-67-nadpisywanie-metod-klasy-object/)