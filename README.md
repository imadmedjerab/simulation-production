# 📦 Système de Gestion de Production — Simulation FlexSim

Modélisation et simulation d'une chaîne de production dans une usine d'emballage avec **FlexSim**, incluant l'analyse de scénarios de crise (variabilité des arrivées, pannes machines) et l'optimisation des ressources.

## 📋 Contexte du projet

Projet réalisé dans le cadre du Master 1 Data Science (ASD), Université d'Alger 1, encadré par Dr. Benghalia Abderaouf, en équipe de 3 (Medjerab Imad, Leftissi Ayoub Abderrahmene, Salaa Aymen).

Dans un contexte industriel où l'optimisation des systèmes de production est une priorité stratégique, ce projet utilise la simulation pour analyser et améliorer une chaîne de production d'emballage — gestion des flux de matières, coordination machines/opérateurs, réduction des temps d'attente et des pertes — sans perturber les opérations réelles.

**Problématiques traitées :**
- Comment réagir en cas de dysfonctionnement des machines ?
- Quelles méthodes de contrôle qualité intégrer dans une simulation d'emballage ?
- Comment gérer les produits non conformes pour minimiser les pertes et améliorer la productivité ?

## 🏭 Modélisation

La chaîne de production est modélisée en deux grandes phases :

1. **Entrée et vérification du produit** : les produits arrivent selon 4 catégories à des horaires précis, sont traités par des machines spécifiques à leur type, puis passent un contrôle qualité. Les produits conformes vont au stock principal, les non conformes sont isolés.
2. **Séparation et stockage** : des transporteurs automatisés acheminent chaque produit vers des racks organisés par type et qualité — racks pour produits conformes, rack dédié aux produits défectueux.

Une comparaison visuelle entre la simulation FlexSim et l'usine réelle a été réalisée pour valider la fidélité du modèle à chaque étape du processus (réception, tri, machines, stockage).

## ⚠️ Scénarios de crise simulés

### Scénario 1 — Variabilité des arrivées de produits
Problème : des mélanges accidentels de produits peuvent survenir lors de perturbations (retard, panne, longue vérification), désorganisant le stockage.
Solution mise en place : un système de classification par type de produit et une organisation stricte des files d'attente de production par ordre de type, réduisant les risques de confusion.

### Scénario 2 — Dysfonctionnement des machines
Problème : la machine principale (Machine1) subissait des arrêts fréquents (environ toutes les heures) à cause d'un capteur de fin de course encrassé, provoquant retards et interventions manuelles.
Solution mise en place : maintenance préventive avec nettoyage du capteur toutes les 4 heures, ajout d'un témoin lumineux pour détecter rapidement les anomalies — réduisant significativement les arrêts imprévus.

## 📊 Résultats de l'analyse

**Utilisation des opérateurs et transporteurs :**

| Ressource | Taux d'utilisation |
|-----------|---------------------|
| Opérateur 1 | 5.96% |
| Opérateur 2 | 31.55% |
| Transporteur 1 | 10.79% |
| Transporteur 2 | 14.48% |
| Transporteur 3 | 2.99% |

→ L'Opérateur 2 est nettement plus sollicité, révélant une répartition inégale des tâches. Le Transporteur 3, très peu utilisé, suggère un problème de capacité ou d'affectation à revoir.

**Débit des machines (throughput) :**

| Machine / Poste | Débit |
|------------------|-------|
| Machine 1 | 27 |
| Machine 2 | 51 |
| Machine 3 | 80 |
| Machine 4 | 82 |
| Contrôle | 240 |

→ Machine 4 est la plus performante (82), Machine 1 la moins performante (27) — un écart important qui identifie un goulot d'étranglement potentiel.

**Taux de fonctionnement des machines :** Machine 4 et le poste de Contrôle affichent la charge de travail la plus concentrée, ce qui pourrait affecter leur efficacité à long terme.

## 🎯 Conclusion

La simulation avec FlexSim a permis de modéliser les différentes étapes de la production, d'identifier les goulots d'étranglement (notamment autour de Machine 1 et Machine 4), et de tester des stratégies d'amélioration sans risque pour l'environnement réel — un outil précieux pour accompagner les décisions stratégiques de gestion industrielle.

## 🛠️ Technologies utilisées

- **Simulation** : FlexSim
- **Analyse** : State Bar, taux de fonctionnement, throughput

## 👤 Auteurs

**Medjerab Imad**, Leftissi Ayoub Abderrahmene, Salaa Aymen
Encadré par Dr. Benghalia Abderaouf — Master 1 Data Science (ASD), Université d'Alger 1

[LinkedIn Imad](https://linkedin.com/in/imadmedjerab-8400a0341) | imadmedjerab94@gmail.com
