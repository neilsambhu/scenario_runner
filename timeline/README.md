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
4/16/2022 9:45:28 PM: re-run distance_between_vehicles.py
```
(carla-test) nsambhu@SAMBHU19:~/github/scenario_runner$ python scenario_runner.py --scenario FollowLeadingVehicle_1 --record records --reloadWorld
scenario_runner.py:94: DeprecationWarning: distutils Version classes are deprecated. Use packaging.version instead.
  if LooseVersion(dist.version) < LooseVersion('0.9.12'):
Preparing scenario: FollowLeadingVehicle_1
ScenarioManager: Running scenario FollowVehicle
All scenario tests were passed successfully!
Destroying ego vehicle 554
ERROR: failed to destroy actor 554 : unable to destroy actor: not found 
No more scenarios .... Exiting
```
```
(carla-test) nsambhu@SAMBHU19:~/github/scenario_runner$ python metrics_manager.py --log records/FollowLeadingVehicle_1.log --criteria records/FollowLeadingVehicle_1.json --metric srunner/metrics/examples/distance_between_vehicles.py
```
Output image stored at /home/nsambhu/github/scenario_runner/srunner/metrics/data/DistanceBetweenVehicles.png and https://github.com/neilsambhu/scenario_runner/blob/NeilBranch0/srunner/metrics/data/DistanceBetweenVehicles.png.

Absolute image path:

![](https://github.com/neilsambhu/scenario_runner/blob/NeilBranch0/srunner/metrics/data/DistanceBetweenVehicles.png)

Relative image path:

![](../srunner/metrics/data/DistanceBetweenVehicles.png)

4/16/2022 11:00:51 PM: adding adversarial texture to one object in CARLA
```
(carla-test) nsambhu@SAMBHU19:~/github/scenario_runner$ python scenario_runner_NeilBranch0.py --scenario FollowLeadingVehicle_1 --record records --reloadWorld
scenario_runner_NeilBranch0.py:94: DeprecationWarning: distutils Version classes are deprecated. Use packaging.version instead.
  if LooseVersion(dist.version) < LooseVersion('0.9.12'):
Neil got here 1
Altering texture for object: Road_Road_Town01_372
image.shape (233, 216, 3)
Traceback (most recent call last):
  File "scenario_runner_NeilBranch0.py", line 641, in main
    result = scenario_runner.run()
  File "scenario_runner_NeilBranch0.py", line 545, in run
    result = self._run_scenarios()
  File "scenario_runner_NeilBranch0.py", line 485, in _run_scenarios
    result = self._load_and_run_scenario(config)
  File "scenario_runner_NeilBranch0.py", line 389, in _load_and_run_scenario
    if not self._load_and_wait_for_world(config.town, config.ego_vehicles):
  File "scenario_runner_NeilBranch0.py", line 357, in _load_and_wait_for_world
    self.adversarial_textures(bVerbose)
  File "scenario_runner_NeilBranch0.py", line 326, in adversarial_textures
    self.world.apply_color_texture_to_object(target_object, carla.MaterialParameter.Diffuse, texture, 0)
Boost.Python.ArgumentError: Python argument types in
    World.apply_color_texture_to_object(World, str, MaterialParameter, TextureColor, int)
did not match C++ signature:
    apply_color_texture_to_object(carla::client::World {lvalue}, std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> > object_name, carla::rpc::MaterialParameter material_parameter, carla::rpc::Texture<carla::sensor::data::Color> texture)
```
4/16/2022 11:04:41 PM: change "a" to use int constructor; same error.