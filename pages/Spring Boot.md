### Pytania rekrutacyjne
	- **1. Czym jest Spring?**
	  collapsed:: true
		- Spring to framework do tworzenia aplikacji w Javie,  oferujący m.in. kontener IoC, wstrzykiwanie zależności, programowanie  aspektowe i wiele modułów ułatwiających tworzenie aplikacji.
		- Źródło:
		  https://docs.spring.io/spring-framework/docs/3.2.x/spring-framework-reference/html/overview.html
		  ![image.png](../assets/image_1720514429168_0.png){:height 454, :width 523}
		-
	- **2. Czy Spring i Spring Boot to to samo?**
	  collapsed:: true
		- Spring i Spring Boot to nie to samo. Spring Boot to projekt 
		  zbudowany na bazie Spring Framework, który ułatwia tworzenie aplikacji 
		  Spring poprzez automatyczną konfigurację
	- **3. Na jakim porcie uruchamiana jest domyślnie springbootowa aplikacja? Czy można go zmienić?**
	  collapsed:: true
		- Domyślny port dla aplikacji Spring Boot to **8080**. Można go zmienić np. w pliku application.properties za pomocą wpisu **server.port: 9090**
	- **4. Co to jest Bean?**
	  collapsed:: true
		- Jaki scope może mieć bean w Springu?
			- Jaki jest domyślny scope dla beanów springowych?
			- Czy bean mający scope Singleton jest bezpieczny w środowisku wielowątkowym/jest thread-safe?
			- Co to jest wstrzykiwanie zależności (dependency injection)?
			- Jakie znasz sposoby wstrzykiwania zależności? Który jest preferowany?
			- Jaka jest różnica między adnotacjami @Autowired oraz @Inject?
			- Czy adnotacja @Autowired jest obowiązkowa w przypadku wstrzykiwania przez konstruktor?
			- W jaki sposób możemy wstrzyknąć wartość jakiegoś property, np. spring.datasource.url?
			- Do czego służy adnotacja @PostConstruct?
			- Do czego służy adnotacja @Profile?
			- Co dają nam profile springowe?
			- Jaka jest różnica między adnotacjami @Qualifier oraz @Primary? Która ma pierwszeństwo?
			- Co to jest DispatcherServlet?
			- Czy możemy mieć w controllerze dwie metody z adnotacją @GetMapping i taką samą ścieżką, np. /number?
			- Jaka jest różnica między adnotacjami @PathVariable i @RequestParam?
			- Czy możemy zmapować metodę HTTP DELETE na dodawanie użytkowników w bazie danych?
			- Czym się różnią Filter oraz HandlerInterceptor?
			- Do czego służy adnotacja @ExceptionHandler? Czy możemy użyć jej globalnie dla wszystkich controllerów?
			- Czy przechwytywanie wyjątków w komponencie z adnotacją @ControllerAdvice dotyczy wszystkich controllerów?
			- Po co nam mechanizm migracji bazy danych? Jakie narzędzia do tego celu wspiera Spring Boot?
			- Czy interfejs JpaRepository jest parametryzowany? Jeśli tak, to jakie parametry typu wymaga?
			- Do czego służy klasa JdbcTemplate?
			- Co to są poziomy izolacji transakcji? Wymień je i krótko omów.
			- Jakie rodzaje propagacji transakcji są dostępne w springu?
			- Jeśli w trakcie procesowania metody oznaczonej adnotacją 
			  @Transactional zostanie rzucony wyjątek, to będzie miał miejsce rollback
			  czy nie?
			- W jaki sposób możemy opublikować zdarzenie w springu?
			- Czy metoda oznaczona adnotacją @EventListener może coś zwracać czy musi być void? Jakie to ma konsekwencje?
			- Z jakiego CacheManagera domyślnie korzysta Spring?
			- Do czego służy klasa RestTemplate?
			- Do czego służą adnotacje takie jak @Before, @Around, @After?
			- Czy kojarzysz adnotacje takie jak @Email, @Max, @Min, @Null, @Pattern? Do czego one służą?
		- Jaki scope może mieć bean w Springu?
			- Jaki jest domyślny scope dla beanów springowych?
			- Czy bean mający scope Singleton jest bezpieczny w środowisku wielowątkowym/jest thread-safe?
			- Co to jest wstrzykiwanie zależności (dependency injection)?
			- Jakie znasz sposoby wstrzykiwania zależności? Który jest preferowany?
			- Jaka jest różnica między adnotacjami @Autowired oraz @Inject?
			- Czy adnotacja @Autowired jest obowiązkowa w przypadku wstrzykiwania przez konstruktor?
			- W jaki sposób możemy wstrzyknąć wartość jakiegoś property, np. spring.datasource.url?
			- Do czego służy adnotacja @PostConstruct?
			- Do czego służy adnotacja @Profile?
			- Co dają nam profile springowe?
			- Jaka jest różnica między adnotacjami @Qualifier oraz @Primary? Która ma pierwszeństwo?
			- Co to jest DispatcherServlet?
			- Czy możemy mieć w controllerze dwie metody z adnotacją @GetMapping i taką samą ścieżką, np. /number?
			- Jaka jest różnica między adnotacjami @PathVariable i @RequestParam?
			- Czy możemy zmapować metodę HTTP DELETE na dodawanie użytkowników w bazie danych?
			- Czym się różnią Filter oraz HandlerInterceptor?
			- Do czego służy adnotacja @ExceptionHandler? Czy możemy użyć jej globalnie dla wszystkich controllerów?
			- Czy przechwytywanie wyjątków w komponencie z adnotacją @ControllerAdvice dotyczy wszystkich controllerów?
			- Po co nam mechanizm migracji bazy danych? Jakie narzędzia do tego celu wspiera Spring Boot?
			- Czy interfejs JpaRepository jest parametryzowany? Jeśli tak, to jakie parametry typu wymaga?
			- Do czego służy klasa JdbcTemplate?
			- Co to są poziomy izolacji transakcji? Wymień je i krótko omów.
			- Jakie rodzaje propagacji transakcji są dostępne w springu?
			- Jeśli w trakcie procesowania metody oznaczonej adnotacją 
			  @Transactional zostanie rzucony wyjątek, to będzie miał miejsce rollback
			  czy nie?
			- W jaki sposób możemy opublikować zdarzenie w springu?
			- Czy metoda oznaczona adnotacją @EventListener może coś zwracać czy musi być void? Jakie to ma konsekwencje?
			- Z jakiego CacheManagera domyślnie korzysta Spring?
			- Do czego służy klasa RestTemplate?
			- Do czego służą adnotacje takie jak @Before, @Around, @After?
			- Czy kojarzysz adnotacje takie jak @Email, @Max, @Min, @Null, @Pattern? Do czego one służą?
		- Bean to obiekt zarządzany przez kontener IoC Springa
	- Jaki scope może mieć bean w Springu?
	- Jaki jest domyślny scope dla beanów springowych?
	- Czy bean mający scope Singleton jest bezpieczny w środowisku wielowątkowym/jest thread-safe?
	- Co to jest wstrzykiwanie zależności (dependency injection)?
	- Jakie znasz sposoby wstrzykiwania zależności? Który jest preferowany?
	- Jaka jest różnica między adnotacjami @Autowired oraz @Inject?
	- Czy adnotacja @Autowired jest obowiązkowa w przypadku wstrzykiwania przez konstruktor?
	- W jaki sposób możemy wstrzyknąć wartość jakiegoś property, np. spring.datasource.url?
	- Do czego służy adnotacja @PostConstruct?
	- Do czego służy adnotacja @Profile?
	- Co dają nam profile springowe?
	- Jaka jest różnica między adnotacjami @Qualifier oraz @Primary? Która ma pierwszeństwo?
	- Co to jest DispatcherServlet?
	- Czy możemy mieć w controllerze dwie metody z adnotacją @GetMapping i taką samą ścieżką, np. /number?
	- Jaka jest różnica między adnotacjami @PathVariable i @RequestParam?
	- Czy możemy zmapować metodę HTTP DELETE na dodawanie użytkowników w bazie danych?
	- Czym się różnią Filter oraz HandlerInterceptor?
	- Do czego służy adnotacja @ExceptionHandler? Czy możemy użyć jej globalnie dla wszystkich controllerów?
	- Czy przechwytywanie wyjątków w komponencie z adnotacją @ControllerAdvice dotyczy wszystkich controllerów?
	- Po co nam mechanizm migracji bazy danych? Jakie narzędzia do tego celu wspiera Spring Boot?
	- Czy interfejs JpaRepository jest parametryzowany? Jeśli tak, to jakie parametry typu wymaga?
	- Do czego służy klasa JdbcTemplate?
	- Co to są poziomy izolacji transakcji? Wymień je i krótko omów.
	- Jakie rodzaje propagacji transakcji są dostępne w springu?
	- Jeśli w trakcie procesowania metody oznaczonej adnotacją @Transactional zostanie rzucony wyjątek, to będzie miał miejsce rollback czy nie?
	- W jaki sposób możemy opublikować zdarzenie w springu?
	- Czy metoda oznaczona adnotacją @EventListener może coś zwracać czy musi być void? Jakie to ma konsekwencje?
	- Z jakiego CacheManagera domyślnie korzysta Spring?
	- Do czego służy klasa RestTemplate?
	- Do czego służą adnotacje takie jak @Before, @Around, @After?
	- Czy kojarzysz adnotacje takie jak @Email, @Max, @Min, @Null, @Pattern? Do czego one służą?