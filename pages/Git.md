- Połączenie się ze swoim repozytorium (aby nie ciągle wpisywać hasła po pushu do repo)
	- https://stackoverflow.com/questions/6565357/git-push-requires-username-and-password
	  **git remote set-url origin git@github.com:username/repo.git**
	  **git remote -v**
	  https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh
- Ustawienie użytkownika GitHub lokalnie
  collapsed:: true
	- https://stackoverflow.com/questions/22844806/how-to-change-my-git-username-in-terminal
	- In your terminal, navigate to the repo you want to make the changes in.
	- Execute `git config --list` to check current username & email in your local repo.
	- Change username & email as desired. Make it a global change or specific to the local repo: 
	  
	  `git config --global user.name "Full Name"`
	  
	  `git config --global user.email "email@address.com"`
	  
	  Per repo basis you could also edit `.git/config` manually instead.
	- Done!
- ((66bc86a6-71f9-4b67-9023-7bb868b2a44b))
-
-