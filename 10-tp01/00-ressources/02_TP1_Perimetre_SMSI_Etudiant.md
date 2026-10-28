# TP 1 · Définir le périmètre du SMSI

Séquence 1 · mercredi 28 octobre 2026 · groupe : \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

|                      |                                                                                                                    |
|----------------------|--------------------------------------------------------------------------------------------------------------------|
| **Durée**            | 60 min de travail en groupe, puis 15 min de restitution                                                            |
| **Organisation**     | Groupes de 3 ou 4 étudiants. Un groupe rend une seule fiche.                                                       |
| **Document de base** | Fiche NovaCloud Services                                                                                           |
| **Livrable**         | Cette fiche complétée (4 pages maximum), rendue en fin de séance                                                   |
| **Barème indicatif** | 10 points : parties intéressées (2), actifs et services (2), frontières (3), exclusions justifiées (2), clarté (1) |

> **Mission**
>
> La direction de NovaCloud lance son SMSI. Avant toute chose, il faut décider **ce que le SMSI protège** : c’est le périmètre (clause 4.3 de l’ISO 27001). Un périmètre trop large est impossible à tenir ; un périmètre trop étroit n’a aucune valeur pour les clients. À vous de trouver le bon compromis et de le justifier.

# Étape 1 · Contexte et parties intéressées (15 min)

Identifiez au moins **six parties intéressées** (clause 4.2) et, pour chacune, ses attentes en matière de sécurité et la nature de l’exigence (légale, contractuelle ou autre).

| Partie intéressée | Attentes en matière de sécurité | Exigence (légale, contractuelle, autre) |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |


**Question de réflexion** : parmi ces exigences, laquelle pèse le plus sur le choix du périmètre, et pourquoi ?

# Étape 2 · Inventaire des actifs et des services (15 min)

Classez les éléments de la fiche NovaCloud dans le tableau. Indiquez pour chacun s’il est **dans le périmètre proposé** (oui / non / à discuter) et pourquoi.

| Catégorie | Éléments identifiés | Dans le périmètre ? | Justification courte |
|---|---|---|---|
| Services fournis aux clients |  |  |  |
| Sites et locaux |  |  |  |
| Infrastructure (réseau, serveurs, stockage) |  |  |  |
| Applications et outils internes |  |  |  |
| Postes et mobiles |  |  |  |
| Personnes et fonctions |  |  |  |
| Sous-traitants et fournisseurs |  |  |  |


# Étape 3 · Frontières et interfaces (15 min)

Un périmètre se décrit par ses **frontières** (ce qui est dedans, ce qui est dehors) et par ses **interfaces** (ce qui traverse la frontière). Complétez :

| Élément | Réponse |
|---|---|
| Services inclus |  |
| Sites inclus |  |
| Processus et fonctions concernés |  |
| Interfaces et dépendances (sous-traitants, clients, réseaux) |  |
| Exclusions et justification |  |


# Étape 4 · Rédaction de l’énoncé du périmètre (10 min)

Rédigez en **cinq lignes maximum** l’énoncé officiel, tel qu’il figurerait dans le certificat. Exemple de forme (volontairement incomplet) : « Le SMSI couvre … fournies depuis les sites de … à destination de … , conformément à la déclaration d’applicabilité en vigueur au … »

> **Auto-contrôle avant de rendre la fiche**
>
> ☐ Chaque exclusion est justifiée et ne met pas en cause la sécurité des services inclus.
>
> ☐ Chaque service critique pour un client santé est inclus ou son exclusion est expliquée.
>
> ☐ Les sous-traitants qui traitent des données du périmètre sont mentionnés comme interfaces.
>
> ☐ L’énoncé est compréhensible par un client qui ne connaît pas NovaCloud.

## Questions pour la restitution

- Quelle a été la décision la plus difficile à prendre, et pourquoi ?

- Si la salle serveur historique est exclue, que devient la sécurité des deux anciens serveurs clients qui s’y trouvent ?

- Un auditeur peut-il considérer votre périmètre comme artificiellement réduit ?

