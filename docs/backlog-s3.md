## Backlog S3 — PostLab

### HMW Définitif
"Comment pourrions-nous permettre à une PME sénégalaise sans DRH de fiabiliser sa paie et de ne plus rater une échéance de contrat ou de congé, en s'appuyant sur ses outils actuels (Excel, WhatsApp) et en fonctionnant même avec une connexion instable ?"

> **Note de cadrage :** le MVP évalué est une application web déployée (Bolt.new / Lovable) connectée à un agent IA Dify. Le bot WhatsApp et le mode offline complet restent la vision produit portée au pitch S6 ; le MVP S3 en simule la valeur dans l'interface web. Séquençage : noyau **paie + alertes** d'abord, présences/self-service ensuite.

---

### User Stories MUST
*(À construire obligatoirement en S3)*

#### US-01
**Story :** En tant que gestionnaire RH de fait, je veux importer mon fichier Excel d'employés et voir un tableau de bord centralisé (nom · contrat CDD/CDI · statut · solde de congés · prochaine échéance), afin de remplacer Excel + papier par une source unique.
**Priorité :** MUST
**Outil :** Bolt.new / Lovable (import tableur + table filtrable)
**Effort :** Faible
**Adresse :** Pain Reliever — SmartRH prolonge Excel au lieu de le remplacer (Contrainte 5) + Job "centraliser"
**Critère d'acceptation :** Une liste d'au moins 6 employés réels est chargée depuis un fichier tableur, affichée avec contrat, statut, solde de congés et date d'échéance, et un filtre CDD/CDI fonctionne ; la liste est ré-exportable.

---

#### US-02
**Story :** En tant que gestionnaire RH de fait, je veux une section « Échéances à venir » qui signale fins de CDD, renouvellements et soldes de congés bas, afin de ne plus rien rater sans surveillance manuelle.
**Priorité :** MUST
**Outil :** Bolt.new / Lovable + logique de dates
**Effort :** Moyen
**Adresse :** Pain Reliever — alertes automatiques d'échéances (Contrainte 2)
**Critère d'acceptation :** Les échéances à moins de 7 jours s'affichent en couleur d'alerte, la liste est triée par date, et aucune action de surveillance manuelle n'est requise pour les faire apparaître.

---

#### US-03
**Story :** En tant que gestionnaire RH de fait, je veux interroger un assistant IA RH (« quelles cotisations pour ce salaire ? », « ce renouvellement de CDD est-il légal ? », « combien de jours de congé reste-t-il ? ») et obtenir une réponse fiable ancrée dans le droit sénégalais, afin de fiabiliser mes décisions sans être experte.
**Priorité :** MUST
**Outil :** Dify (workflow Chercheur → Si/Sinon → Rédacteur, enrichi par RAG en S5)
**Effort :** Moyen
**Adresse :** Pain Reliever — fiabilité de la paie et conformité (Contraintes 1 et 4)
**Critère d'acceptation :** L'agent Dify répond de façon structurée à 3 questions RH de test, renvoie « INSUFFISANT » quand la donnée manque, et n'invente jamais un chiffre ou un barème non fourni.

---

#### US-04
**Story :** En tant que gestionnaire RH de fait, je veux un récapitulatif de paie calculé automatiquement (brut → cotisations IPRES/CSS/IR → net) à partir d'un salaire saisi, afin de produire une paie juste sans recompter à la main.
**Priorité :** MUST
**Outil :** Dify (logique de calcul avec barèmes pré-paramétrés) + interface Bolt.new
**Effort :** Élevé
**Adresse :** Pain Reliever — calcul des cotisations automatisé (Contrainte 1) + Métrique Nord (paie juste du premier coup)
**Critère d'acceptation :** À partir d'un brut saisi, l'outil affiche un récapitulatif clair avec cotisations détaillées et net, sans ressaisie des taux, et le résultat est cohérent avec un calcul de contrôle manuel à moins de 1 % d'écart.

---

#### US-05
**Story :** En tant que gestionnaire RH de fait, je veux que les montants de salaire ne soient visibles que sous accès par rôle et jamais diffusés en clair, afin de protéger des données sensibles.
**Priorité :** MUST
**Outil :** Bolt.new / Lovable (gestion de rôles + masquage des montants)
**Effort :** Moyen
**Adresse :** Pain Reliever — accès par rôle, aucun salaire en clair (Contrainte 4)
**Critère d'acceptation :** Un rôle « consultation » ne voit pas les nets individuels, les montants ne sont jamais envoyés via un canal non authentifié, et l'affichage des salaires exige une authentification.

---

### User Stories SHOULD
*(À construire si le temps le permet en S3)*

#### US-06
**Story :** En tant que gestionnaire RH de fait, je veux exporter la paie et la liste des employés en Excel/PDF, afin de transmettre à la compta et de ne pas dépendre d'une seule personne ni d'un format fermé.
**Priorité :** SHOULD
**Outil :** Bolt.new / Lovable (export CSV/PDF)
**Effort :** Faible
**Adresse :** Pain Reliever — exportabilité, pas de point de défaillance unique (Contrainte 6)
**Critère d'acceptation :** La paie d'un cycle et la liste des employés s'exportent en un clic dans un format ouvert, lisible hors de l'outil.

---

#### US-07
**Story :** En tant qu'administrateur SmartRH, je veux un tableau de bord des 3 métriques (taux de paies justes, temps de production, échéances anticipées), afin de suivre les indicateurs de la démo S6 sans outil externe.
**Priorité :** SHOULD
**Outil :** Bolt.new / Lovable (dashboard KPIs)
**Effort :** Moyen
**Adresse :** Métrique Nord + Métriques de Progression P1 et P2
**Critère d'acceptation :** Le dashboard affiche le taux de bulletins sans correction, le temps de production avant/après et le pourcentage d'échéances anticipées, à partir des données de l'outil sans saisie manuelle supplémentaire.

---

### User Stories COULD
*(Roadmap post-MVP — S4 et au-delà)*

#### US-08
**Story :** En tant qu'employé, je veux déclarer une présence ou un congé via WhatsApp, afin de gagner en visibilité sur ma situation RH sans accéder à l'interface.
**Priorité :** COULD
**Outil :** Webhook + intégration WhatsApp (Dify) + Bolt.new (base)
**Effort :** Élevé
**Adresse :** Gain — redonner de la visibilité aux employés (Chapeau Rouge) + Produit "bot WhatsApp" (Chapeau Vert)
**Critère d'acceptation :** Une déclaration envoyée par message WhatsApp est enregistrée dans le tableau de bord avec accusé de réception, sans exposer de donnée salariale (simulable en démo S6).

---

#### US-09
**Story :** En tant que gestionnaire RH de fait, je veux que l'outil fonctionne hors-ligne et synchronise au retour du réseau, afin de continuer à travailler malgré les coupures.
**Priorité :** COULD
**Outil :** PWA / stockage local + logique de synchronisation
**Effort :** Élevé
**Adresse :** Pain Reliever — fonctionnement hors-ligne (Contrainte 3)
**Critère d'acceptation :** La saisie et la consultation restent disponibles sans connexion, et les données se synchronisent sans perte ni doublon au retour du réseau (démontrable en mode avion).

---

#### US-10
**Story :** En tant que gérant de PME, je veux un résumé mensuel de l'état RH (effectifs · échéances · alertes), afin de suivre sans entrer dans le détail.
**Priorité :** COULD
**Outil :** Dify (Rédacteur) + Bolt.new
**Effort :** Moyen
**Adresse :** Gain Creator — conformité défendable + crédibilité de la gestionnaire
**Critère d'acceptation :** Une synthèse de quelques lignes résume effectifs, échéances du mois et alertes déclenchées, générée automatiquement à partir des données de l'outil.

---

### Sprint S3

**Semaine 1 — Noyau données & conformité :**
US-01 (import Excel + tableau de bord) + US-02 (alertes d'échéances) + US-05 (accès par rôle) — objectif : avoir une base d'employés réelle, des alertes fonctionnelles et des montants protégés d'ici vendredi.

**Semaine 2 — Cerveau IA & paie :**
US-03 (agent RH Dify Chercheur → Rédacteur) + US-04 (récapitulatif de paie automatisé) — objectif : répondre de façon fiable à 3 questions RH et produire un récapitulatif de paie cohérent avec un contrôle manuel, avant le jeudi de la semaine 2.

Si avance constatée en fin de semaine 2 : démarrer US-06 (export) ou US-07 (dashboard KPIs).

**Démo S6 — À démontrer obligatoirement :**
US-04 (calcul d'un récapitulatif de paie en direct devant le jury) + US-03 (réponse fiable de l'agent Dify, avec un cas « INSUFFISANT ») + US-02 (alerte d'échéance qui se déclenche à l'écran).
