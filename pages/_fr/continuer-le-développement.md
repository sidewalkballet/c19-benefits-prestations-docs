---
layout: page
title: Continuer le développement
lang: fr
trans_url: Continuing development
---
Ce document décrit comment poursuivre le développement avec ce code de base – ainsi que la structure de l’application et les technologies utilisées – pour faciliter la reprise de ce travail à l’avenir.

On prévoit deux scénarios pour poursuivre le développement :

1. Exécuter l’application et afficher toutes les pages afin de la restructurer à l’aide d’autres technologies.
2. Poursuivre le développement de ce référentiel précis.

## 1. Exécuter l’application et afficher toutes les pages

Tout ce que vous avez à faire ici est d’exécuter l’application et puis de trouver toutes les adresses URL.

1. D’abord, exécutez-la.
   * Consultez « Running Locally » (Exécution locale) dans le [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md).
   * L’application s’exécutera à l’adresse <http://localhost:3030/>.
3. Une liste complète des adresses URL se trouve à l’adresse [/config/routes.config.js](https://github.com/cds-snc/c19-benefits-node/blob/master/config/routes.config.js). Vous devrez naviguer dans les flux pour les voir tous.

## 2. Continuer à utiliser notre référentiel

Pour pouvoir reprendre le développement après un certain temps arbitraire, vous devez d’abord exécuter l’application, mettre à jour toutes les dépendances npm, puis vérifier que tous les tests réussissent avant de faire autre chose.

1. D’abord, exécutez-la.
   * Consultez « Running Locally » (Exécution locale) dans [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md).
   * L’application s’exécutera à l’adresse <http://localhost:3030/>.
3. Ensuite, exécutez les tests. S’ils réussissent tous (ils devraient), alors vous pouvez continuer.
   * Consultez « Testing » (Tests) dans [README](https://github.com/cds-snc/c19-benefits-node/blob/master/README.md).
5. Mettez à jour toutes les dépendances, car beaucoup seront obsolètes.

### Structure du référentiel

| Dossier              | But                                                                                              |
| -------------------- | ------------------------------------------------------------------------------------------------ |
| `/.github/workflows` | Pipelines/flux de travail d’IC/DC                                                                        |
| `/bin`               | Script d’exécution pour Node.js et scripts shell utiles                                             |
| `/config`            | Configurations des modules npm/intergiciels utilisés                                          |
| `/cypress`           | Fonctions et intégrations de tests de bout en bout                                                        |
| `/locales`           | Clés d’internationalisation (i18n) pour prendre en charge les langues officielles en français et en anglais           |
| `/middleware`        | Intergiciel personnalisé rédigé                                                                        |
| `/public`            | Ressources statiques (images, scripts, feuilles de style, icône favorite) : tous nos styles se trouvent dans /public/scss.  |
| `/routes`            | Contrôleurs (itiniraires et logique opérationnelle) et tests unitaires                                           |
| `/terraform`         | Scripts Terraform Azure et HashiCorp pour l’infrastructure comme code (IaC)                           |
| `/utils`             | Fonctions d’utilitaire et [intergiciel express](https://expressjs.com/en/guide/using-middleware.html) |
| `/views`             | Fichiers d’affichage [Pug](https://pugjs.org/api/getting-started.html) qui se traduisent en HTML au moment de l’exécution   |

### Choix technologiques

#### Développement

* Express.js (Node.js).
* Nunjucks (technologie d’affichage).
* express-validator (validation de formulaire).
* Tailwind CSS (styles).
* Jest (tests unitaires).
* Cypress (tests de bout en bout).
* Morgan (intergiciel du journal de requêtes HTTP).
* Helmet (intergiciel de stratégie de sécurité du contenu).

#### Intégration et prestation continues

* GitHub Actions.
* Seekret (trouver des secrets dans le code).
* Snyk (analyse continue de la sécurité).
* Semmle/LGTM (analyse de sécurité continue).

#### Informatique en nuage

Microsoft Azure est le fournisseur de services infonuagiques.

* Azure AppService (offre de plateforme comme service pour déployer l’application).
* Registre conteneur d’Azure.
* Azure KeyVault (Secrets).
* Azure Application Insights (Metrics and journalisation).

#### Déploiement

* Azure AppService.
* Docker.

Si vous avez des questions ou des commentaires sur le produit, veuillez envoyer un courriel au [Service du numérique canadien](mailto:cds-snc@tbs-sct.gc.ca).