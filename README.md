

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
