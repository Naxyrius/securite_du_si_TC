# NovaCloud Services

Fiche entreprise · fil rouge des TP · séquences 1 et 2

> **Document remis aux étudiants · fiche de contexte**
>
> Cette fiche décrit une entreprise **fictive**. Elle sert de fil rouge aux TP des deux séquences. Toute ressemblance avec une entreprise réelle serait fortuite. Vous pouvez poser des hypothèses raisonnables si une information manque, à condition de les noter.

# 1. Présentation générale

**NovaCloud Services** est une PME française d’infogérance et d’hébergement fondée en 2012. Elle conçoit, héberge et exploite des environnements informatiques pour des clients du secteur de la santé et des collectivités territoriales. Son siège est à Lyon ; un second site, à Nantes, abrite le support.

|                        |                                                                                                                                                                                                              |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Effectif**           | 120 personnes (dont 70 en production et support, 20 en développement, 30 en fonctions support)                                                                                                               |
| **Chiffre d’affaires** | 14 M€ (en croissance de 12 % par an)                                                                                                                                                                         |
| **Clients**            | 65 clients : 18 établissements de santé (cliniques, EHPAD, laboratoires), 30 collectivités et syndicats intercommunaux, 17 PME                                                                               |
| **Sites**              | Siège à Lyon (bureaux et salle serveur historique) ; antenne à Nantes (support niveau 1 et 2) ; hébergement en datacenter loué à Lyon, avec un second datacenter loué à Marseille pour la reprise d’activité |
| **Direction**          | Directrice générale (fondatrice), directeur technique (CTO), directeur financier et administratif, directrice commerciale                                                                                    |

# 2. Services proposés

| **Service**                      | **Description**                                                                                                         | **Données et criticité**                                                           |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| **Cloud privé hébergé**          | Plateforme de virtualisation mutualisée (VMware), stockage et réseau, hébergée en datacenter loué                       | Contient les serveurs des clients, dont des données de santé. Criticité très forte |
| **Infogérance**                  | Supervision, exploitation, patching et sauvegarde du parc des clients (serveurs et postes)                              | Accès administrateur chez les clients. Criticité forte                             |
| **Sauvegarde externalisée**      | Sauvegardes chiffrées répliquées entre Lyon et Marseille                                                                | Copies de toutes les données clientes. Criticité forte                             |
| **Support (service desk)**       | Assistance niveaux 1 et 2, du lundi au vendredi de 8 h à 19 h, astreinte la nuit pour les clients santé                 | Outil de tickets et accès à distance. Criticité moyenne                            |
| **Logiciel métier « NovaPlan »** | Application web de planification de tournées pour des services d’aide à domicile, développée en interne, vendue en SaaS | Données personnelles de patients et de salariés. Criticité forte                   |

# 3. Système d’information

### Infrastructure

- **Datacenter de Lyon** : 3 baies louées, 24 serveurs physiques, environ 350 machines virtuelles (clients et interne).

- **Datacenter de Marseille** : 1 baie louée, sert de site de reprise et de stockage des sauvegardes répliquées.

- **Salle serveur historique du siège** : héberge encore l’annuaire interne, un serveur de fichiers et deux anciens serveurs clients non migrés.

- **Réseau** : interconnexion entre sites par VPN IPsec ; accès à distance des collaborateurs par VPN avec authentification par mot de passe seul.

### Applications et outils internes

- Annuaire Active Directory interne, messagerie en ligne (Microsoft 365), outil de gestion de tickets (SaaS), supervision (outil open source auto-hébergé).

- Forge de code (GitLab auto-hébergé) et chaîne d’intégration continue pour NovaPlan.

- Outil de gestion des mots de passe d’administration des clients : coffre partagé en base de données chiffrée, accessible à toute l’équipe de production.

- RH et paie externalisées chez un prestataire ; facturation par un ERP en SaaS.

### Postes et mobilité

- 130 ordinateurs portables (Windows et quelques Linux), chiffrement du disque activé sur environ 70 % d’entre eux.

- Les techniciens de production utilisent leurs propres téléphones pour la messagerie et les alertes d’astreinte (BYOD, sans gestion centralisée).

# 4. Sous-traitants et partenaires

| **Partenaire**                                       | **Rôle**                                                                         |
|------------------------------------------------------|----------------------------------------------------------------------------------|
| **Opérateur de datacenters (Lyon et Marseille)**     | Location de baies, énergie, accès physique, connectivité                         |
| **Éditeur de l’outil de tickets et de l’ERP (SaaS)** | Hébergement de données de clients et de données financières                      |
| **Prestataire RH et paie**                           | Traitement des données personnelles de tous les salariés                         |
| **Société de nettoyage et de gardiennage**           | Accès aux locaux du siège et de Nantes, y compris en dehors des heures de bureau |
| **Cabinet de conseil en cybersécurité (ponctuel)**   | Test d’intrusion annuel sur la plateforme d’hébergement                          |

# 5. Contexte réglementaire et contractuel

- **RGPD** : NovaCloud est sous-traitant pour ses clients (données hébergées) et responsable de traitement pour les données de ses salariés.

- **Hébergement de données de santé (HDS)** : exigence de certification pour les clients du secteur santé. NovaCloud ne possède **pas** encore cette certification ; elle y réfléchit.

- **NIS2** : plusieurs clients (santé, collectivités) entrent dans le champ de la directive ; ils demandent à leurs prestataires des garanties de sécurité.

- Contrats clients : engagement de disponibilité de 99,9 % sur le cloud privé, avec pénalités ; clauses de confidentialité ; obligation de prévenir le client dans les 48 heures en cas d’incident.

# 6. Situation actuelle de la sécurité

La sécurité est assurée de manière informelle par le directeur technique et deux ingénieurs système, sans rôle dédié. Les points suivants ont été relevés lors d’un récent entretien interne :

- Aucune politique de sécurité écrite ; quelques procédures techniques sont éparpillées dans un wiki interne, souvent périmées.

- Aucun poste de RSSI. Le DPO est le directeur financier, à temps partiel.

- Un test d’intrusion annuel est réalisé, mais ses recommandations ne sont pas toutes suivies.

- Un client santé a exigé récemment la preuve d’une démarche de certification ISO 27001 ; la direction a donc décidé de **lancer la construction d’un système de management de la sécurité de l’information (SMSI)**.

- Deux incidents ont marqué l’entreprise : un compte administrateur compromis par hameçonnage il y a un an (sans conséquence grave), et une indisponibilité de six heures du cloud privé suite à une erreur de manipulation.

- Aucune sensibilisation formelle du personnel. Un nouveau collaborateur reçoit ses accès sans parcours dédié.

> **Votre rôle**
>
> La directrice générale vous mandate comme équipe projet chargée de définir le **périmètre** du SMSI (séquence 1), puis de proposer les **mesures prioritaires** et un **plan de sensibilisation** (séquence 2).
