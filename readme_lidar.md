Lastools - LIDAR LAS / LAZ
------

### Définition

Librairie pour utilisation des données LIDAR.

Format LAS. LAZ compressé.

Partie de la librairie capable de traiter les données LAS bas niveau.

Certains outils sont Open source et d'autres sont sous licence.

## LASTools

### Installation sur Windows :

1.    create directory "c:\lastools"
2.    unzip LAStools.zip to this directory
3.    run the LAStools executables

En parallèle, installer le plugin sur QGIS. Redémarrer QGIS et paramétrer Préférences > Option

![](img/qgis_activer_lastools.png)



### Installation Linux - Debian

[https://github.com/LAStools/LAStools](https://github.com/LAStools/LAStools)



```bash
mkdir lastools
```

```bash
cd lastools
```

```bash
wget https://downloads.rapidlasso.de/LAStools.tar.gz
```

```bash
tar xvzf LAStools.tar.gz
```

```bash
rm LASTools.tar.gz
```

> Installation dépendances

```bash
sudo apt-get install libjpeg62 libpng-dev libtiff-dev libjpeg-dev libz-dev libproj-dev liblzma-dev libjbig-dev libzstd-dev libgeotiff-dev libwebp-dev liblzma-dev libsqlite3-dev
```

> Ajout du dossier data/lib dans le PATH

```bash
export LD_LIBRARY_PATH=./lib:$LD_LIBRARY_PATH
```

> Exécution des programmes depuis lastools/bin

./


### Les OUTILS LASTools

> Vue rapide sur les outils Open Source et free

https://rapidlasso.de/product-overview/

>lasinfo64

sortie de toutes les informations sur la sortie standard

	./lasinfo64 -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz

>lascopcindex64

Cloud Optimized Point Cloud => permet une utilisation plus légére dans QGIS

	./lascopcindex64 -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz -o out.copc.laz

> lasindex64
Création d'un fichier d'index .lax (ajouter -append pour le recalculer)

	 ./lasindex64 -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz
	 
> lasmerge64 avec option -split 

	lasmerge64 -i *.laz -o out0000.las -split 1000000000

> las2dem
WARNING=> unlicensed. over 1.5 million points. inserting black diagonal.
	 
	./las2dem64 -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz -elevation -o mnt_test.asc

>lasprecision (https://downloads.rapidlasso.de/html/lasprecision_README.html)

	./lasprecision64 -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz

>lasdistance (https://downloads.rapidlasso.de/html/lasdistance_README.html)

	./lasdistance64 -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz -poly manip_aveyron/vecteur/lignes_rff_2154.shp -distance_xy 200 -remove_points -o lidarhd_najac/decoup.laz
	 
>lasground


#### Ressources

https://github.com/LAStools/LAStools

https://lastools.github.io/

https://rapidlasso.de/product-overview/

https://rapidlasso.de/lastools-as-qgis-plugin/
