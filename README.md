# Astro on Netlify Platform Starter

SHA256:tyUzMRJHrlScUn1NmOj5RQOsyTpwxsomFu/P/4NGCDU
[Live Demo](https://astro-platform-starter.netlify.app/)

A modern starter based on Astro.js, Tailwind, and [Netlify Core Primitives](https://docs.netlify.com/core/overview/#develop) (Edge Functions, Image CDN, Blob Store).

## Astro Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## Deploying to Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/netlify-templates/astro-platform-starter)

## Developing Locally

| Prerequisites                                                                |
| :--------------------------------------------------------------------------- |
| [Node.js](https://nodejs.org/) v18.14+.                                      |
| (optional) [nvm](https://github.com/nvm-sh/nvm) for Node version management. |

1. Clone this repository, then run `npm install` in its root directory.

2. For the starter to have full functionality locally (e.g. edge functions, blob store), please ensure you have an up-to-date version of Netlify CLI. Run:

```
npm install netlify-cli@latest -g
```

3. Link your local repository to the deployed Netlify site. This will ensure you're using the same runtime version for both local development and your deployed site.

```
netlify link
```

4. Then, run the Astro.js development server via Netlify CLI:

```
netlify dev
```

If your browser doesn't navigate to the site automatically, visit [localhost:8888](http://localhost:8888).

// mailzeet_bot.js
// Auteur : Héoumi

// Étape 1 : Importation des modules
import fetch from "node-fetch";

// Étape 2 : Variables principales
const API_KEY = "TA_CLE_API_MAILZEET"; // remplace ici par ta vraie clé
const API_URL = "https://api.mailzeet.com/v1/send"; // URL de l'API Mailzeet

// Étape 3 : Fonction pour envoyer un mail automatique
async function sendAutoMail(name, email) {
  const data = {
    to: email,
    subject: "Bienvenue dans la team Héoumi 🔥",
    html: `<h2>Salut ${name} !</h2>
           <p>Tu viens de rejoindre une communauté ambitieuse et créative 🌍</p>
           <p>Découvre nos formations ici : <a href="https://heoumi-sousdomaine-1.systeme.io/a596ab6f">Accéder</a></p>
           <br><p>— L’équipe Héoumi</p>`,
  };

  const response = await fetch(API_URL, {
    method: "POST",
    headers: {
      "Authorization": `Bearer ${API_KEY}`,
      "Content-Type": "application/json",
    },
    body: JSON.stringify(data),
  });

  if (response.ok) {
    console.log(`✅ Email envoyé à ${email}`);
  } else {
    console.error("❌ Erreur d’envoi :", await response.text());
  }
}

// Exemple : appel automatique
sendAutoMail("Nouvel Abonné", "client@example.com");
