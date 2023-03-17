# Titre de la compétence

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'état (_state_) pour contrôler l'affichage d'un composant ✔️
    `Utilisation d'un hook qui se nomme useState, doit être importer depuis react et est utiliser dans l'objectif de stocké des informations.
    ex: const [users, setUsers] = useState([]);
    Dans cette exemple users est la varible qui va être utiliser pour afficher les datas. le setUsers quand a lui va permettre de moidifier le state.`
- les composants enfants et les _props_ qu'on leur passe ✔️
    `Les props sont des informations que l'on va paser d'un composant parent a un composant enfants. Les props peuvent être utiliser par l'enfant et modifier 
    celui-ci puis le faire remonter au parent.
    ex: <UserCard data={users} />`
- le déclenchement d'instructions en fonction des actions de l'utilisateur ✔️
- le déclenchement d'instructions en fonction de l'étape du cycle de vie du composant ou du changement de valeur de ses props ✔️
- l'usage d'un reducer (_useReducer_) pour gérer un état composé dans un composant
- l'état stocké dans un composant avec un _context provider_ et accessible dans ses descendants via `useContext` ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

```
import PropTypes from "prop-types";
import "./style.scss";
import { Link } from "react-router-dom";
import ProgressBar from "@components/ProgressBar/ProgressBar";
import { useEffect, useState } from "react";
import axios from "axios";

export default function SuggestCardToForm({ suggestData }) {
  const [counter, setCounter] = useState([]);
  useEffect(() => {
    axios
      .get(
        `${import.meta.env.VITE_BACKEND_URL}/suggests/countcomments/${
          suggestData.id
        }`
      )
      .then(({ data }) => {
        setCounter(data);
      });
  }, []);
  return (
    <Link to={`/suggestform/${suggestData.id}`} className="suggestBlock">
      <article className="card">
        <h2 className="titleCard">{suggestData.title}</h2>
        <ProgressBar priority={suggestData.priority} />
        <div className="footerCard">
          <p className="opinion">Opinions({counter.count})</p>
        </div>
      </article>
    </Link>
  );
}

SuggestCardToForm.propTypes = {
  suggestData: PropTypes.shape({
    title: PropTypes.string.isRequired,
    id: PropTypes.number.isRequired,
    priority: PropTypes.number.isRequired,
  }).isRequired,
};
```

### Utilisation dans un projet  ✔️

[lien github]https://github.com/Sax593/makesense

Description : Projet de formation, en lien avec une entreprise (MakeSense) qui a pour but la gestion d'idéation au sein de l'entreprise. Avec un backOffice, un espace de discution pour les memebres de l'entreprise.

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ✔️

https://github.com/Sax593/makesense

Description : Projet de formation, en lien avec une entreprise (MakeSense) qui a pour but la gestion d'idéation au sein de l'entreprise. Avec un backOffice, un espace de discution pour les memebres de l'entreprise.

## 🌐 J'utilise des ressources

### Titre
- lien
- description

### Documentation react
- [lien](https://fr.reactjs.org/)
- Documentation officiel de réact

### Documentation react admin
- https://marmelab.com/react-admin/
- Documentation officiel de réact admin. Outils permettant d'avouter un backOffice a nos application réact.

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
