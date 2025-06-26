- 1. K8s - teoria architektury
	- Jak działa Kubernetes?
	  collapsed:: true
		- ![k8s-control_plane.png](../assets/k8s-control_plane_1750927149036_0.png)
		  ![k8s-worker_nodes.png](../assets/k8s-worker_nodes_1750927297425_0.png) 
		  ![k8s-jak_dziala.png](../assets/k8s-jak_dziala_1750927667424_0.png)
	- Control plane (master nody) - szczegóły...
	  collapsed:: true
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
	  collapsed:: true
		- ![data_plane.png](../assets/data_plane_1750932147076_0.png){:height 264, :width 472}
			- kubelet
			  ![kubelet.png](../assets/kubelet_1750932550665_0.png){:height 167, :width 287}
			- kube-proxy
			  ![kube-proxy.png](../assets/kube-proxy_1750932638779_0.png){:height 193, :width 293}
			- container-runtime
			  ![container-runtime.png](../assets/container-runtime_1750932864812_0.png){:height 269, :width 291}
-