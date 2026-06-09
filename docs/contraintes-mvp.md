Contraintes MVP — SmartRH

Persona
Fatou Diallo, 30 ans, gère la RH sans être DRH, Dakar, ordinateur (Excel), téléphone, WhatsApp

Contraintes Non Négociables

Contrainte 1
Critère : Le MVP DOIT automatiser le calcul de la paie en intégrant nativement le SMIG, l'IPRES, la CSS et l'IR, sans saisie manuelle de ces paramètres par Fatou. Origine : Chapeau Blanc Élimine : toute version « tableur amélioré » où l'utilisateur ressaisit lui-même les taux de cotisation et barèmes.

Contrainte 2
Critère : Le MVP DOIT générer des alertes automatiques d'échéances (fin de CDD, renouvellement de contrat, solde de congés) sans action de surveillance de la part de Fatou. Origine : Chapeau Blanc Élimine : le simple stockage passif de contrats sans logique de rappel ; l'agenda manuel « à consulter ».

Contrainte 3
Critère : Le MVP DOIT fonctionner hors-ligne et synchroniser dès le retour du réseau ; aucune fonction cœur (saisie, calcul paie, consultation) NE DOIT exiger une connexion permanente. Origine : Chapeau Noir Élimine : l'architecture 100 % cloud temps réel, les fonctions bloquées sans data.

Contrainte 4
Critère : Le MVP NE DOIT PAS exposer les montants de salaire individuels via WhatsApp ni via un accès partagé non authentifié ; les données de paie DOIVENT être protégées par accès par rôle. Origine : Chapeau Noir Élimine : l'envoi de bulletins/salaires en clair par WhatsApp, le fichier unique partagé sans contrôle d'accès.

Contrainte 5
Critère : Le MVP DOIT être prise en main sans formation longue (logique proche d'Excel/WhatsApp déjà connue) et DOIT permettre l'import du fichier Excel existant. Origine : Chapeau Blanc + Chapeau Noir Élimine : l'onboarding complexe, l'obligation de ressaisir tout l'historique, l'interface « ERP » dense.

Contrainte 6
Critère : Le MVP NE DOIT PAS reposer sur un point de défaillance unique : les données DOIVENT être exportables (Excel/PDF) et récupérables même en l'absence de Fatou. Origine : Chapeau Noir Élimine : le format propriétaire fermé, l'enfermement des données sans export.

Contrainte 7
Critère : Le MVP DOIT être accessible à coût d'entrée nul ou très faible pour une PME en trésorerie tendue (palier gratuit fonctionnel). Origine : Chapeau Noir Élimine : l'abonnement obligatoire avant toute preuve de valeur, le paywall à l'installation.

Fonctionnalités Éliminées

* Bulletins de paie envoyés par WhatsApp → éliminée parce que la Contrainte 4 interdit l'exposition des salaires en clair sur un canal non sécurisé.
* Tableau de bord « temps réel » permanent connecté → éliminée parce que la Contrainte 3 impose un fonctionnement hors-ligne ; le vrai temps réel dépend d'un réseau non fiable.
* Pointage présences/congés par les employés (self-service) → éliminée du MVP parce qu'elle élargit la surface (gestion d'accès multi-utilisateurs, sécurité) avant d'avoir prouvé la valeur du noyau paie + alertes.
* Saisie manuelle des taux IPRES/CSS/IR par l'utilisateur → éliminée parce que la Contrainte 1 exige l'automatisation et que la saisie manuelle est précisément la source d'erreur à supprimer.
* Format de données propriétaire sans export → éliminée parce que la Contrainte 6 exige l'exportabilité et la non-dépendance à une seule personne.
* Module de reporting/analytics avancé → éliminée parce qu'il n'adresse aucun risque prioritaire et alourdit la prise en main (Contrainte 5).

Critère de Validation Final
Le MVP est valide si et seulement si Fatou peut, hors-ligne et sans formation, produire une paie juste (cotisations automatisées) et recevoir ses alertes d'échéances de contrats et congés, sans jamais exposer un salaire individuel sur un canal non sécurisé.
