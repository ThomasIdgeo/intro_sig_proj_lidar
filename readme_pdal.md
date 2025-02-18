PDAL 
-----

![](img/pdal_logo.png)

[https://pdal.io/](https://pdal.io/)

[]()

### Installation PDAL

**Définition**

> Point Data Abstraction Library

- Comment utiliser PDAL
	- en mode CLI
	- python avec Numpy
	- API C++
	- Intégré à QGIS depuis version 3.34
	- pipelines json
	
> Différences avec LASTools

	1. Tous les composants de la librairie sont diffusés sous licence libre.
	2. PDAL manipule tous les formats de nuages de points autre que .las
	3. Un repo github https://github.com/PDAL/PDAL
	


https://docs.anaconda.com/miniconda/install/#quick-command-line-install

Conda est un utilitaire de gestion de paquet.

Miniconda est libre, installation minimaliste de distribution Conda qui inclue Conda, Python, les packages de dépendances et
 un petit nombre de packages utiles.

- Création du répertoire dans le home de l'utilisateur courant

```bash
mkdir -p ~/miniconda3 && cd ~/miniconda3
```

- Téléchargement du script d'installation (-> renommer miniconda.sh)

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh 
```

- Exécution de script d'installation (en mode silencieux)
```bash
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
```

- On efface le script d'installation
```bash
rm ~/miniconda3/miniconda.sh
```

- On rafraichi pour activer l'installation
```bash
source ~/miniconda3/bin/activate
```

- initialisation de conda dans tous les terminaux
```bash
conda init --all
```



- **Création de l'environnement de travail**, incluant PDAL
```bash
conda create --yes --name envidgeo --channel conda-forge pdal
```

- Info sur les env de travail
```bash
conda info --envs
```

- On bascule dessus
```bash
conda activate envidgeo
```

*(envidgeo) thomas@PCP-Thomas:~$*

- Mise à jour de PDAL
```bash
conda update pdal
```

- Les drivers > **On distingue les filters, les writers, le readers**
```bash
pdal --drivers
```

```{note}
L'aide contextuelle
	`pdal <command> --help`
```


### Manipulations

crop, colorinterp, colorization (avec une ortho), geomdistance, reprojection, splitter


- 
```bash
$ pdal info myfile.las
$ pdal translate input.las output.las
$ pdal pipeline --stdin < pipeline.json
```

- SPlit pour répartir la charge entre plusieurs fichiers au format Binary Point File .bpf
```bash
pdal split --capacity 5000000 LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz split/out.bpf
```

- pdal ground permet d'extraire le sol par exemple
```bash
pdal ground --extract "Classification=2" -i LHD_FXX_0618_6346_PTS_C_LAMB93_IGN69.copc.laz -o extract_2.laz
```

- Création d'un MNT
```bash

```

- Utilisation du pipeline pour réaliser une chaine de traitement

> Traitement simple d'une entrée (reader), filtres crop sur un extent (filter) vers une sortie (writers)
```bash
pdal pipeline --stdin < pipeline_test.json
```

> Traitement crop avec shape + reprojection en json 
```bash

```

