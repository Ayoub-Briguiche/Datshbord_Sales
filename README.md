

Ce tableau de bord vise à intégrer les données de vente par produit et par client, tout en permettant une comparaison des performances par rapport au budget. L'objectif est également d'offrir des filtres personnalisés par vendeur, produit et client, afin de faciliter une analyse détaillée et ciblée.

![Picture38](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/9353186f-bcd3-41f6-b98d-e9f9cc737588)

### Étapes suivies

- Étape 1 : Charger les données dans Power BI Desktop, l'ensemble de données étant 3 fichiers .CSV et un fichier .xlsx.

- Étape 2 : Créer une modélisation de données en établissant des liaisons entre les tables de dimension et les tables de fait.

![1](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/ce2b2200-8e8b-4aa5-97a9-62d956dbb641)



- Étape 3 : Vérifier les types de données pour chaque colonne et les corriger selon le type adéquat. Nous avons remarqué que la colonne "SalesAmount" était de type texte alors qu'il s'agit d'un nombre décimal. Après vérification, nous avons constaté que nous devions remplacer les points (.) dans toute la colonne par des virgules (,).
          
      SalesAmount = Table.AddColumn(#"Texte inséré après le délimiteur", "Personnalisé", each [Texte avant le délimiteur]& "," & [Texte après le délimiteur])

- Étape 4 : Création des mesures nécessaires, notamment la différence entre les ventes réelles et le budget ('Sales' - 'Budget'), ainsi que le rapport entre les ventes et le budget ('Sales' / 'Budget') pour permettre une comparaison des performances.
      
      Sales-Budget = [Sales] - [Budget Amount]

      Sales/Budget Amount = DIVIDE([Sales],[Budget Amount])


- Étape 5 : Mise en place des filtres pour les années ('Year'), les mois ('Month'), les catégories de produits ('Category'), ainsi que la personnalisation des filtres par vendeur, produit et client.

    ![2](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/2eabf40c-f97c-4962-b3b9-81fa7583a4b1)





- Étape  6 : la mise en place des visualisation adéquates :
    
  1-Pour présenter le KPI, nous avons téléchargé une visualisation "dynamic KPI Card by Sereviso", dans laquelle nous avons ajouté les ventes ("Sales") comme indicateur, le budget comme première variable de comparaison, et la différence entre les ventes et le budget comme deuxième variable de comparaison.

![3](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/e6a3812a-de91-4b16-83f4-52d854a8b0ef)



   2-Pour les ventes par catégorie de produit, nous avons utilisé un graphique en anneau dans lequel nous avons ajouté les ventes ("Sales") comme valeur et la catégorie de produit comme légende. Selon le graphique, 94% des ventes sont des vélos, ce qui reflète la spécialité de l’entreprise, tandis que les accessoires représentent 4%.

 ![22](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/c84670a5-e8f6-42bb-8724-66bd6f8c7207)


  
  3-Pour les ventes et les budgets par mois, il est utile de visualiser l’évolution et les tendances au cours d’une année. Généralement, on observe une tendance similaire pour les deux variables, à l'exception de périodes où les ventes surpassent le budget, comme en juin et novembre 2020, ce qui dénote une performance solide durant ces périodes.

![4](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/5b0ba5ac-b6e3-44e4-b0f5-3811e45a1441)



  4-Pour illustrer les ventes de chaque client, nous avons opté pour un graphique à barres empilées, en restreignant la sélection aux dix principaux clients. En 2020, les trois meilleurs clients étaient "Jordon Turner", "Maurice Shan" et "Janet Munoz".

  ![5](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/7c33ae03-3cca-49e3-a53c-c4d7e329bc45)


  5-De même, pour la présentation des ventes par produit, les trois produits les plus performants étaient le "Mountain 200 Black 42", le "Mountain 200 Black 38" et "le Mountain 200 Silver".

![6](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/98cb4362-dd00-41b3-b0dd-958a2aa2670c)


  
  6-Pour localiser les villes et les pays des consommateurs, nous avons utilisé un graphe de type carte. À travers cette carte, nous avons remarqué que les clients sont principalement issus d'Europe en premier lieu, puis d'Amérique du Nord et de l'ouest de l'Australie.

![7](https://github.com/Ayoub-Briguiche/my_projects_Data/assets/159647559/dc50896d-05b2-45ea-ad4c-e222b0eb2299)
