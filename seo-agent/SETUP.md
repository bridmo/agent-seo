# Guide d'onboarding — Bootstrapper votre agent SEO

Ce guide vous accompagne pour remplir chaque fichier contexte a partir de vos donnees brutes. L'objectif : donner a l'agent suffisamment de contexte pour qu'il produise une strategie SEO pertinente et des articles de qualite.

---

## Vue d'ensemble

```
Vos donnees brutes                    Fichiers contexte
─────────────────                     ────────────────
Site web, LP                    →     product-marketing-context.md
Transcripts de calls            →     icp-bible.md
Guidelines, exemples articles   →     voice-tone.md
Connaissance marche             →     competitors.md
Ahrefs / recherche manuelle     →     competitors-seo.md
GSC, blog existant              →     channels-seo.md
Pages produits, pricing         →     products.md
```

---

## Fichier 1 : product-marketing-context.md

### Ce que c'est
La carte d'identite de votre business vue par le marketing. Ce que vous vendez, a qui, comment, et pourquoi vous plutot qu'un autre.

### Comment le remplir

**Source la plus rapide :** Votre site web + vos landing pages.

**Prompt a utiliser :**
```
Lis mon site [URL] et remplis le template product-marketing-context.md :
- Nom, URL, entite legale
- What it is / What it is NOT
- Positionnement en une phrase
- Liste des produits avec prix
- ICP resume (qui achete ?)
- Liste des fichiers de contexte disponibles
```

### Donnees necessaires
- Nom de l'entreprise et URL
- Description en 2 phrases (ce que c'est / ce que ce n'est pas)
- Positionnement vs concurrents
- Catalogue produits avec prix
- Profil client type (meme approximatif)
- Certifications, labels, elements de credibilite

---

## Fichier 2 : icp-bible.md (le plus important)

### Ce que c'est
Le document maitre sur vos clients. Pas un persona marketing generique — un portrait base sur des donnees reelles : ce qu'ils disent, ce qu'ils ressentent, ce qui les bloque, ce qui les fait acheter.

### Pourquoi c'est crucial pour le SEO
Chaque article sera ancre dans un pain reel de votre ICP. Sans ICP bible, l'agent ecrit du contenu generique qui ne convertit pas.

### Sources de donnees (par ordre de valeur)

| Source | Ce qu'on en tire | Comment l'obtenir |
|--------|-----------------|-------------------|
| **Transcripts de calls commerciaux** | Verbatims exacts, objections, declencheurs d'achat, langage naturel du client | Gong, Chorus, enregistrements Zoom, notes de calls |
| **Transcripts de calls support/CS** | Problemes recurrents, frustrations, cas d'usage reels | Intercom, Zendesk, enregistrements |
| **Transcripts de reunions internes** | Retours terrain des commerciaux, patterns observes | Notes de reunion, enregistrements |
| **CRM (HubSpot, Salesforce...)** | Donnees demographiques, taille entreprise, secteur, cycle de vente | Export CRM ou MCP HubSpot |
| **Enquetes clients** | NPS, raisons d'achat, satisfaction | Typeform, Google Forms, SurveyMonkey |
| **Avis en ligne** | Verbatims non filtres, points forts/faibles percus | Google, Trustpilot, G2, Capterra |
| **Reseaux sociaux** | Questions posees, langage utilise, frustrations exprimees | LinkedIn, Twitter, groupes Facebook |
| **Analytics site** | Pages les plus vues, parcours, taux de rebond | Google Analytics, Hotjar |

### Prompt pour analyser des transcripts

```
Voici [N] transcripts de calls commerciaux. Analyse-les et remplis le template icp-bible.md :

Pour chaque transcript, extrais :
1. Le profil du prospect (poste, experience, situation)
2. Le declencheur : pourquoi il nous contacte maintenant ?
3. Les pain points exprimes (citations exactes entre guillemets)
4. Les objections soulevees
5. Le langage utilise (mots et expressions recurrents)
6. Le resultat du call (achat, hesitation, refus + raison)

Puis synthetise sur l'ensemble des transcripts :
- Les 5-7 pain points les plus frequents avec verbatims representatifs
- Les 3-5 triggers d'achat principaux
- Les objections recurrentes et comment elles sont resolues
- Les personas qui emergent (regrouper les profils similaires)
- Le vocabulaire naturel des prospects (pas le jargon marketing)
```

### Prompt si vous n'avez PAS de transcripts

```
Je vais te decrire mes clients. Aide-moi a construire une ICP bible.

Mon entreprise : [description]
Mes clients typiques : [description]
Ce qu'ils me disent souvent : [ce que vous entendez en call/email]
Pourquoi ils achetent : [vos hypotheses]
Pourquoi ils hesitent : [objections courantes]

Pose-moi des questions pour completer les zones d'ombre.
```

### Structure du fichier ICP Bible

Le template dans `agents/icp-bible.md` contient ces sections :

1. **Donnees demographiques** — age, poste, experience, secteur, taille entreprise
2. **Situation professionnelle** — en poste, en recherche, freelance, % de chaque
3. **Pain points** — les 5-7 problemes majeurs avec verbatims reels
4. **Triggers d'achat** — ce qui fait passer de "j'y pense" a "j'achete"
5. **Objections** — freins a l'achat et comment ils sont resolus
6. **Parcours d'achat** — d'ou viennent-ils, combien de temps avant d'acheter
7. **Langage** — mots et expressions utilises naturellement
8. **Ce qu'ils veulent vs ce dont ils ont besoin** — le desire vs le reel

> **Important :** Separez les univers de pains. Si vous vendez plusieurs produits (ex: un produit IA et un produit marketing), les pains sont differents. Ne les melangez pas dans les articles — un article sur l'IA doit ancrer dans les pains IA, un article sur le marketing dans les pains marketing.

---

## Fichier 3 : voice-tone.md

### Ce que c'est
Les regles editoriales pour que tous les articles aient le meme ton.

### Comment le remplir

**Si vous avez des guidelines existantes :** Copiez-les et adaptez au template.

**Si vous n'en avez pas :**

```
Voici 3 articles/posts que j'ai ecrits et dont je suis content du ton :
[coller les textes]

Analyse le ton et remplis le template voice-tone.md :
- Style general (direct/formel, tutoiement/vouvoiement, etc.)
- Phrases signatures ou formulations recurrentes
- Ce qu'on evite
- Vocabulaire recurrent du secteur
```

### Elements a definir
- **Tutoiement ou vouvoiement** — choix fondamental qui impacte tout le contenu
- **Niveau de formalite** — expert accessible vs prof academique vs pote
- **Anglicismes** — acceptes ou traduits systematiquement
- **Longueur des phrases** — courtes et percutantes ou developpees
- **Emojis** — jamais, parfois, souvent
- **Humour** — absent, subtil, assume

---

## Fichier 4 : competitors.md

### Ce que c'est
La liste de vos concurrents directs avec positionnement et forces/faiblesses.

### Comment le remplir

```
Voici mes 3-5 concurrents principaux : [noms + URLs]

Pour chacun, analyse :
- Positionnement (comment ils se presentent)
- Produits et prix
- Forces et faiblesses perçues
- Ce qui les differencie de nous
```

### Donnees utiles
- URLs des concurrents
- Leurs pages de prix
- Leurs pages "a propos"
- Avis clients (G2, Trustpilot)
- Leurs reseaux sociaux

---

## Fichier 5 : competitors-seo.md

### Ce que c'est
L'analyse detaillee de la strategie SEO de chaque concurrent : quels keywords ils ciblent, quels formats d'articles fonctionnent, quels sont leurs tops pages.

### Comment le remplir

**Avec Ahrefs :**
```
Analyse la strategie SEO de mes concurrents avec Ahrefs :
- [concurrent1.com]
- [concurrent2.com]
- [concurrent3.com]

Pour chacun, donne-moi :
- Domain Rating et nombre de referring domains
- Top 10 pages par trafic organique
- Keywords principaux et positions
- Types de contenu qui performent (comparatifs, guides, listicles...)
- Gaps : keywords qu'ils couvrent et pas nous
```

**Sans Ahrefs :**
```
Va sur les blogs de mes concurrents et analyse manuellement :
- [URLs des blogs]

Pour chacun :
- Combien d'articles ? A quelle frequence publient-ils ?
- Quels types d'articles (comparatifs, guides, tutos, definitions...) ?
- Quels sujets couvrent-ils ?
- Quels articles semblent les plus populaires (partages, commentaires) ?
- Quels sujets ils ne couvrent PAS (gaps) ?
```

---

## Fichier 6 : channels-seo.md

### Ce que c'est
L'inventaire complet de votre contenu SEO existant : articles de blog, pages qui rankent, URLs.

### Comment le remplir

**Avec GSC :**
```
Recupere mes donnees Google Search Console et liste :
- Toutes les pages qui recoivent du trafic organique
- Les keywords associes a chaque page
- Les positions moyennes
- Les pages a fort potentiel (impressions elevees, position 5-20)
```

**Sans GSC :**
```
Voici la liste de mes articles de blog existants :
[coller les URLs ou titres]

Cree un inventaire dans le template channels-seo.md avec :
- URL, titre, sujet principal
- Date de publication
- Statut (a jour / a rafraichir / obsolete)
```

---

## Fichier 7 : products.md

### Ce que c'est
Le catalogue detaille de vos produits ou services — tout ce que l'agent doit savoir pour faire le lien entre un keyword et un produit.

### Comment le remplir

```
Pour chaque produit/service, donne-moi :
- Nom exact
- Prix
- Description en 2-3 phrases
- Public cible
- Probleme qu'il resout
- URL de la page produit/LP
- Duree (si formation/service)
- Differenciateur principal
- Programme detaille / features (si applicable)
```

> **Crucial pour le SEO :** Le programme detaille de chaque produit est une mine de keywords. Chaque outil mentionne, chaque concept enseigne, chaque competence = un article potentiel. L'agent extraira systematiquement ces themes pour construire le backlog.

---

## Checklist de demarrage

- [ ] `product-marketing-context.md` rempli
- [ ] `icp-bible.md` rempli (minimum : 3 pain points avec verbatims)
- [ ] `voice-tone.md` rempli (minimum : tutoiement/vouvoiement + style)
- [ ] `competitors.md` rempli (minimum : 3 concurrents)
- [ ] `competitors-seo.md` rempli (au moins une analyse manuelle)
- [ ] `channels-seo.md` rempli (inventaire blog existant)
- [ ] `products.md` rempli (catalogue complet avec prix)
- [ ] MCP Ahrefs connecte (ou donnees keywords preparees manuellement)
- [ ] Decision prise : articles en .md local ou sur Notion ?

### Demarrage minimum viable (si vous etes presse)

Les 3 fichiers **indispensables** pour que l'agent produise quelque chose d'utile :

1. `product-marketing-context.md` — sans ca, l'agent ne sait pas quoi vendre
2. `products.md` — sans ca, pas de lien keyword → produit
3. `icp-bible.md` — sans ca, les articles sont generiques

Tout le reste ameliore la qualite mais n'est pas bloquant.

---

## Apres l'onboarding

Une fois les fichiers remplis, lancez :

```
Construis ma strategie SEO complete pour le prochain trimestre.
Lis tous les fichiers dans agents/ puis deroule les 7 phases.
```

L'agent va :
1. Synthetiser votre contexte
2. Rechercher les keywords (avec Ahrefs ou vos donnees)
3. Analyser vos concurrents
4. Scorer et prioriser 30-60 articles
5. Creer un calendrier editorial
6. Produire les briefs detailles
7. Rediger les articles sur demande

Chaque phase est presentee pour validation avant de passer a la suivante.
