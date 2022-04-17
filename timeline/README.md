4/16/2022 8:10:23 PM: previous repositories:
https://github.com/neilsambhu/carla-simulator3
https://github.com/neilsambhu/carla-simulator4

4/16/2022 8:11:00 PM: create remote branch NeilBranch0
```
git checkout -b NeilBranch0
```
```
git branch
```
Maybe:

	Useful when pushing a new branch, this creates an upstream tracking branch with a lasting relationship to your local branch:
	```
	git push -u origin [branch]: 
	```
	https://stackoverflow.com/a/68781050 > Create Personal Access Token on GitHub
	From your GitHub account, go to Settings => Developer Settings => Personal Access Token => Generate New Token (Give your password) => Fillup the form => click Generate token => Copy the generated Token, it will be something like ghp_sFhFsSHhTzMDreGRLjmks4Tzuzgthdvfsrta
	```
	$ git config --global user.name "your_github_username"
	$ git config --global user.email "your_github_email"
	$ git config -l
	```
	```
	git push origin NeilBranch0
	Username: <type your username>:neilsambhu
	Password: <type your password or personal access token (GitHub)>
	```
4/16/2022 9:13:30 PM: add remote "github.com/neilsambhu/scenario_runner"
```
(base) nsambhu@SAMBHU19:~/github/scenario_runner$ git remote
origin
(base) nsambhu@SAMBHU19:~/github/scenario_runner$ git remote add neil_scenario_runner git@github.com:neilsambhu/scenario_runner.git
(base) nsambhu@SAMBHU19:~/github/scenario_runner$ git remote
neil_scenario_runner
origin
(base) nsambhu@SAMBHU19:~/github/scenario_runner$ git remote -v
neil_scenario_runner	git@github.com:neilsambhu/scenario_runner.git (fetch)
neil_scenario_runner	git@github.com:neilsambhu/scenario_runner.git (push)
origin	https://github.com/carla-simulator/scenario_runner.git (fetch)
origin	https://github.com/carla-simulator/scenario_runner.git (push)
```
4/16/2022 9:20:49 PM: push
```
git commit -a -m "update timeline"&&git push neil_scenario_runner NeilBranch0 
```