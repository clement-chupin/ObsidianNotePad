All command for romea_furrow_training :

```bash
roslaunch romea_furrow_training gen_data_furrow_all.launch 
	demo:=simu / replay           #use simulation or replay .bag record
	gen_mode:= "random" / "traj"  #robot follow traj or move random around the traj
	realistic_world:=true         #irregular ground with weeds and rocks
	dataset_path:="dataset path"  #path to store dataset
	dataset_name:="name"          #name of dataset saved
	overwrite_dataset:=true       #delete the last dataset, or keep and increment it with new data
	record:=true                  #record on our dataset or not
```


```bash
roslaunch romea_furrow_training eval_furrow_all.launch.launch
	eval_mode
    demo:="simu" / "replay"           #use simulation or replay .bag record
    realistic_world:=true             #irregular ground with weeds and rocks (specific to traj evaluation, robust evaluation have its owns worlds)
	dataset_path:="dataset path"      #path to store dataset
	dataset_name:="name"              #name of dataset saved
    overwrite_dataset:=true / false   #delete the last dataset, or keep and increment it with new data
    record:= true                     #record on our dataset or not
    id_run:= "000"                    #id to store the specific run, usefull to plot the result with variation of paramteres
    eval_mode:= "traj" / "robust"     #eval the precision of following, of the winrate of trajectory sucessfully followed
```



gen_mode and eval_mode are just intermediate parameters to setup the furrow_trainer_mode, with these options :
```bash
furrow_trainer_mode:= 
	"random_gen", #generate a dataset by robot random moves around traj
	"traj_gen", #generate a dataset by robot following traj
	"traj_eval", #test and register the furrow following a curve
	"robust_eval", #test the following of row in market_gardening, eval manually the winrate
```



