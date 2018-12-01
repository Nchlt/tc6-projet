# Criteo-Display-Ad-by-Mllib-Spark

Le rapport du projet se trouve dans le notebook rapport.

Quelques notes concernant le notebook Experiences:

1) "A la limite de resources, il est très couteux au niveau de temps d'execution avec RandomForest pour les colonnes categorielle ayant trop de valeurs discretes. Donc, nous ne garderions que les colonnes qui a moins de 4000 valeurs pour entrainement."
This code used to remove some oversized , but if your computer is powerful , do not run this part of code or just remove it.

2) If you do not remove above , you must modify "col_now" variable such that:
cols_now = cols_now = ['i1','i2','i3','i4','i5','i6','i7','i8','i9','i10','i11','i12','i13','c1_index','c2_index','c3_index','c4_index',\
	'c5_index','c6_index','c7_index','c8_index','c9_index','c10_index','c11_index','c12_index','c13_index',\
	'c14_index','c15_index','c16_index','c17_index','c18_index','c19_index','c20_index','c21_index','c22_index','c23_index',\
	'c24_index','c25_index','c26_index']

3) And you must modify:
rf = RF(labelCol='labelIndex', featuresCol='features', numTrees=200, maxBins=160000)
because maximum number of discrete values of one column is 160000 instead of 4000. The same modification of "maxBins" for GradientBoostTree and K-Fold
