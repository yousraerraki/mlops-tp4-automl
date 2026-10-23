# Comparatif des approches - projet fraude (TP04)

| Approche | F1 test | Temps humain | Temps machine | Cout estime (source, date) | Explicabilite | Export / reversibilite |
|---|---|---|---|---|---|---|
| Logistique (ref.) | 0.7407 | A COMPLETER | 0.04 s | 0 (poste local) | Maximale | Totale |
| Manuel (TP2) | 0.8669 | A COMPLETER | 1.19 s | 0 (poste local) | Moyenne/Bonne | Totale |
| FLAML 60 s | 0.8582 | A COMPLETER | 60.5 s | 0 (poste local) | Moyenne/Basse | Totale |
| Vertex AI AutoML | non mesure | A COMPLETER | non mesure | 21.252 USD par heure-noeud (entrainement tabulaire), cloud.google.com/vertex-ai/pricing, 23/10/2026 | Bonne (Explainable AI) | A verifier (doc) |
| SageMaker Autopilot | non mesure | A COMPLETER | non mesure | ~2.3 a 9.2 USD pour un jeu < 100 Mo (Canvas), aws.amazon.com/sagemaker/canvas/pricing, 23/10/2026 | Bonne | A verifier (doc) |
| Azure Automated ML | non mesure | A COMPLETER | non mesure | Pas de surcout AutoML, calcul facture a la seconde, azure.microsoft.com/pricing/details/machine-learning, 23/10/2026 | Bonne (Responsible AI) | A verifier (doc) |

## Commentaire (5 lignes)

1. Logistique : reference obligatoire, a privilegier quand explicabilite, latence ou audit priment.
2. Manuel : utile quand on connait bien les donnees et que l'espace de recherche est petit.
3. FLAML local : prototypage rapide, plusieurs familles, donnees gardees sur le poste, cout nul. Gain surtout entre 10 s et 30 s, puis plateau (0.858 a 30 s et 60 s, 0.856 a 120 s).
4. Plateformes managees : equipes sans infrastructure, besoin de registre, endpoints et monitoring. Attention a la facture et au verrouillage fournisseur.
5. Dans tous les cas, l'AutoML ne remplace pas la validation des donnees (fuite : F1 test 1.0 puis F1 production 0.0), le choix de la metrique ni le monitoring.
