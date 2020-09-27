# Projet RI partie 2
Ce repo contient les packages de la deuxième partie du projet.

### part_two_urdf
Ce package l'urdf d'une du robot quadruped ainsi qu'un launch file pour visualizer le robot.

### udm_project_moveitconfig
Ce package a été généré avec moveit.

### udm_project_control
Ce package contient les noeuds, les services et les launch file nécéssaire pour déplacer le robot en ligne droite, à droite, à gauche et en arrière. 

## Installation
Pour installer ce noeud il faut le cloner dans le dossier src de votre catkin workspace (catkin_ws).

```
cd catkin_ws/src
git clone https://github.com/IF488/MIAR_ROS_1.git
catkin build
cd ..
source devel/setup.bash
```
## Execution 
### Visualiser la jambe
Pour visualiser, il faut executer le code suivant dans le terminal de votre workspace:

```
source devel/setup.bash
roslaunch part_two_urdf simulate.launch
```
### Controler la jambe à l'aide de la cinématique directe

Dans le premier terminal de votre catkin workspace:
```
source devel/setup.bash
roslaunch udm_project_moveitconfig demo.launch
```

Dans le deuxième terminal de votre catkin workspace:
```
source devel/setup.bash
roslaunch udm_project_control control.launch
```

Dans le troisième terminal de votre catkin workspace:
```
source devel/setup.bash
rosservice call /control "mouvement:
 data: 'front'"
```
NB: Vous pouvez choisir les valeurs suivantes: 'front' , 'right' , 'left' , 'back'. 
