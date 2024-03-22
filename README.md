# Network_Analysis

Data description : 


Le jeu de données a été produit à partir des fichiers de dumps de données liées .rdf du triplestore Persée, disponibles à l'adresse https://data.persee.fr/explorer/demander-un-dump/dumps-collections/


Les fichiers contiennent les métadonnées bibliographiques des documents de chacune des collections de Persée.


Les métadonnées bibliographiques originales ont été filtrées et allégées en conséquence :
- exclusion de la collection "Archives Parlementaires" (hors scope et trop volumineuse) ;
- exclusion des collections bhe, sgeol et shf (dump défectueux) ;
- collection shom limitée à 255 documents (dump défectueux) ;
- données de documents uniquement ;
- manifestations numériques uniquement.


Etat des données documentaires : octobre 2021.


La correspondance entre collection et discipline utilise les codes de collection Persée (collection_id).
Le collection_id ne fait l'objet d'aucune colonne spécifique.
On le trouve dans le nom des documents car les documents sont nommés de manière systématique, sous la formule :
<collection_id>_<ISSN>_<année de publication print>_<code de type de fascicule>_<volume>_<numéro>_<données supplémentaires de localisation/identification>


Ex: assr_0335-5985_1989_num_67_2_1390_t1_0308_0000_1
code collection = assr
ISSN = 0335-5985
date de publication = 1989
code de type de fascicule = num
volume = 67
numéro = 2
autres données de localisation/identification : page 308 etc




Dependencies
Pour fonctionner, le code nécessite les modules Python suivants


* Numpy/Scipy
* Matplotlib
* Pandas
* Scikit-Learn 


Requirements


Pour commencer assurez vous d’avoir ces librairies : 


* Pour manipuler ton dataset : 


import pandas as pd
import numpy as np
import math
import networkx as nx




* Pour tout ce qui est visualisation : 
Il faudra l’installer pour le clustering 
!pip install python-louvain
import matplotlib.pyplot as plt


* Méthodes pour représenter les traitement textuels


from scipy.sparse import csr_matrix
from numpy import linalg as LA
import community  
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.feature_extraction.text import CountVectorizer
from scipy.sparse import find, csr_matrix


from scipy.linalg import norm
