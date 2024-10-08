- Instalacja
  collapsed:: true
	- NVM (zbiór rożnych wersji node js)
	  https://github.com/coreybutler/nvm-windows
		- przydatne komendy (admin w PowerShellu):
			- **nvm + enter** -> wyświetla listę komend
			- **nvm current** -> pokazuje zainstalowaną wersję node.js
			- **nvm install 20** -> instaluje noda w wersji 20.15.1 LTS
			- **nvm use 20.15.1** -> ustawiamy wersję noda na 20.15.1
	- po zainstalowaniu node.js instalujemy **Angular CLI** komendą (admin w PowerShellu):
	  **npm i -g @angular/cli@18** i potem sprawdzamy komendą: **ng version**
	- komenda: **ng --help** -> wyświetla wszystkie komendy w angularze
	  oficjalna dokumentacja -> https://angular.dev/cli
- Tworzenie projektu wraz przydatnymi komendami
  collapsed:: true
	- **ng new nazwa-projektu --no-standalone** -> komenda do tworzenia projektu(od wersji 17)
	- zainstalowanie biblioteki bootstrap -> **npm install bootstrap@5.2.3**
	  :LOGBOOK:
	  CLOCK: [2024-07-18 Thu 09:55:23]--[2024-07-18 Thu 09:55:24] =>  00:00:01
	  :END:
	  Po zainstalowaniu trzeba w stylach dopisać scieżkę **"node_modules/bootstrap/dist/css/bootstrap.min.css"** w pliku **angular.json**
	  ![image.png](../assets/image_1721289340273_0.png){:height 137, :width 405}
	  Ścieżkę zainstalowanych styli **bootstrapa** (także innych bibliotek) zawsze dajemy nad ścieżką **"src/styles.css"**, w przeciwnym razie może na to nadpisywać style z głównego pliku **styles.css**
	  Po każdej modyfikacji pliku **angular.json** należy zrestartować aplikację
	- **ng g c nazwa** (ng generate component) -> generowanie komponentu
	- **ng g c footer --inline-template** -> generowanie komponentu bez pliku html, który dodajemy w komponencie (przydaje się przy małych komponentach jak stopki czy przyciski)
	- **ng g s nazwa** (ng generate service) -> generowanie serwisu
- Data Binding w Angular
  collapsed:: true
	- Data Binding to powiązanie stanu komponentu z widokiem HTML, rozróżniamy:
		- **One-way Data Binding** – z komponentu (pliku .ts) do szablonu (pliku HTML)
		  collapsed:: true
			- Interpolation (Interpolacja) za pomocą operatora {{}}
			  collapsed:: true
				- Służy do wyświetlania wartości (property) z klasy komponentu w widoku HTML.
				- Operator {{}}
				  Poniższy zapis wyświetli w komponecie napis „Witaj, Andrzej!
				  ![image.png](../assets/image_1721293819905_0.png){:height 108, :width 415}
				  ![image.png](../assets/image_1721293867311_0.png){:height 176, :width 329}
			- Property Binding za pomocą operatora []
			  collapsed:: true
				- Służy do przypisania wartości z klasy komponentu do właściwości (property) elementów HTML w szablonie.
				- Operator []
				  ![image.png](../assets/image_1721293969563_0.png){:height 125, :width 383}
				  ![image.png](../assets/image_1721293987139_0.png){:height 123, :width 383}
		- **One-way Data Binding** – z szablonu (pliku HTML) do komponentu (pliku .ts).
		  collapsed:: true
			- Event Binding za pomocą operatora ()
				- Służy do reagowania na zdarzenia wywoływane przez użytkownika w aplikacji. W tym celu w komponencie należy zdefiniować metodę, która zostanie wywołana, gdy użytkownika wykona jakieś akcje w interfejsie.
				- Operator ()
				  ![image.png](../assets/image_1721294491434_0.png){:height 151, :width 422}
				  ![image.png](../assets/image_1721294517944_0.png){:height 101, :width 423}
		- **Two-way Data Binding** – czyli zarówno z szablonu do pliku .ts, jak i z pliku .ts do szablonu. Połączenie Property Binding oraz Event Binding za pomocą dyrektywy [(ngModel)]
		  id:: 6698deda-4439-46aa-96bb-dd1badcb8fd4
		  collapsed:: true
		  (konieczny import modułu FormsModule)
			- Służy do synchronizacji danych między koponentem, a szablonem (w obie strony). Zmiana danych w szablonie automatycznie zmieni wartość w klasie komponentu, a zmiana wartości w klasie komponentu automatycznie zostanie wyświetlona w szablonie.
			- Dyrektywa [(ngModel)]. Konieczny jest import modułu FormsModule w module, w którym znajduje się komponent.
			  ![image.png](../assets/image_1721294670322_0.png){:height 145, :width 316}
			  ![image.png](../assets/image_1721294689527_0.png){:height 133, :width 425}
			  ![image.png](../assets/image_1721294709584_0.png){:height 94, :width 448}
- Dyrektywy w Angular
  collapsed:: true
	- **Dyrektywy strukturalne** – dodawanie / usuwanie elementów z DOM
	  collapsed:: true
		- Dyrektywa * **ngFor** -> pozwala iterować po kolekcji danych np. po tablicy i wyświetlić odpowiednie dane. Poniżej przykład.
		  ![image.png](../assets/image_1721300522207_0.png){:height 80, :width 353}
		  ![image.png](../assets/image_1721300542379_0.png){:height 133, :width 350}
		  ![image.png](../assets/image_1721300554679_0.png){:height 138, :width 212}
		- Dyrektywa * **ngIf** -> pozwala na dynamiczne dodawanie lub usuwanie elementów z interfejsu użytkownika w zależności od wartości warunku. Elementy są usuwane z drzewa DOM i nie można ich podglądnąć w zakładce Elements w devtools.
		  ![image.png](../assets/image_1721300717316_0.png){:height 89, :width 232}
		  ![image.png](../assets/image_1721300744588_0.png){:height 95, :width 372}
		  Powyższy element **<p>** nie zostanie wyświetlony w przeglądarce, ponieważ właściwość **displaySomething** w app.component.ts ma wartość false
		- Dyrektywa * **ngSwitch** -> pozwala na dynamiczne przełączanie pomiędzy różnymi elementami interfejsu użytkownika w zależności od wartości wyrażenia.
		  ![image.png](../assets/image_1721300891712_0.png){:height 108, :width 270}
		  ![image.png](../assets/image_1721300905310_0.png){:height 178, :width 445}
		  W przeglądarce wyświetli się zawartość pierwszego **<p>**, ponieważ właściwość **switchCase** ma taką samą wartość, jak warunek przy * **ngSwitchCase**
	- **Dyrektywy atrybutowe** - zmiana wyglądu elementów DOM.
		- Dyrektywa * **ngStyle** -> pozwala na dynamiczne ustawianie stylów CSS na elemencie w oparciu o wartości właściwości w komponencie.
		  ![image.png](../assets/image_1721301100774_0.png){:height 94, :width 310}
		  ![image.png](../assets/image_1721301113235_0.png){:height 97, :width 628}
		  ![image.png](../assets/image_1721301126987_0.png){:height 54, :width 232}
		  W tym przypadku kolorem pozostanie czarny, ponieważ właściwość isRed jest ustawiona na wartość false
		- Dyrektywa * **ngClass** -> pozwala na dynamiczne dodawanie lub usuwanie klas CSS na elemencie w oparciu o wartości właściwości w komponentach.
		  ![image.png](../assets/image_1721301234585_0.png){:height 96, :width 333}
		  ![image.png](../assets/image_1721301245321_0.png){:height 84, :width 552}
		  ![image.png](../assets/image_1721301255728_0.png){:height 88, :width 181}
		  ![image.png](../assets/image_1721301265693_0.png){:height 48, :width 245}
		  Właścwiość **useClass** ma wartość true, więc element **<p>** otrzyma dwie klasy – **class1** oraz **class2**.
	- **Komponenty** - to także dyrektywa, ale posiada tzw. widok definiowany przez szablon HTML.
	- **ng-container** - to specjalny element, który służy jako logiczny kontener do  grupowania elementów DOM bez dodawania dodatkowego węzła do drzewa DOM. Oto najważniejsze cechy i zastosowania ng-container:
	  collapsed:: true
		- Jest to element logiczny, który nie renderuje się w finalnym drzewie DOM - zamiast tego jest renderowany jako komentarz HTML.
		- Służy głównie do grupowania elementów bez konieczności dodawania dodatkowego elementu HTML (jak np. div).
		- Jest szczególnie przydatny przy używaniu dyrektyw strukturalnych, takich jak *ngIf, *ngFor czy *ngSwitch.
		- Pozwala na stosowanie wielu dyrektyw strukturalnych na jednym fragmencie kodu bez konieczności dodawania dodatkowych elementów.
		- Pomaga uniknąć problemów z stylami CSS, które mogłyby wystąpić przy dodawaniu dodatkowych elementów div lub span.
		- Jest często używany do warunkowego renderowania grup elementów.
		- Może być używany do poprawy czytelności kodu poprzez logiczne grupowanie elementów.
		- W przeciwieństwie do ng-template, ng-container nie wymaga użycia dyrektywy strukturalnej do renderowania zawartości.
		  ![image.png](../assets/image_1721385018161_0.png){:height 305, :width 523}
- Sposoby komunikacji między komponentami
  collapsed:: true
	- Dekorator **@Input()**
	  collapsed:: true
		- Za pomocą tego dekoratora komponent rodzic (parent) może przekazywać dane do komponentu dziecka(child). 
		  Dekorator przyjmuje opcjonalną nazwę do użycia np. @Input('nazwa-wlasciwosci'). Konieczny jest import **Input** z **@angular/core** jak na załączonym poniżej obrazku.
		  ![image.png](../assets/image_1721638316249_0.png){:height 274, :width 416}
		  ![image.png](../assets/image_1721638335600_0.png){:height 125, :width 295}
		  ![image.png](../assets/image_1721638351843_0.png)
		  ![image.png](../assets/image_1721638363165_0.png){:height 133, :width 140}
	- Dekorator **@Output()**
	  collapsed:: true
		- Za pomocą tego dekoratora komponent dziecko (child) może komunikować się z komponentem rodzicem (parent). Dekorator przyjmuje opcjonalną nazwę do użycia np. @Output('my-event'). Konieczny jest import **Output** oraz **EventEmitter** z **@angular/core**.
		  id:: 669e1e29-b849-4f9c-b57f-65f36f96bb26
		  ![image.png](../assets/image_1721638850820_0.png){:height 340, :width 492}
		  ![image.png](../assets/image_1721638883917_0.png){:height 70, :width 499}
		  ![image.png](../assets/image_1721638906755_0.png){:height 92, :width 653}
		  ![image.png](../assets/image_1721638917251_0.png){:height 215, :width 356}
- Lifecycle hooks w Angular
  collapsed:: true
	- to specjalne metody, które pozwalają na wykonanie kodu w kluczowych momentach cyklu życia komponentu lub dyrektywy.
		- Główne lifecycle hooks:
			- ![image.png](../assets/image_1721730361177_0.png)
			- Odpalane jednorazowo:
				- **ngOnInit() - OnInit**
				  Uruchamia się dokładnie raz w całym cyklu życia dyrektywy/komponentu, gdy komponent się zainicjalizuje. Można wykonywać tutaj kosztowne operacje, których nie powinno umieszczać się w konstruktorze.
				- **ngAfterContentInit() - AfterContentInit**
				  Uruchamia się po tym, jak zainicjalizują się elementy dostarczone poprzez projekcję treści, czyli element <ng-content>. Tutaj mamy dostęp do elementów html / komponentów, które są wyświetlane za pomocą <ng-content>.
				- **ngAfterViewInit() - AfterViewInit**
				  Uruchamia się raz po pierwszym wywołaniu ngAfterContentChecked(). Używana do
				  reagowania, gdy Angular w pełni zainicjalizuje widok komponentu oraz widok jego child
				  komponentów (albo widok który zawiera dyrektywę).
				- **ngOnDestroy() - OnDestroy**
				  Uruchamia się przed tym, jak Angular zniszczy komponent / dyrektywę. Tutaj dokonuje
				  się „czyszczenia” zależności itp. by uniknąć wycieków pamięci.
			- Odpalane wielokrotnie:
				- **OnChanges - ngOnChanges()** - Uruchamia się przy tworzeniu komponentu (jeśli istnieją jakieś property z dekoratorem @Input()). Odpala się za każdym razem, gdy zmienia się wartość property z @Input().
				- **DoCheck - ngDoCheck()** - Uruchamia się za każdym razem, gdy zadziała detekcja zmian w Angular. Używana do wykrywania zmian, które Angular mógł pominąć / wykonywania jakiejś operacji po każdym wywołaniu detekcji zmian.
				- **AfterContentChecked - ngAfterContentChecked()** - Uruchamia się po ngAfterContentInit(), a następnie po każdym wywołaniu ngDoCheck(), kiedy detekcja zmian sprawdzi widok dostarczany poprzez projekcję treści (ng-content).
				- **AfterViewChecked - ngAfterViewChecked()** - Uruchamia się po ngAfterViewInit() i następnie po każdym ngAfterContentChecked(). Używany do reagowania, gdy Angular już sprawdzi widok komponentu i widok child komponentów.
- Pipe
  collapsed:: true
	- To proste funkcje, używane w szablonie HTML, które przyjmują jakąś wartość na
	  wejściu i zwracają ją w zmienionej postaci
	- Używane do formatowania string’ów, walut, liczb, dat itp. 
	  ![image.png](../assets/image_1721905557784_0.png){:height 113, :width 296}
	  ![image.png](../assets/image_1721905598400_0.png){:height 111, :width 350}
	- Wbudowane Pipe
	  collapsed:: true
		- AyncPipe (async) – obsługa asynchronicznych działań (Promise/Observable)
		- CurrencyPipe (currency) – wyświetlanie liczb w formie walut
		- DatePipe (date) – formatowanie dat (można dopasować do dat lokalnych)
		- DecimalPipe (number) – formatowanie liczb zależnie od ustawień lokalnych i separatora
		- JsonPipe (json) – zamienia obiekt w jego reprezentacje w postaci JSON (którą można wyświetlić za pomocą interpolacji)
		- KeyValuePipe (keyvalue) – zamienia obiekt w tablicę z parami klucz-wartość
		- LowerCasePipe (lowercase) – zmienia cały tekst na pisany małymi literami
		- PercentPipe (percent) – zamienia liczbę na jej reprezentację w procentach
		- SlicePipe (slice) – tworzy nową tablicę lub string zawierający wycięty kawałek początkowej
		  wartości
		- UpperCasePipe (uppercase) – zmienia cały tekst na pisany dużymi literami
		- TitleCasePipe (titlecase) – formatuje zdanie, żeby każde słowo zaczynało się z dużej litery
	- Tworzenie własnych Pipe -> **ng g p shared/pipes/first-letter-uppercase**
	  ![image.png](../assets/image_1721905757726_0.png){:height 304, :width 431}
	  ![image.png](../assets/image_1721905778696_0.png){:height 262, :width 251}
- Biblioteka RxJS
  collapsed:: true
	- Czym jest RxJs
	  collapsed:: true
		- RxJS to biblioteka (JavaScript) do programowania reaktywnego, czyli asynchronicznego
		  programowania związanego z wykorzystaniem obserwowalnych strumieni danych. RxJS dostarcza typ tzw. Observable.
		- Angular używa biblioteki RxJS do m.in.: obsługi żądań HTTP (zwraca tzw. Observable),
		  w formularzach, obsługi routingu oraz przy EventEmitter (dziedziczy po klasie Subject, który jest Observable).
	- Czym jest Observable i Observer
	  collapsed:: true
		- ![image.png](../assets/image_1722243644187_0.png){:height 188, :width 360}
		  ![image.png](../assets/image_1722243668623_0.png){:height 357, :width 420}
		- Observable – to obiekt, który emituje wartości przekazywane asynchronicznie (strumień danych). Możemy się do niego subskrybować za pomocą metody subscribe() i nasłuchiwać na pojawiające się wartości. Kiedy subskrybujemy się do Observable – to zwraca nam obiekt Subscription (możemy przypisać go do zmiennej i np. użyć w OnDestroy do odsubskrybowania)
		- Observer – to obiekt, nasłuchuje na wartości emitowane przez Observable. Można go rozumieć
		  jako odbiorcę danych, który w jakiś sposób reaguje na pojawiające się wartości. Obiekt Observer składa się z trzech funkcji – next() (kiedy Observable emituje nową wartość), error() (Observable zwraca błąd), complete() (kiedy Observable kończy emisję wartości). Obiekt Observer przekazujemy do metody subscribe().
	- Tworzenie Observera
	  collapsed:: true
		- Zamiast do ciała metody subscribe() przekazywać nawiasy klamrowe (obiekt Observer) i tam
		  reagować na next, error i complete możemy utworzyć Observer osobno, dzięki czemu będziemy mogli go stosować w kilku miejscach (komponentach itd.)
		  ![image.png](../assets/image_1722243937943_0.png){:height 178, :width 349}
		  ![image.png](../assets/image_1722243952738_0.png){:height 283, :width 421}
	- Observable czy Promise?
	  collapsed:: true
		- **Promise** są wbudowane w język JavaScript i są wykorzystywane do asynchronicznego działania kodu. Jednak Observable dają większe możliwości, jeśli chodzi o pracę z asynchronicznym kodem.
		- ***Promise***:
		  collapsed:: true
			- Jest eager, tzn. że wykonuje się od razu.
			- Dostarcza jedną wartość.
			- Nie można przerwać jego działania.
			- Nie posiada wbudowanych operatorów, łączenie za pomocą .then().
			- Obsługa błędów poprzez .catch().
		- ***Observable:***
		  collapsed:: true
			- Jest lazy, tzn. wykonuje się dopiero po subskrypcji.
			- Może dostarczać strumień z wieloma wartościami.
			- Można przerwać jego działanie poprzez odsubskrybowanie.
			- Posiada wbudowane operatory do wpływania na dane przychodzące ze strumienia danych.
			- Dedykowane operatory do obsługi błędów.
	- Czym jest Subject?
		- Subject – to rodzaj Observable, które działa również jako Observer. Można go rozumieć jako
		  połączenie strumienia danych i odbiorcy, który może jednocześnie emitować wartości (metoda
		  **next()**) i nasłuchiwać (subskrybować) na wartości. Nie przyjmuje żadnych danych wejściowych. Posiada kilka odmian (m.in. **BehaviorSubject** – który działa tak samo oprócz tego, że przyjmuje dane wejściowe oraz przechowuje ostatnio emitowaną wartość).
		  ![image.png](../assets/image_1722248621971_0.png){:height 274, :width 280}
		  ![image.png](../assets/image_1722248638123_0.png){:height 308, :width 416}
		  W powyższym kodzie w metodzie **changeName()** za każdym razem, gdy właściwość name otrzyma nową wartość emitujemy tą wartość poprzez **Subject**. Dzięki temu możemy subskrybować się do tego **Subject** w różnych komponentach i reagować na zmianę **name**.
	- Kiedy trzeba użyć **unsubscribe()**, a kiedy nie?
		- Do Observable możemy się subskrybować (metoda **subscribe()**), ale i odsubskbrybować (metoda **unsubscribe()**). W niektórych sytuacjach np. kiedy pracujemy ze skończonymi strumieniami danych nie ma konieczności używania unsubscribe().
		- **Trzeba:**
		  collapsed:: true
			- Subskrybujemy się do Subject/BehaviorSubject.
			- Subskrybujemy się do eventów DOM za pomocą fromEvent().
			- Subskrypcja do Store w NgRx.
			- Nieskończone strumienie danych – np. metoda interval().
			- Formularze – metoda valueChanges(), czyli subskrypcja do kontrolki formularza.
		- **Nie trzeba:**
		  collapsed:: true
			- Używamy skończonego strumienia **of()**.
			- Subskrybujemy się do Observable z HttpClient (żadania HTTP).
			- Subskrybujemy się do Observable z Routera.
			- Po wykorzystaniu **AsyncPipe**.
		- Jak używać unsubscribe()
		  collapsed:: true
			- Bardzo ważne jest żeby używać unsubscribe(), wtedy kiedy jest to konieczne! Inaczej po zniszczeniu komponentu subskrypcja dalej będzie działać, co może spowodować bardzo duże wycieki pamięci i problemy z działaniem aplikacji.
			  ![image.png](../assets/image_1722249295235_0.png){:height 95, :width 277}
			  ![image.png](../assets/image_1722249306750_0.png){:height 333, :width 466}
			- Alternatywny sposób na unsubscribe()
			  ![image.png](../assets/image_1722249404088_0.png){:height 380, :width 429}
		- Tworzenie własnych Observable (operatory tworzące)
		  collapsed:: true
			- RxJS udostępnia funkcję do tworzenia własnych Observable:
				- of()
				- from()
				- interval()
				- timer()
				- fromEvent()
				- defer()
			- ![image.png](../assets/image_1722249568873_0.png){:height 153, :width 483}
	- Operatory RxJS
	  ![image.png](../assets/image_1722250480308_0.png){:height 154, :width 529}
		- Operatory w RxJS to funkcje, które pozwalają na transformację, filtrowanie i manipulowanie
		  strumieniami danych w czasie rzeczywistym.
		- Używanie operatorów jest dostępne dzięki metodzie **.pipe()**.
		- Jest podział zależnie od tego, co wykonuje dany operator. Istnieją operatory kombinacyjne,
		  filtrujące, operatory matematyczne, operatory transformujące itd.
		- Oprócz wbudowanych operatorów RxJS można tworzyć także własne, ale istnieje duża szansa że biblioteka RxJS już zawiera operator, który będzie nam potrzebny.
- Rodzaje formularzy w Angular
  collapsed:: true
	- Jeśli chodzi o pracę z formularzami w Angular, to jeśli Nasz formularz ma więcej niż jedną kontrolkę to lepiej wykorzystać **Reactive Forms** (choć nie jest to wymóg). **Reactive Forms** są bardziej elastyczne i skalowalne niż **Template Driven Forms**. Do tego **Reacive Forms** ułatwiają tworzenie testów jednostkowych dla formularzy i są oparte na **Observable** (każda kontrolka to obiekt FormControl, która pozwala używać metodę valueChanges(), która zwraca Observable).
	- **Template Driven Forms** - formularze są tworzone bezpośrednio w szablonie HTML.
		- Aby korzystać z **Template Driven Forms** moduł Angular, w którym pracujemy musi importować wbudowany moduł **FormsModule** (często import FormsModule umieszcza się w tzw. SharedModule).
		  ![image.png](../assets/image_1722418546258_0.png){:height 88, :width 220}
		- Po imporcie FormsModule w komponentach naszego modułu otrzymujemy dostęp do trzech dyrektyw:
			- NgModel (używana do ((6698deda-4439-46aa-96bb-dd1badcb8fd4)) )
			- NgForm (umożliwia śledzenie aktualnej wartości kontrolek formularza i statusu walidatorów kontrolek, po imporcie FormsModule domyślnie wszystkie formularze mają aktywną tą dyrektywę)
			- NgModelGroup (pozwala grupować kontrolki)
		- Ważne! Używając dyrektywy ngModel musimy także dodać atrybut name do tej kontrolki!
		  collapsed:: true
			- ![image.png](../assets/image_1722418734691_0.png){:height 88, :width 390}
		- Dodanie dyrektywy **ngModel** do kontrolki dodaje także nowe klasy w ramach tej kontrolki formularza. Dzięki temu możemy zmieniać style naszej kontrolki zależnie od tego, czy ma wpisane poprawne dane, czy została zaznaczona, czy jej wartość się zmieniła.
		  ![image.png](../assets/image_1722418821844_0.png)
	- **Reactive Forms** - formularze oraz związana z nimi logika są tworzone w pliku TypeScript. Umożliwiają dynamiczne tworzenie pól formularza.
- Json-server
  collapsed:: true
	- Instalacja
		- w PowerShellu wpisujemy komendę `npm install --save-dev json-server@0.17.4`. W pliku **package.json** w sekcji "devDependencies" doda nam się właściwa dependencja
		  ![image.png](../assets/image_1722593898408_0.png){:height 285, :width 396}
		- następnie w tym samym pliku **package.json** w sekcji **scripts** tuż pod **"start"** dodajemy:
		  ![image.png](../assets/image_1722594211648_0.png){:height 177, :width 556}
		- na samym końcu dodajemy plik **db.json** do naszego głownego folderu w projekcie, gdzie tworzymy nasze dane testowe zgodne z naszymi obiektami w aplikacji:
		  ![image.png](../assets/image_1722594389137_0.png){:height 211, :width 603}
	- Uruchomienie
		- otwieramy drugie okno w terminalu PowerShell i wpisujemy -> `npm run start:backend`