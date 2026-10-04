# Pharmoire, données publiées

Ce dépôt publie les fichiers que l'app Pharmoire télécharge : la base des médicaments, les notices officielles et les alertes de l'ANSM. Ils sont construits automatiquement à partir de la [base de données publique des médicaments](https://base-donnees-publique.medicaments.gouv.fr) et ne contiennent aucune donnée personnelle.

Pharmoire n'est pas un service de l'ANSM et ne remplace pas l'avis d'un médecin ou d'un pharmacien.

## Fichiers

Le manifeste est toujours à la même adresse :

```
https://github.com/bruno00o/pharmoire-data/releases/download/current/manifest.json
```

Il donne, pour chaque fichier, sa version, son adresse, sa taille et son empreinte SHA-256.

| Fichier | Contenu | Mise à jour |
| --- | --- | --- |
| `reference.db` | Médicaments, présentations, compositions, prix, remboursements, avis de la HAS, génériques | chaque semaine |
| `notices.db` | Notices officielles et rubriques 4.6, 4.7, 6.3 et 6.4 des RCP, compressées document par document | chaque semaine |
| `alerts.db` | Informations de sécurité en cours et ruptures de stock | chaque jour |

Les releases `data-…` contiennent la base et les notices ; la release `current` contient le manifeste et les alertes du jour. La release `documents-store` est la base de travail du parcours des pages et n'est pas destinée à l'app.

## Licence et source

Données issues de la base de données publique des médicaments, éditée par l'ANSM :

- fichiers téléchargeables : Licence Ouverte / Open Licence 1.0 (Etalab) ;
- contenus du site, dont les RCP et les notices : licence etalab-2.0.

Les textes officiels ne sont ni modifiés ni résumés : seules leur mise en forme et leur compression changent. Chaque fichier indique dans sa table `meta` la date à laquelle la source a été téléchargée.
