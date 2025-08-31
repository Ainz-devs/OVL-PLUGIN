<h1 align="center">OVL-PLUGIN 🚀</h1>

## 🌐 Installer un plugin

Installez un plugin via une URL publique avec la commande :

```bash
[prefixe]pgi <url>
```

### Exemple :

```bash
pgi https://gist.githubusercontent.com/username/abcd1234/raw/mon_plugin.js
```

---

## ⚡ Créer vos propres plugins

Pour créer votre plugin :

1. Écrivez le code de votre plugin en suivant la structure ci-dessous.
2. Uploadez-le sur [**Gist**](https://gist.github.com) pour obtenir un lien direct raw.
3. Récupérez le **lien direct raw** de votre fichier.

```javascript
const { ovlcmd } = require('../lib/ovlcmd');

ovlcmd(
  {
    nom_cmd: "",       // Nom de la commande (ex: 'delete')
    alias: [],           // Alias de la commande (optionnel)
    react: "",          // Emoji de réaction (optionnel)
    classe: "",        // Catégorie du plugin (ex: Owner, Outils, Fun, Convert)
    desc: ""            // Brève description du plugin
  },
  async (ms_org, ovl, {}) => {
    // logique du plugin
  }
);
```

> **Remarque :** le nom de la commande (`nom_cmd`) doit être en **minuscules**, **sans espace** et sans caractères spéciaux. Les alias doivent suivre les mêmes règles.

### Exemple simple de plugin

```javascript
const { ovlcmd } = require('../lib/ovlcmd');

ovlcmd(
  {
    nom_cmd: "mon_plugin",
    react: "💡",
    classe: "Outils",
    desc: "Envoie un message simple"
  },
  async (ms_org, ovl, {}) => {
    await ovl.sendMessage(ms_org, {
      text: "Hello, c'est mon plugin !"
    });
  }
);
```

---

## 📦 Publier un plugin

Pour ajouter votre plugin dans la liste officielle **OVL-PLUGIN** :

1. Contactez le développeur (mainteneur du projet).
2. Fournissez les infos suivantes :

   * **nom** : nom du plugin
   * **description** : description du plugin
   * **url** : lien direct vers le fichier raw du plugin ([Gist](https://gist.github.com))
   * **auteur** : nom de l'auteur du plugin
