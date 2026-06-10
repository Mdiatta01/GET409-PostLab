## Connexions 6 Chapeaux → VPC — SmartRH

### Profil Client — Origines

#### Jobs To Be Done
| Job | Chapeau d'origine | Citation exacte |
|---|---|---|
| Produire chaque mois une paie juste intégrant SMIG, IPRES, CSS et IR sans calcul manuel | Chapeau Blanc | "le calcul de paie intègre manuellement le SMIG, l'IPRES, la CSS et l'IR, ce qui multiplie les sources d'erreur à chaque cycle mensuel" |
| Suivre CDD/CDI, renouvellements et soldes de congés, et être prévenue avant chaque échéance | Chapeau Blanc | "les renouvellements de contrats et les soldes de congés ne sont aujourd'hui suivis par aucune alerte automatique : les échéances sont repérées au feeling ou découvertes en retard" |
| Gérer la RH avec peu de temps et de budget, depuis Excel, smartphone et WhatsApp | Chapeau Blanc | "Fatou cumule la RH avec d'autres fonctions : elle n'a ni temps de formation long ni budget logiciel élevé, mais utilise WhatsApp quotidiennement comme canal de travail principal" |

#### Pains
| Pain | Chapeau d'origine | Citation exacte |
|---|---|---|
| Anxiété du jour de paie — l'erreur de net engage la crédibilité | Chapeau Rouge | "Fatou ressent une anxiété récurrente autour du jour de paie : la peur de se tromper sur un salaire net engage sa crédibilité" |
| Résistance émotionnelle si l'outil remplace Excel au lieu de le prolonger | Chapeau Rouge | "tout outil perçu comme remplaçant plutôt que prolongeant son fichier risque de déclencher une résistance émotionnelle" |
| Dépendance au réseau — système en ligne inutilisable lors des coupures | Chapeau Noir | "les coupures réseau et data limitée rendent risqué un système 100 % en ligne ; un outil inutilisable hors-ligne sera abandonné" |
| Exposition des salaires — fuite ou accès partagé détruit la confiance | Chapeau Noir | "centraliser la paie sur un outil connecté expose des données très sensibles ; une fuite ou un accès partagé mal géré détruirait la confiance instantanément" |

#### Gains
| Gain | Chapeau d'origine | Citation exacte |
|---|---|---|
| Gagner du temps — quelques clics au lieu d'heures de calcul | Chapeau Jaune | "automatiser le calcul paie + cotisations transforme plusieurs heures mensuelles en quelques clics" |
| Adopter sans courbe d'apprentissage via un canal déjà maîtrisé | Chapeau Jaune | "un système qui parle le canal que Fatou et les employés utilisent déjà réduit drastiquement la courbe d'apprentissage" |
| Protéger la PME en cas de contrôle ou de litige | Chapeau Jaune | "un outil qui sécurise contrats, congés et déclarations sociales protège la PME en cas de contrôle ou de litige" |

---

### Proposition de Valeur — Origines

#### Produits & Services
| Produit / Service | Job ou Pain adressé | Chapeau d'origine |
|---|---|---|
| Moteur de paie automatisé (SMIG/IPRES/CSS/IR) + alertes d'échéances | Job "produire une paie juste" + Job "être prévenue avant chaque échéance" | Chapeau Vert |
| Bot WhatsApp + tableau de bord de synthèse | Job "gérer depuis WhatsApp" + Gain "adopter sans courbe d'apprentissage" | Chapeau Vert |
| Architecture offline-first + import/export Excel + freemium | Pain "dépendance au réseau" + Pain "résistance au changement" | Chapeau Vert |

#### Pain Relievers
| Pain Reliever | Pain adressé | Chapeau d'origine |
|---|---|---|
| Calcul des cotisations automatisé et traçable (zéro ressaisie) | Anxiété du jour de paie — erreur engageant la crédibilité | Chapeau Noir (mitigation du risque "calcul manuel = erreur") |
| Fonctions cœur disponibles hors-ligne + synchro au retour réseau | Dépendance au réseau — système en ligne inutilisable | Chapeau Noir (mitigation du risque "100 % en ligne inutilisable hors-ligne") |
| Accès par rôle + aucun salaire en clair sur WhatsApp | Exposition des salaires — fuite détruit la confiance | Chapeau Noir (mitigation du risque "accès partagé mal géré") |

#### Gain Creators
| Gain Creator | Gain adressé | Chapeau d'origine |
|---|---|---|
| Automatisation paie + cotisations, mesurée avant/après sur un cycle | Gagner du temps | Chapeau Jaune ("quelques clics") + Chapeau Bleu ("mesure avant/après : temps, erreurs, échéances ratées") |
| SmartRH prolonge Excel (import/export) au lieu de le remplacer | Adopter sans friction + neutraliser la résistance émotionnelle | Chapeau Jaune ("familiarité WhatsApp") + Chapeau Vert ("Excel comme pont plutôt que rival") |
| Contrats/congés/déclarations sécurisés sous gouvernance définie | Protéger la PME + conformité défendable | Chapeau Jaune ("valeur que les dirigeants paient") + Chapeau Bleu ("cadrer dès le départ la gouvernance des données") |

---

### Éléments Non Tracés

- **Pointage présences/congés self-service par les employés (bot WhatsApp)** → répond au sentiment d'opacité des employés identifié dans le Chapeau Rouge ("mes congés, mes heures, mon contrat sont dans la tête de quelqu'un d'autre") mais sans Gain Creator dédié et repoussé hors du noyau MVP — [Non tracé comme fonctionnalité MVP — à valider en interview S3 : la visibilité employés est-elle un déclencheur d'adoption ou un confort V2 ?]
- **Modèle freemium par paliers** → identifié dans le Chapeau Vert comme levier d'adoption et réponse au risque de coût du Chapeau Noir, mais relève du modèle économique et non de la proposition de valeur d'usage — [Non tracé comme fonctionnalité — à intégrer dans la stratégie go-to-market, hors VPC]
- **Pilote sur 3 à 5 PME pendant un cycle de paie complet** → identifié dans le Chapeau Bleu comme prérequis de validation mais non représenté dans le VPC comme Produit, Service ou Gain Creator — [Non tracé comme activité clé — à intégrer dans la roadmap opérationnelle S3, hors VPC]

---

### Synthèse de Cohérence

**Alignement :** Fort sur le cœur du service — les 3 Jobs, les 4 Pains et les 3 Gains du profil client ont chacun au moins un Pain Reliever ou Gain Creator correspondant, et chaque élément du VPC est traçable à au moins un chapeau source.

**Tension principale :** Le Pain Reliever "accès par rôle + aucun salaire en clair sur WhatsApp" (Chapeau Noir) entre en tension avec le Produit "bot WhatsApp" (Chapeau Vert) : WhatsApp est à la fois le canal d'adoption privilégié et le canal le plus exposé pour des données sensibles. La proposition de valeur ne peut tenir que si le bot WhatsApp se limite aux actions non sensibles (pointage, demande de congé, alertes génériques) et renvoie toute donnée salariale vers l'interface authentifiée.

**Recommandation avant S3 :** Conduire un entretien terrain de 20 minutes avec 3 à 5 gestionnaires RH de fait pour valider laquelle des deux promesses — paie fiable ou alerte d'échéance — déclenche réellement l'adoption dès le premier cycle (question ouverte du Chapeau Bleu), et tester quel niveau d'information salariale Fatou accepte de voir transiter par WhatsApp.
