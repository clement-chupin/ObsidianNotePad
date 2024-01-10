

- C++ / Python / R / Matlab
- Ubuntu 16.04 / 18.04 / 20.04 / 22.04
- Windows ???
- Ros melodic / noetic / humble / kinetic ....
- Décentraliser les projets ?



Ground Segmentation méthode : 
[[Erasor, Patchwork, Patchwork++]]
[[Ground Segmentation State of art]]



Github similaires :

https://github.com/url-kaist/Ground-Segmentation-Benchmark/tree/main


Quid du partage de dataset ?
Pourquoi partager et adapter du code quand on peut simplement partager les résultats sur un dataset en particulier ?!?

Les 2 peuvent difficelement subsister en face de dataset égémonique tel que kitti ou roughdataset,



Objectif 1 : 
Popularize our dataset
Rendre facile et répétable le test d'algos extérieurs

## Virtual Env, Launcher, Bridge :

Virtual Env :
- Ros/Ubuntu version
- Keep additionnal packages (C++, Python)

Launcher :
- For every project, launch the code associate to the ground segmentation methode

Bridge :
- Can be incorporate to the Launcher
- Convert the topic, the node, the ros version, the rosbag version....





