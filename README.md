# Optimisation de tournées de véhicules avec dépendances

## 📚 Aperçu du projet
Ubaze est un proof‑of‑concept réalisé sous forme de _notebook_ Jupyter (`Ubaze.ipynb`) qui illustre **la résolution d’un Vehicle Routing Problem (VRP) avec contraintes de dépendance/précédence entre points de livraison**. Le projet couvre la **génération d’instances réalistes**, la **modélisation exacte** avec _PuLP_ et deux méta‑heuristiques :

* **Recherche Tabou**
* **Algorithme Génétique**

Des expériences mesurent ensuite la qualité des solutions et les temps d’exécution selon la taille de l’instance et les paramètres algorithmiques.

---

## 🗂️ Contenu du dépôt
| Élément | Rôle |
|---------|------|
| `Ubaze.ipynb` | Notebook principal : génération des données, modélisation VRP, heuristiques, analyses et graphes |
| `README.md` | Le document que vous lisez – mode d’emploi et contexte |
| `requirements.txt` | Dépendances Python proposées (à générer avec `pip freeze` si besoin) |

> **Astuce :** si vous ne travaillez qu’avec le notebook, un simple `pip install` des dépendances ci‑dessous suffit.

---

## ⚙️ Dépendances
Le projet s’appuie sur l’écosystème scientifique Python :

```bash
python >= 3.9
numpy
pandas
matplotlib
networkx
pulp
faker
```

Installez‑les via :

```bash
pip install -r requirements.txt  # ou installez individuellement
```

---

## 🚀 Prise en main rapide
1. **Clonez** le dépôt ou copiez `Ubaze.ipynb` et `requirements.txt`.
2. Créez un **environnement virtuel** (recommandé) :

   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/macOS
   .venv\Scripts\activate    # Windows
   ```

3. **Installez** les dépendances.
4. **Lancez** :

   ```bash
   jupyter notebook Ubaze.ipynb
   ```

5. Exécutez les cellules étape par étape – chaque grande section est clairement titrée :
   - _I/ Génération des instances_
   - _Modélisation (PuLP)_
   - _Recherche Tabou_
   - _Algorithme Génétique_
   - _Plan d’expérience & analyse des résultats_

---

## 🏗️ Architecture du notebook
| Section | Points clés |
|---------|-------------|
| **Génération des instances** | Création de graphes complets de villes synthétiques (librairie **Faker**) et distances euclidiennes ; ajout aléatoire de contraintes de précédence |
| **Modélisation VRP** | Formulation en Programme Linéaire Mixte avec **PuLP** : variables d’arêtes, contraintes de flux, de dépendance et de capacité ; résolution avec `CBC` |
| **Recherche Tabou** | Heuristique itérative avec liste tabou, stratégie d’aspiration et diversification |
| **Algorithme Génétique** | Encodage par permutations, opérateurs de croisement/mutation et sélection élitiste |
| **Analyse expérimentale** | Boucles d’expérimentation (nombre de villes, seuils tabou, taille population…) ; mesure **qualité vs. temps** et visualisations **matplotlib** |

---

## 📊 Principaux résultats (exemple)
* La modélisation exacte donne la solution optimale pour ≤ 20 villes mais devient coûteuse au‑delà.
* La recherche tabou converge rapidement (quelques secondes) et fournit une solution ≤ 5 % de l’optimum sur des instances de 50 villes.
* L’algorithme génétique reste plus stable sur les grandes tailles (> 100 villes) mais nécessite un réglage fin de la population.

> Ces chiffres varient selon la graine aléatoire ; lancez le plan d’expérience pour reproduire.

---

## 📜 Licence
Distribué sous licence **MIT** — voir le fichier `LICENSE` (à créer si nécessaire).

## 👩‍💻 Auteurs
*WB - SL - AT - FC*  
CESI — 2025

N’hésitez pas à ouvrir des *issues* ou des *pull‑requests* ! :)


