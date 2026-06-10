## Métriques de Succès — SmartRH

### MVP
Application web (mobile-first) qui fiabilise la paie d'une PME sans DRH — calcul automatisé SMIG · IPRES · CSS · IR — et alerte avant chaque échéance de contrat ou de congé, avec import/export Excel, accès par rôle et fonctionnement même en connexion instable.

---

### ⭐ Métrique Nord

**Indicateur :** Taux de paies justes du premier coup — pourcentage de bulletins produits par SmartRH qui ne nécessitent aucune correction de net ou de cotisation après le contrôle de la gestionnaire.

**Valeur cible à 30 jours :** 100 % des bulletins du cycle justes du premier coup sur la PME pilote (0 correction après clôture), sur un effectif d'au moins 5 salariés.

**Comment mesurer :** Sur un cycle de paie complet, la gestionnaire compare chaque bulletin produit par SmartRH à son contrôle habituel et note toute correction nécessaire dans un carnet de suivi (date · salarié · type d'écart). Consolidation manuelle en fin de cycle.

---

### 📈 Métriques de Progression

#### Métrique P1
**Indicateur :** Temps de production de la paie mensuelle — durée totale du calcul de la paie et des cotisations pour l'ensemble de l'effectif.

**Valeur cible à 30 jours :** Réduction d'au moins 50 % du temps déclaré par rapport à la méthode Excel (mesure avant/après).

**Comment mesurer :** Auto-déclaration chronométrée de la gestionnaire sur 2 cycles — un cycle en méthode Excel (référence) et un cycle avec SmartRH — reportée dans le carnet de suivi.

---

#### Métrique P2
**Indicateur :** Taux d'échéances anticipées — pourcentage des échéances de contrats et de congés du mois signalées par une alerte au moins 7 jours avant la date.

**Valeur cible à 30 jours :** 100 % des échéances de la période anticipées par une alerte (0 échéance découverte en retard).

**Comment mesurer :** Comparer la liste réelle des échéances du mois (fins de CDD, renouvellements, soldes de congés) au journal des alertes effectivement déclenchées par l'outil.

---

#### Métrique P3
**Indicateur :** Continuité hors-ligne — capacité à mener une session de travail complète sans connexion, puis à synchroniser sans perte.

**Valeur cible à 30 jours :** Au moins 1 cycle de saisie/consultation réalisé entièrement hors-ligne, suivi d'une synchronisation sans perte ni doublon de données.

**Comment mesurer :** Test en connexion dégradée (mode avion) consigné dans le journal de synchronisation, avec vérification de l'intégrité des données au retour du réseau.

---

### 🚨 Métriques d'Alerte

#### Alerte A1
**Signal :** Écart de calcul — différence entre un montant produit par SmartRH (net ou cotisation) et le montant réel attendu après contrôle.

**Seuil :** Déclenchement dès le 1er écart non expliqué sur la paie — un calcul faux est plus grave que l'absence d'outil, car il expose la PME à un redressement ou à un litige.

**Action corrective :** Gel immédiat de la fonction de calcul concernée, vérification de la donnée source et de la règle appliquée (barème SMIG/IPRES/CSS/IR), correction et test de non-régression avant tout nouvel usage.

---

#### Alerte A2
**Signal :** Retour à Excel — la gestionnaire cesse d'utiliser SmartRH et reprend son ancien fichier.

**Seuil :** Déclenchement après plus de 7 jours consécutifs sans usage de l'outil sur la PME pilote.

**Action corrective :** Entretien de friction sous 48h pour identifier la cause (confiance dans les calculs, complexité, réseau, confidentialité) et distinguer un blocage corrigeable d'un rejet de fond ; résultat présenté en rétrospective d'équipe.

---

### Tableau de Bord S6

À la démo S6, nous présenterons ces 3 chiffres :

1. **Métrique Nord — Taux de paies justes du premier coup :** X % des bulletins sans correction après clôture (cible : 100 %)
2. **Métrique P1 — Temps de production de la paie :** X minutes avant vs X minutes après SmartRH (cible : −50 %)
3. **Alerte A1 — Fiabilité des calculs :** déclenchée / non déclenchée — et si déclenchée, cause identifiée et action corrective appliquée
