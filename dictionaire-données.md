# Dictionnaire de données

## Produits (`product`)

| Champ       | Type      | Spécificités                                    | Description                                                   |
| ----------- | --------- | ----------------------------------------------- | ------------------------------------------------------------- |
| id          | INT       | PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT | L'identifiant de notre produit                                |
| name        | VARCHAR   | NOT NULL                                        | Le nom du produit                                             |
| description | TEXT      | NULL                                            | La description du produit                                     |
| picture     | VARCHAR   | NULL                                            | L'URL de l'image du produit                                   |
| price       | DECIMAL   | NOT NULL, DEFAULT 0                             | Le prix du produit                                            |
| rate        | TINYINT   | NOT NULL, DEFAULT 0                             | L'avis sur le produit, de 1 à 5                               |
| status      | TINYINT   | NOT NULL, DEFAULT 0                             | Le statut du produit (0=non renseignée, 1=dispo, 2=pas dispo) |
| created_at  | TIMESTAMP | NOT NULL, DEFAULT CURRENT_TIMESTAMP             | La date de création du produit                                |
| updated_at  | TIMESTAMP | NULL                                            | La date de la dernière mise à jour du produit                 |
| brand       | entity    | FOREIGN KEY, NOT NULL                           | La marque (autre entité) du produit                           |
| category    | entity    | FOREIGN KEY, NOT NULL                           | La catégorie (autre entité) du produit                        |
| type        | entity    | FOREIGN KEY, NOT NULL                           | Le type (autre entité) du produit                             |

## Catégories (`category`)

| Champ      | Type      | Spécificités                                    | Description                                                              |
| ---------- | --------- | ----------------------------------------------- | ------------------------------------------------------------------------ |
| id         | INT       | PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT | L'identifiant de la catégorie                                            |
| name       | VARCHAR   | NOT NULL                                        | Le nom de la catégorie                                                   |
| subtitle   | VARCHAR   | NULL                                            | Le sous-titre/slogan de la catégorie                                     |
| picture    | VARCHAR   | NULL                                            | L'URL de l'image de la catégorie (utilisée en home, par exemple)         |
| home_order | TINYINT   | NOT NULL, DEFAULT 0                             | L'ordre d'affichage de la catégorie sur la home (0=pas affichée en home) |
| created_at | TIMESTAMP | DEFAULT CURRENT_TIMESTAMP                       | La date de création de la catégorie                                      |
| updated_at | TIMESTAMP | NULL                                            | La date de la dernière mise à jour de la catégorie                       |

## Marque (`brand`)

| Champ      | Type      | Spécificités                                    | Description                                     |
| ---------- | --------- | ----------------------------------------------- | ----------------------------------------------- |
| id         | INT       | PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT | L'identifiant de la marque                      |
| name       | VARCHAR   | NOT NULL                                        | Le nom de la marque                             |
| created_at | TIMESTAMP | DEFAULT CURRENT_TIMESTAMP                       | La date de création de la marque                |
| updated_at | TIMESTAMP | NULL                                            | La date de la dernière mise à jour de la marque |

## Type de produit (`type`)

| Champ      | Type      | Spécificités                                    | Description                                |
| ---------- | --------- | ----------------------------------------------- | ------------------------------------------ |
| id         | INT       | PRIMARY KEY, NOT NULL, UNSIGNED, AUTO_INCREMENT | L'identifiant du type                      |
| name       | VARCHAR   | NOT NULL                                        | Le nom du type                             |
| created_at | TIMESTAMP | DEFAULT CURRENT_TIMESTAMP                       | La date de création du type                |
| updated_at | TIMESTAMP | NULL                                            | La date de la dernière mise à jour du type |
