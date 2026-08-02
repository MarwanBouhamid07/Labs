---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  section {
    background: #101827;
    color: #edf3fa;
    font-family: Inter, "Segoe UI", Arial, sans-serif;
    font-size: 24px;
    padding: 48px 66px;
    justify-content: center;
  }

  h1, h2 {
    color: #f7fbff;
    font-family: Anton, Impact, "Arial Narrow", sans-serif;
    font-weight: 400;
    line-height: 1;
    margin: 0 0 24px;
  }

  h1 { font-size: 94px; }
  h2 { font-size: 58px; }

  h3 {
    color: #56d6c2;
    font-size: 26px;
    margin: 0 0 10px;
  }

  ul, ol {
    font-size: 26px;
    line-height: 1.34;
  }

  li { margin-bottom: 10px; }
  strong { color: #56d6c2; }

  code {
    background: rgba(86, 214, 194, 0.14);
    border-radius: 5px;
    color: #b9fff2;
    padding: 2px 7px;
  }

  pre {
    background: #0a111d;
    border: 1px solid #2a3b50;
    border-radius: 10px;
    font-size: 18px;
    line-height: 1.32;
    padding: 16px 20px;
  }

  table {
    font-size: 19px;
    line-height: 1.2;
  }

  th, td { padding: 6px 10px; }

  section.light {
    background: #f3f6fa;
    color: #172337;
  }

  section.light h1,
  section.light h2 { color: #172337; }

  section.light h3,
  section.light strong { color: #087f73; }

  section.light code {
    background: #dceeea;
    color: #075e56;
  }

  section.light pre {
    background: #e8edf3;
    border-color: #d0d9e4;
    color: #172337;
  }

  section.title {
    justify-content: center;
    overflow: hidden;
  }

  section.title::before {
    color: rgba(86, 214, 194, 0.09);
    content: "!";
    font-family: Anton, Impact, sans-serif;
    font-size: 440px;
    line-height: 0.8;
    position: absolute;
    right: 100px;
    bottom: -50px;
  }

  section.title h1 {
    font-size: 125px;
    position: relative;
    z-index: 1;
  }

  .eyebrow {
    color: #56d6c2;
    font-size: 17px;
    font-weight: 700;
    letter-spacing: 3px;
    margin-bottom: 18px;
    text-transform: uppercase;
  }

  .small {
    font-size: 19px;
    line-height: 1.35;
  }

  .callout {
    border-left: 5px solid #56d6c2;
    margin-top: 18px;
    padding: 8px 0 8px 16px;
  }
---

<!-- _class: title -->

# Erreurs JS

---

<!-- _class: light -->

## Lab Plan

1. Introduction
2. Problems Encountered
3. Solutions Implemented

---

<div class="eyebrow">01 / Introduction</div>

## Comprendre les erreurs web

Une erreur peut apparaître dans le navigateur, dans une requête HTTP ou sur le serveur. Ce lab présente les codes HTTP et les erreurs JavaScript et PHP, puis montre comment remonter à leur cause.

### Notions abordées

- Familles de codes HTTP : `2xx`, `3xx`, `4xx` et `5xx`.
- Erreurs JavaScript et réponses `fetch()`.
- Erreurs PHP côté serveur.
- Outils de diagnostic : Console, Network et logs.

---

<!-- _class: light -->

<div class="eyebrow">02 / Problems Encountered</div>

## Symptômes fréquents

Le rapport du lab présente des cas courants à reconnaître :

- Une route ou une ressource renvoie `404`.
- Une requête échoue ou retourne un code `4xx` ou `5xx`.
- Le frontend attend du JSON mais reçoit du HTML.
- `fetch()` renvoie une réponse HTTP d’erreur sans rejeter automatiquement sa Promise.
- Une erreur JavaScript ou PHP interrompt le traitement attendu.

---

<div class="eyebrow">03 / Solutions Implemented</div>

## Une méthode de diagnostic

1. Lire le message et la pile d’appels dans la **Console**.
2. Dans **Network**, inspecter l’URL, la méthode, le statut, le payload et la réponse.
3. Vérifier le terminal ou les logs du serveur PHP.
4. Comparer le format reçu avec celui attendu (`JSON` ou `HTML`).
5. Traiter explicitement les erreurs HTTP et les erreurs de parsing.

<div class="callout">Le statut HTTP aide à localiser le problème ; il ne remplace pas l’inspection de la réponse et des logs.</div>

---

<!-- _class: light -->

<div class="eyebrow">04 / Codes HTTP</div>

## Lire la famille du statut

| Famille | Sens général | Première piste |
|:---:|:---|:---|
| **2xx** | Requête traitée avec succès | Vérifier le contenu retourné |
| **3xx** | Redirection ou validation du cache | Examiner la destination ou les en-têtes |
| **4xx** | Problème lié à la requête ou à l’accès | Vérifier URL, méthode, données et droits |
| **5xx** | Échec côté serveur ou passerelle | Consulter les logs côté serveur |

Le statut est une première indication : le détail dépend de la route et de la réponse.

---

<div class="eyebrow">05 / Réussite & redirection</div>

## Codes `2xx` et `3xx`

| Code | Signification | Exemple courant |
|:---:|:---|:---|
| `200` | OK — requête réussie | Lecture de données |
| `201` | Created — ressource créée | Création via `POST` |
| `204` | No Content — succès sans corps | Suppression réussie |
| `301` | Redirection permanente | URL déplacée |
| `302` | Redirection temporaire | Redirection provisoire |
| `304` | Ressource non modifiée | Utilisation du cache |

Pour `204`, ne tentez pas de parser un corps JSON qui n’existe pas.

---

<!-- _class: light -->

<div class="eyebrow">06 / Erreurs de requête</div>

## Codes `4xx`

| Code | Signification | À vérifier |
|:---:|:---|:---|
| `400` | Bad Request | Format et contenu de la requête |
| `401` | Unauthorized | Authentification requise ou expirée |
| `403` | Forbidden | Autorisations insuffisantes |
| `404` | Not Found | URL, route ou ressource |
| `405` | Method Not Allowed | Méthode HTTP attendue |
| `429` | Too Many Requests | Limite de fréquence |

Un code `4xx` indique généralement que le serveur n’a pas pu traiter la requête telle qu’elle a été envoyée.

---

<div class="eyebrow">07 / Erreurs serveur</div>

## Codes `5xx`

| Code | Signification | Première action |
|:---:|:---|:---|
| `500` | Erreur interne du serveur | Lire les logs serveur |
| `503` | Service indisponible | Vérifier l’état du service |
| `504` | Délai dépassé auprès d’un serveur amont | Vérifier les dépendances et délais |

Le navigateur seul ne révèle pas toujours la cause d’un `5xx` : consulter le terminal ou les journaux du backend.

---

<!-- _class: light -->

<div class="eyebrow">08 / JavaScript & PHP</div>

## Reconnaître les messages

| Message | Interprétation ou piste |
|:---|:---|
| `SyntaxError` | Syntaxe invalide, ou parsing JSON impossible |
| `ReferenceError` | Variable ou fonction non définie |
| `TypeError` | Opération incompatible avec la valeur reçue |
| `Failed to fetch` | Échec réseau, URL, serveur ou blocage navigateur |
| `Uncaught (in promise)` | Rejet de Promise non pris en charge |
| PHP `Parse error` | Erreur de syntaxe PHP |
| PHP `Undefined variable` | Variable non définie |
| PHP `Fatal error` | Erreur bloquante à examiner dans les logs |

---

<div class="eyebrow">09 / Pratique · Diagnostic</div>

## Quand JSON attendu, HTML reçu

Le serveur peut retourner une page HTML d’erreur (par exemple une page `404` ou `500`). Appeler directement `response.json()` peut alors provoquer une `SyntaxError`.

```javascript
const response = await fetch("/api/genres");

console.log(response.status);
console.log(response.headers.get("content-type"));

const body = await response.text();
console.log(body);
```

Dans DevTools, inspectez aussi **Network → requête → Response** pour voir le corps réellement reçu.

---

<!-- _class: light -->

<div class="eyebrow">10 / Pratique · Traiter `fetch()`</div>

## Vérifier le statut avant le JSON

`fetch()` rejette notamment en cas d’échec réseau, mais un statut HTTP comme `404` ne rejette pas automatiquement la Promise. Vérifiez `response.ok` avant d’utiliser le corps comme JSON.

```javascript
const response = await fetch("/api/genres");

if (!response.ok) {
  throw new Error(`HTTP ${response.status}`);
}

const genres = await response.json();
console.log(genres);
```

Le corps peut aussi être vide ou ne pas être du JSON : adaptez le parsing au contrat de l’API.

---

<div class="eyebrow">11 / Workflow de débogage</div>

## Suivre la requête de bout en bout

1. **Console** — relever le message et la ligne concernée.
2. **Network** — contrôler URL, méthode, statut, payload et réponse.
3. **Frontend** — vérifier le traitement du statut et le parsing.
4. **Backend** — lire l’erreur et le contexte dans les logs PHP.
5. **Reproduire** — corriger une cause à la fois puis refaire la requête.

<div class="callout">Suivez le même appel du navigateur au serveur au lieu de déduire la cause à partir d’un seul message.</div>

---

<!-- _class: light -->

<div class="eyebrow">12 / À retenir</div>

## Observer, localiser, vérifier

**Console** &nbsp; + &nbsp; **Network** &nbsp; + &nbsp; **logs serveur** &nbsp; → &nbsp; **diagnostic vérifiable**

- Les familles HTTP orientent vers la zone à inspecter.
- Les messages JavaScript décrivent le symptôme côté navigateur.
- Les logs PHP aident à trouver la cause côté serveur.
- Vérifiez toujours le statut et le format avant de traiter la réponse.
