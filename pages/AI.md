- Prompty AI
  collapsed:: true
	- Wdrożenie mikroserwisów na MiniPC
	  collapsed:: true
		- W pierwszym kroku chciałbym wdrożyć aplikację mikroserwisową na server. 
		  Server byłby niskonapieciowym miniPC w moim domu który byłby podłaczony 
		  do domowej sieci. 
		  W drugim kroku chciałbym się połączyć z wdrożoną aplikacją 
		  mikroserwisową z innego kumputera który byłby w tej samej sieci domowej.
		  Jak wykonać oba kroki?
- Jak skonfigurować lokalnie AI (OPEN-WEBUI + ollama3)
	- docker run -d -p 1000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
	- install wsl in your PowerShell:
	  wsl --install
	- start Ubuntu by typing in PS:
	  Ubuntu
	  ollama run llama3
	- To exit ollama type:
	  /bye
	- To exit Ubuntu type:
	  exit