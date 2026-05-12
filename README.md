#  COVID-19 Dashboard

Un tableau de bord interactif et responsive pour visualiser les données mondiales de la pandémie COVID-19 (2020–2023). Construit en HTML, CSS et JavaScript pur — aucune dépendance à installer.

![Dashboard Preview](https://img.shields.io/badge/status-stable-brightgreen) ![HTML](https://img.shields.io/badge/HTML-5-orange) ![CSS](https://img.shields.io/badge/CSS-3-blue) ![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow) ![Chart.js](https://img.shields.io/badge/Chart.js-4.4.1-ff6384) ![License](https://img.shields.io/badge/license-MIT-green)

---

##  Aperçu

<img width="926" height="533" alt="image" src="https://github.com/user-attachments/assets/39885e12-6a4a-4b28-a8c8-6801c8f2cc1b" />


Le dashboard présente en une seule page :

- **5 métriques clés** — cas confirmés, décès, guérisons, doses vaccinales, pays touchés
- **Graphique principal interactif** (3 onglets : Cas / Décès / Vaccination)
- **Donut de répartition** des cas par région
- **Tableau des régions** les plus touchées avec barres de progression
- **Barres de couverture vaccinale** par catégorie de pays
- **Graphique des variants** (souche originale → Alpha → Delta → Omicron BA.1/BA.4/5)

---

##  Démarrage rapide

Aucune installation requise. Il suffit d'ouvrir le fichier dans un navigateur :

```bash
# Cloner le dépôt
git clone https://github.com/votre-username/covid19-dashboard.git
cd covid19-dashboard

# Ouvrir directement dans le navigateur
open covid19_dashboard.html         # macOS
xdg-open covid19_dashboard.html    # Linux
start covid19_dashboard.html        # Windows
```

Ou via un serveur local :

```bash
# Python 3
python -m http.server 8000
# puis ouvrir http://localhost:8000
```

---

##  Structure du projet

```
covid19-dashboard/
└── covid19_dashboard.html   # Application complète (HTML + CSS + JS)
└── README.md
```

Tout est contenu dans un seul fichier HTML autonome. Les dépendances (Chart.js et Tabler Icons) sont chargées via CDN.

---

##  Dépendances CDN

| Bibliothèque | Version | Usage |
|---|---|---|
| [Chart.js](https://www.chartjs.org/) | 4.4.1 | Graphiques interactifs |
| [Tabler Icons](https://tabler-icons.io/) | latest | Icônes UI |

Aucune installation npm / pip requise.

---

##  Données

Les données présentées sont **illustratives** et basées sur les rapports officiels publiés par :

- [Organisation Mondiale de la Santé (OMS)](https://www.who.int/emergencies/diseases/novel-coronavirus-2019)
- [Johns Hopkins University CSSE](https://github.com/CSSEGISandData/COVID-19)
- [Our World in Data](https://ourworldindata.org/covid-vaccinations)

Les chiffres couvrent la période **janvier 2020 – avril 2023**.

> Pour connecter des données en temps réel, remplacer les tableaux JS dans le fichier par des appels à l'[API disease.sh](https://disease.sh/) ou à l'[API OMS](https://covid19.who.int/).

---

##  Fonctionnalités

- **Thème sombre** complet, optimisé pour la lisibilité
- **Onglets interactifs** pour basculer entre Cas / Décès / Vaccination
- **Tooltips** contextuels sur tous les graphiques
- **Responsive** — s'adapte aux petits écrans (grilles CSS auto-fit)
- **Accessibilité** — attributs `aria-label` et `role="img"` sur les canvas

---

##  Personnalisation

### Modifier les données

Les données sont définies dans des tableaux JS en bas du fichier `<script>` :

```js
// Exemple : modifier les métriques principales
const regions = [
  { name: 'Europe',         cas: 251, color: '#3b9eff', pct: 36 },
  { name: 'Asie-Pacifique', cas: 210, color: '#1dd1a1', pct: 30 },
  // ...
];
```

### Connecter une API externe

```js
// Remplacer les données statiques par un fetch()
const res = await fetch('https://disease.sh/v3/covid-19/all');
const data = await res.json();
// data.cases, data.deaths, data.recovered...
```

### Modifier le thème

Les couleurs sont définies en variables CSS en tête du fichier :

```css
:root {
  --bg-primary: #0a0e1a;
  --red: #ff4757;
  --blue: #3b9eff;
  --green: #2ed573;
  /* ... */
}
```

---

##  Compatibilité navigateurs

| Navigateur | Support |
|---|---|
| Chrome 90+ | ✅ |
| Firefox 88+ | ✅ |
| Safari 14+ | ✅ |
| Edge 90+ | ✅ |

---

## Licence

Ce projet est distribué sous licence **MIT**. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

---

## Contribution

Les contributions sont les bienvenues !

1. Forker le dépôt
2. Créer une branche (`git checkout -b feature/ma-fonctionnalite`)
3. Commiter les changements (`git commit -m 'feat: ajout de la carte mondiale'`)
4. Pousser la branche (`git push origin feature/ma-fonctionnalite`)
5. Ouvrir une Pull Request

---

*Données à titre informatif uniquement. Pour des informations médicales officielles, consulter l'[OMS](https://www.who.int/).*
