# Embodied AI Journey — Yassine Inkatto

Dépôt de travail documentant ma progression vers la robotique apprenante
(reinforcement learning, imitation learning, sim-to-real), dans le cadre
d'une feuille de route personnelle sur deux ans.

Élève-ingénieur en Génie Électromécanique & Digitalisation Industrielle,
ENSAM Meknès.

---

## Objectif du dépôt

Documenter, de façon honnête et vérifiable, la construction progressive
des fondations nécessaires à la robotique apprenante — en partant d'une
base en systèmes embarqués, ROS2 et cinématique, vers l'apprentissage
par renforcement et l'imitation learning appliqués à des systèmes
physiques réels.

Chaque notebook contient le code, les vérifications effectuées, et les
erreurs rencontrées en cours de route — pas seulement le résultat final.

---

## Progression

### 01 — Micrograd : moteur de différentiation automatique
**Statut : en cours**

Ré-implémentation, à la main et sans copier-coller, du moteur `Value`
de [micrograd](https://github.com/karpathy/micrograd) (Andrej Karpathy),
suivie de la construction manuelle d'un petit réseau de neurones.

Contenu couvert à ce jour :
- Classe `Value` : stockage de données, construction du graphe de calcul
  (`_prev`, `_op`)
- Opérations : `__add__`, `__mul__`, `__pow__`, `relu`, négation unaire
- Vérification indépendante des dérivées par différences finies
  (comparaison forward pass vs. gradient numérique)
- Test de validation multi-opérations ("torture test") : addition,
  multiplication, puissance, division, ReLU et accumulation `+=`
  combinés dans un seul graphe

À venir :
- Implémentation de `backward()` (backpropagation automatique via tri
  topologique)
- Classes `Neuron`, `Layer`, `MLP`
- Boucle d'entraînement par descente de gradient sur un jeu de données
  simple
- Comparaison de l'implémentation avec PyTorch

Notebook : [`karpathy-s-micrograd-ep1.ipynb`](./karpathy-s-micrograd-ep1.ipynb)

---

## Méthodologie

Chaque résultat de gradient est, dans la mesure du possible, vérifié par
au moins une méthode indépendante de la source du tutoriel (différences
finies, calcul manuel, ou comparaison avec un framework établi comme
PyTorch), plutôt qu'accepté simplement parce qu'il correspond à la
vidéo de référence.

---

## Stack

Python · MuJoCo · Gymnasium · Stable-Baselines3 · PyTorch (à venir) ·
LeRobot (à venir)

---

## Contexte

Ce dépôt s'inscrit dans une feuille de route plus large : cinématique
inverse → planification de mouvement → apprentissage (RL / imitation) →
sim-to-real, avec pour plateforme matérielle cible un bras robotique
(écosystème LeRobot).

Profil complet : [Portfolio](https://yassineinkatto.github.io/Portfolio/) ·
[LinkedIn](https://linkedin.com/in/yassine-inkatto) ·
[Kaggle](https://www.kaggle.com/yassineinkatto)

---

*Dernière mise à jour : 04 juillet 2026*
