## Hypothèses de Validation — SmartRH

### HMW Définitif
"Comment pourrions-nous permettre à une PME sénégalaise sans DRH de fiabiliser sa paie et de ne plus rater une échéance de contrat ou de congé, en s'appuyant sur ses outils actuels (Excel, WhatsApp) et en fonctionnant même avec une connexion instable ?"

---

### Hypothèses CRITIQUES

#### Hypothèse C1 — Fiabilité et adoptabilité de la paie automatisée

**Affirmation :** Nous croyons que le module dont la fiabilité ferait basculer une gestionnaire RH de fait d'Excel vers SmartRH dès le premier cycle est la paie automatisée (SMIG · IPRES · CSS · IR) — et qu'une paie produite par l'outil est jugée juste et adoptable sans recompter à la main.

**Indicateur :** Nous le saurons si, sur 5 PME « Fatou » testées, au moins 4 confirment que le net et les cotisations calculés par SmartRH correspondent à leur calcul Excel à moins de 1 % d'écart, ET si au moins 3 acceptent de produire leur cycle suivant dans l'outil.

**Méthode :** Wizard of Oz sur un cycle de paie réel — l'équipe saisit les données de 3 à 5 salariés d'une PME volontaire dans une feuille de calcul SmartRH (barèmes pré-paramétrés), produit les bulletins, et les compare ligne à ligne avec la paie Excel habituelle de la gestionnaire, puis débriefe 15 minutes.

**Qui valide :** La personne qui gère la paie de fait (assistante, comptable ou gérant) dans chaque PME pilote.

**Délai S3 :** Recrutement J1–J2, tests de paie J3–J7, analyse J8 — résultat en fin de semaine 1 du sprint S3.

---

#### Hypothèse C2 — Continuité hors-ligne en connexion instable

**Affirmation :** Nous croyons que le fonctionnement hors-ligne est non négociable : sans lui, les coupures réseau provoqueraient l'abandon de l'outil, quelle que soit la qualité de la paie.

**Indicateur :** Nous le saurons si une utilisatrice peut saisir et consulter ses données en mode déconnecté pendant une session complète, ET si la synchronisation au retour du réseau s'effectue sans perte ni doublon sur 10 essais consécutifs.

**Méthode :** Test en conditions de connexion dégradée (mode avion / data coupée) sur un prototype : saisie de 5 employés et consultation hors-ligne, puis reconnexion et vérification de l'intégrité des données ; répétition sur 2 jours.

**Qui valide :** La gestionnaire RH de fait + vérification technique de l'équipe (journal de synchronisation).

**Délai S3 :** Test sur 2 jours en semaine 2 du sprint S3, après stabilisation du prototype C1.

---

### Hypothèses IMPORTANTES

#### Hypothèse I1 — Confidentialité comme condition d'adoption

**Affirmation :** Nous croyons qu'une gestionnaire RH de fait n'utilisera pas l'outil si elle craint qu'un salaire individuel soit exposé — notamment via WhatsApp — et qu'un accès par rôle clair est une condition d'entrée, pas une option.

**Indicateur :** Nous le saurons si, lors de l'onboarding test, au moins 4 utilisatrices sur 5 vérifient spontanément « qui peut voir les montants » avant de saisir des données réelles, ET si aucune ne demande à diffuser des bulletins en clair par WhatsApp.

**Méthode :** Observation de l'onboarding + entretien semi-directif de 20 minutes auprès de 5 gestionnaires (et si possible 2 gérants) sur leurs attentes de confidentialité ; test d'un parcours où les données sensibles restent dans l'interface authentifiée et où WhatsApp ne sert qu'aux actions non sensibles.

**Qui valide :** Gestionnaire RH de fait + gérant de la PME pilote.

**Délai S3 :** Entretiens semaine 1 (3 jours), test de parcours semaine 2 (2 jours) — résultat avant la fin de S3.

---

#### Hypothèse I2 — WhatsApp comme accélérateur d'adoption

**Affirmation :** Nous croyons que s'appuyer sur WhatsApp (canal déjà maîtrisé) augmente l'adoption par rapport à une interface web inconnue, au moins pour les actions non sensibles (alertes, pointage, demande de congé).

**Indicateur :** Nous le saurons si au moins 6 employés sur 10 acceptent de déclarer une présence ou un congé via WhatsApp lors du test sans formation, ET si les gestionnaires jugent ce canal plus simple qu'une connexion à une interface.

**Méthode :** Test d'usage du bot WhatsApp (simulable manuellement) auprès des employés d'une PME pilote : envoi d'une commande de pointage, mesure du taux de réussite sans assistance + micro-sondage de satisfaction.

**Qui valide :** Les employés d'une PME pilote + la gestionnaire RH.

**Délai S3 :** 1 journée terrain + 1 journée d'analyse, parallélisable avec I1.

---

### Hypothèses SECONDAIRES

#### Hypothèse S1 — Pertinence du périmètre paie + alertes comme noyau V1

**Affirmation :** Nous croyons que la paie et les alertes d'échéances représentent la douleur prioritaire, et que les couvrir d'abord (avant présences/congés self-service) suffit à rendre SmartRH immédiatement utile.

**Indicateur :** Nous le saurons si, interrogées sur leur problème RH n°1, au moins 4 PME sur 5 citent spontanément la paie ou une échéance ratée plutôt que le suivi des présences.

**Méthode :** Question ouverte en entretien (« quel est votre cauchemar RH de fin de mois ? ») auprès de 5 gestionnaires, puis classement assisté des douleurs.

**Qui valide :** 5 gestionnaires RH de fait.

**Délai S3 :** Intégré aux entretiens C1/I1, résultat en semaine 1.

---

#### Hypothèse S2 — Freemium comme levier d'entrée

**Affirmation :** Nous croyons qu'un palier gratuit (suivi présences/congés d'un petit effectif) lève la barrière d'entrée des PME en trésorerie tendue, qui passeront au palier payant (paie automatisée) après avoir constaté la valeur.

**Indicateur :** Nous le saurons si au moins 3 PME sur 5 déclarent qu'elles testeraient l'outil sur le palier gratuit, et qu'au moins 1 envisage le passage payant après le pilote.

**Méthode :** Présentation des paliers en fin d'entretien + question d'intention de paiement ; suivi déclaratif sur la durée du pilote.

**Qui valide :** Gestionnaires et gérants des PME pilotes.

**Délai S3 :** Après le MVP, en fin de S3 et au-delà.

---

### Priorité de Validation S3

La première chose à tester en S3 : produire en Wizard of Oz une paie réelle complète pour 3 à 5 salariés d'une PME volontaire, la comparer ligne à ligne à sa paie Excel, et vérifier que la gestionnaire la juge juste et adoptable dès le premier cycle. C'est le test go/no-go du projet.
