Deux Jupyter Notebook A et B (2 manières de faire)  pour analyser les données. 


Dans le Jupyter Notebook A, j’ai encodé avec TF-IDFou Doc2Vec et essayé les algos : régression logistique, Random Forest et  XGBoost. Je n’ai pas beaucoup modifié les paramètres par défaut. 

La meilleure accuracy et qui est restée  faible est de 0.42  obtenue avec TF-IDF combiné à  Random Forest.  

Je sais que le problème vient en partie  de la difficulté à nettoyer les données pour mettre en valeur les mots spécifiques à chaque catégorie. Voyant que la liste des stopwords utilisée (français) était très limitée, j’ai créé une stoplist supplémentaire où j’ai ajouté des mots qui me semblaient bons à supprimer. J’ai recalculé les accuracy en prenant compte de cette stoplist mais ca n’a pas amélioré le modèle. 

Accuracy		                      Avant stoplist	  Apres stoplist
Doc2Vec	  Regeression logistique	  	0.2234	        	0.2224
	        Random Forest	            	0.1972	        	0.1957
	        XGBoost	                  	0.1972	        	0.2446
			
Tf-Idf	  Regeression logistique	  	0.4093	        	0.3858
	        Random Forest	            	0.4192	        	0.3873
	        XGBoost	                  	0.4139	        	0.3814



Dans le Jupyter Notebook B, j’ai encodé les questions avec un Tokenizer de Keras et transformé les intentions avec OneHotEncoder. Les modèles utilisés sont RNN (Bidirectional GRU Gated Recurrent Unit), regression logistique et XGBoost.


Accuracy	
RNN	                      	0.37 a l’epoch 28 (a partir de la, modele non ameliore)
Regeression logistique	  	0.22
XGBoost	                  	0.32
