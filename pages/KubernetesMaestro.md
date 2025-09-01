collapsed:: true
1. K8s - teoria architektury

	- Jak działa Kubernetes?
		- ![k8s-control_plane.png](../assets/k8s-control_plane_1750927149036_0.png)
		  ![k8s-worker_nodes.png](../assets/k8s-worker_nodes_1750927297425_0.png) 
		  ![k8s-jak_dziala.png](../assets/k8s-jak_dziala_1750927667424_0.png)
	- Control plane (master nody) - szczegóły...
		- składa się z komponentów:
		  ![master_node-szczegoly.png](../assets/master_node-szczegoly_1750930344912_0.png){:height 282, :width 307}
			- apiServer
				- ![kube_apiserver.png](../assets/kube_apiserver_1750930464658_0.png){:height 143, :width 255}
			- scheduler
				- ![kube_scheduler.png](../assets/kube_scheduler_1750930965541_0.png){:height 168, :width 227}
			- controller-manager
				- ![kube_controller_manager.png](../assets/kube_controller_manager_1750930684749_0.png){:height 186, :width 248}
			- cloud-controller-manager
				- ![cloud_controller_manager.png](../assets/cloud_controller_manager_1750930825065_0.png){:height 121, :width 246}
			- etcd - baza danych która przechowuje stan całego klastra
				- ![etcd.png](../assets/etcd_1750930566160_0.png){:height 151, :width 245}
		- liczba master nodów powinna byc nieparzysta (najlepiej min. 3)
		  ![master_nodes-deatails.png](../assets/master_nodes-deatails_1750928647959_0.png)
			- Gdy cos pójdzie nie tak...
			  ![master_nodes-fail.png](../assets/master_nodes-fail_1750928785122_0.png){:height 167, :width 356}
			- Jak ma się do tego wspomniane *quorum*?
			  ![master_nodes-quorum.png](../assets/master_nodes-quorum_1750929002906_0.png)
			  wzór na *quorum* określa nam jak powinna byc minimalna ilość master nodów, aby zachować quorum dla bazy etcd
			- ![master_nody-deadlock.png](../assets/master_nody-deadlock_1750929371984_0.png)
			- ![master_nodes-nieparzysta_ilosc.png](../assets/master_nodes-nieparzysta_ilosc_1750929561732_0.png)
		- ![k8s_chmura.png](../assets/k8s_chmura_1750929794548_0.png){:height 143, :width 483}
		- ![k8s-wlasna_infra.png](../assets/k8s-wlasna_infra_1750929920301_0.png){:height 228, :width 478}
		-
	- Data plane (worker nody)
		- ![data_plane.png](../assets/data_plane_1750932147076_0.png){:height 264, :width 472}
			- kubelet
			  ![kubelet.png](../assets/kubelet_1750932550665_0.png){:height 167, :width 287}
			- kube-proxy
			  ![kube-proxy.png](../assets/kube-proxy_1750932638779_0.png){:height 193, :width 293}
			- container-runtime
			  ![container-runtime.png](../assets/container-runtime_1750932864812_0.png){:height 269, :width 291}
			  <<<<<<< HEAD
- collapsed:: true
  2. K8s - Big Picture
	- Pod - najmniejsza jednostka w K8s
	  collapsed:: true
		- ![image.png](../assets/image_1751532797528_0.png){:height 196, :width 416}
		  Sidecar - kontener z fragmentem kodu która agreguje logi z kontenera głównej aplikacji i np.przesyła je do zewn. systemu. Jest to mozliwe, że kontenery współdziela ten sam interfejs sieciowy.
		  ![image.png](../assets/image_1751533259429_0.png){:height 223, :width 669}
	- Kontener vs Pod
	  collapsed:: true
		- ![image.png](../assets/image_1751534866996_0.png)
		  ![image.png](../assets/image_1751534976175_0.png)
		- Pod w Dockerze
		  ![image.png](../assets/image_1751535242810_0.png)
		- *kubectl* w porównaniu do *Docker CLI*
		  ![image.png](../assets/image_1751535649122_0.png)
	- Format YAML
	  collapsed:: true
		- ```
		  --- # seperator jeśli definiujemy więcej niż jedą strukturę
		  
		  # struktura typu nazwa-wartość
		  apiVersion: v1 # wersja api
		  
		  # nazwa-wartość
		  kind: Pod # rodzaj obiektu
		  
		  # bardziej rozbudowana struktura typu nazwa-wartość
		  metadata:
		    name: hello-pod # spacje, zamiast tabów - zwykle dwie spacje
		    labels:
		      app: web
		      zone: prod
		      version: v1
		  
		  spec:
		    containers:
		      # lista, czyli inaczej sekwencja obiektów
		      # Przykład: 
		  
		      # args:
		      # - sleep
		      # - "1000"
		      # - message
		      # - "Friday, please!"
		  
		      # obiekt również może być strukturą typu nazwa-wartość
		      - name: front-end
		        image: dnaprawa/hello-kubernetes:1.0
		        ports:
		          # możemy robić zagnieżdżone listy
		          - containerPort: 80
		          # tutaj_mógłby_być_element_listy:
		          #   - a_tutaj_kolejne_zagnieżdzenie
		          #     kolejny_element:
		          #     kolejny_element:
		          #       - lista
		  
		      - name: backend # nazwa kontenera
		        image: image.registry.com/backend # obraz
		        ports: 
		          - containerPort: 8080 # na jakim porcie usługa działa w kontenerze
		  ---
		  apiVersion: v1
		  kind: Pod
		  metadata:
		    name: hello-pod-2 # spacje, zamiast tabów - zwykle dwie spacje
		    labels:
		      app: web-1
		      zone: prod-1
		      version: v1-1
		  ```
	- Podejście imperatywne vs deklaratywne
	  collapsed:: true
		- podejście imperatywne
		  ![image.png](../assets/image_1751537943064_0.png){:height 144, :width 464}
		- podejście deklaratywne
		  ![image.png](../assets/image_1751538059457_0.png)
	- ReplicatSet
		- Zadaniem K8s nie jest dbanie, by ten sam kontener działał ciągle i nieprzerwanie, lecz by ilość i stan kontenerów się zgadzała.
		  id:: 68665d7f-6074-4a91-a1e2-3f6847b6ca34
		  Zadanie to wykonuje jeden z podstawowych mechanizmów w Kubernetes - ReplicaSet.
		  ![image.png](../assets/image_1751539325056_0.png)
		- ![image.png](../assets/image_1751539668636_0.png)
		  ![image.png](../assets/image_1751539764223_0.png)
	-
- collapsed:: true
  3. Konfiguracja i wzorce
	- 3.1 Przekazywanie argumentów
	  collapsed:: true
		- ![image.png](../assets/image_1756125172754_0.png)
		- ![image.png](../assets/image_1756125238463_0.png)
		  ENTRYPOINT oraz CMD z dockerfile to odpowiednik "command" i "args" w pliku yaml w K8s
		- ![image.png](../assets/image_1756125413994_0.png)
		-
	- 3.2 Zmienne środowiskowe
	  collapsed:: true
		- ![image.png](../assets/image_1756125849255_0.png)
		- ![image.png](../assets/image_1756125926880_0.png)
		- ![image.png](../assets/image_1756126028046_0.png)
	- 3.3 Sposoby na przekazywanie konfiguracji do kontenerów
	  collapsed:: true
		- ![image.png](../assets/image_1756193031415_0.png)
		- ![image.png](../assets/image_1756193184773_0.png)
		- ![image.png](../assets/image_1756193460079_0.png)
		- ![image.png](../assets/image_1756193562597_0.png)
	- 3.4 Przekazywanie konfiguracji - Sposób 1 - ConfigMaps
		- ![image.png](../assets/image_1756193979665_0.png)
		- ![image.png](../assets/image_1756194093331_0.png)
		- ![image.png](../assets/image_1756194142527_0.png)
		-
-
-