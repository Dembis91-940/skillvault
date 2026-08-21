# Installer et piloter vos skills métier — le guide SkillVault

## Bienvenue dans SkillVault

Vous venez d'acquérir des compétences métier en français, prêtes à l'emploi, pour votre agent d'intelligence artificielle. Ce guide a un objectif unique : faire en sorte que ces compétences travaillent pour vous dès aujourd'hui, sans connaissances techniques, sans lecture de documentation obscure, sans perte de temps.

SkillVault est une banque française de compétences métier au format `SKILL.md` : cinquante savoir-faire concrets — commerce, artisanat, ressources humaines, comptabilité, marketing — rédigés en français, calibrés pour les réalités des petites entreprises, et prêts à être installés dans un agent d'intelligence artificielle compatible (Claude Code, Codex, Copilot, et d'autres).

Un skill, c'est simple : un dossier qui contient un fichier `SKILL.md`. Ce fichier explique à l'agent comment réaliser une tâche précise de votre métier, étape par étape, avec un exemple concret et une checklist de validation. Vous n'écrivez plus rien vous-même : vous demandez, l'agent exécute selon les règles du skill.

### La promesse de ce guide

Voici ce que vous saurez faire à la fin de votre lecture, et ce que vous pouvez vérifier vous-même :

- Installer un skill dans votre agent en **2 minutes** chrono, une fois votre agent configuré ;
- Décrire une tâche à l'agent de manière efficace, pour obtenir un résultat utilisable du premier coup ;
- Valider le résultat de l'agent avec la checklist incluse dans chaque skill ;
- Créer vos propres skills, pour automatiser les tâches que personne d'autre ne connaît mieux que vous ;
- Identifier, dès la fin de la semaine, **5 tâches récurrentes** que vous déléguez à l'agent au lieu de les faire vous-même.

Ce n'est pas une promesse de marketing : c'est un plan de travail. Chaque chapitre vous donne une méthode et des exemples à reproduire. Si vous suivez le guide, vous arrivez au résultat.

### À qui s'adresse ce guide

Ce guide est écrit pour vous si vous êtes :

- **Commerçant ou e-commerçant** : vous gérez une boutique physique ou en ligne, des avis clients, des paniers abandonnés, des fiches produits ;
- **Artisan** : plombier, électricien, menuisier, peintre, maçon, ou tout métier de chantier — vous chiffrez des devis, organisez des rendez-vous, suivez vos chantiers ;
- **Responsable RH ou dirigeant de TPE** : vous recrutez, intégrez, évaluez, formez, gérez les congés et parfois les conflits ;
- **Indépendant, freelance ou micro-entrepreneur** : vous gérez votre comptabilité, votre trésorerie, vos relances et votre communication ;
- **Petite entreprise (TPE/PME)** : vous voulez donner à votre équipe des méthodes solides sans embaucher de spécialiste.

Une précision importante : ce guide n'est **pas** écrit pour les développeurs. Vous n'avez pas besoin de savoir programmer, ni de comprendre comment fonctionne un modèle de langage en profondeur. Vous avez besoin de savoir copier un dossier d'un endroit à un autre — c'est le niveau technique requis. Si vous savez déplacer des fichiers sur votre ordinateur, vous savez installer un skill.

### Ce qu'il vous faut pour commencer

Avant de lire la suite, assurez-vous d'avoir :

1. **Un ordinateur** (Windows, macOS ou Linux) — la plupart des agents s'installent aussi sur mobile, mais l'installation des skills se fait plus simplement sur ordinateur ;
2. **Un agent IA compatible** — Claude Code, Codex de OpenAI, GitHub Copilot, ou un autre agent listé au chapitre 2. Certains sont gratuits, d'autres payants : une version gratuite ou d'essai suffit pour suivre tout ce guide ;
3. **Vos packs SkillVault** — les fichiers ZIP reçus par email, décompressés sur votre ordinateur ;
4. **Dix minutes de calme** pour la première installation — ensuite, chaque skill supplémentaire se dépose en deux minutes.

Vous n'avez besoin de rien d'autre. Pas de serveur, pas de base de données, pas de compte développeur, pas de carte bancaire pour autre chose que votre abonnement éventuel à l'agent.

### Comment lire ce guide

Le guide suit un ordre logique : comprendre (chapitre 1), installer (chapitre 2), utiliser (chapitres 3 et 4), créer (chapitre 5), aller plus loin (chapitre 6), et retrouver l'essentiel (annexes). Vous pouvez le lire de bout en bout, ou sauter directement au chapitre qui vous concerne : si vous voulez commencer tout de suite, lisez le chapitre 2 et installez votre premier skill, puis revenez au chapitre 1 pour comprendre ce que vous venez d'installer.

---

# Chapitre 1 — Le format Skill : ce que vous installez vraiment

Avant de copier le premier dossier, prenons cinq minutes pour comprendre ce que vous installez. Cette compréhension vous évitera les trois erreurs les plus fréquentes des débutants : demander n'importe quoi à l'agent, accepter n'importe quelle réponse, et conclure que « l'IA ne sert à rien ».

## 1.1 Qu'est-ce qu'un fichier SKILL.md ?

`SKILL.md` est le nom d'un fichier. L'extension `.md` signifie Markdown, un format de texte simple qui permet de structurer un document avec des titres, des listes et des tableaux — exactement comme ce guide. Le nom du fichier est toujours `SKILL.md`, en majuscules, et il est placé dans un dossier qui porte le nom du skill.

Prenons un exemple réel de votre pack Commerce. Le dossier `relance-panier/` contient un fichier `SKILL.md`. Ce fichier décrit, pour l'agent d'intelligence artificielle :

- **Ce que fait le skill** : rédiger la séquence de trois relances pour un panier abandonné ;
- **Quand l'utiliser** : quand un client quitte la boutique avec des articles dans son panier ;
- **Comment procéder** : les étapes précises, dans l'ordre, avec les pièges à éviter ;
- **Un exemple concret** : un cas réel rédigé de A à Z, avec les trois messages ;
- **Une checklist de validation** : la liste des points à vérifier avant d'envoyer le résultat.

En d'autres termes, un skill est un **mode d'emploi structuré** que l'agent lit avant de travailler. Quand vous lui demandez « rédige la relance de panier pour Claire qui a laissé la cafetière », l'agent ouvre le skill `relance-panier`, en suit les instructions, et vous produit une séquence conforme à votre métier — pas une réponse générique de robot.

## 1.2 Un prompt et un skill : quelle différence ?

C'est la question la plus importante de ce chapitre, parce que la réponse change tout votre usage de l'IA.

**Un prompt est une demande jetable.** Vous tapez « écris-moi un email pour relancer un client qui a abandonné son panier » dans la boîte de dialogue. L'agent répond du mieux qu'il peut avec ce qu'il sait — c'est-à-dire avec des généralités. Le résultat est inégal : parfois bon, souvent plat, jamais ancré dans les réalités de votre métier. Et si vous refaites la même demande demain, vous repartez de zéro, avec un résultat différent. Le prompt ne laisse aucune trace, n'apprend rien, ne s'améliore pas.

**Un skill est une compétence structurée et réutilisable.** C'est un document permanent, installé dans l'agent, qui contient le savoir-faire complet d'une tâche : les étapes, les pièges, l'exemple, la checklist. Chaque fois que vous demandez cette tâche, l'agent applique la même méthode, avec la même qualité. Le skill ne dépend pas de votre humeur du jour ni de la formulation de votre demande : il encadre la réponse.

La comparaison parlante : le prompt, c'est demander à un stagiaire de faire un devis « comme il sent » ; le skill, c'est lui donner le classeur de l'entreprise avec la méthode, les exemples des bons devis et la liste de contrôle. Même stagiaire, résultats incomparables.

Concrètement, voici ce qui change avec un skill installé :

| Situation | Sans skill (prompt seul) | Avec le skill installé |
|---|---|---|
| Demande : « relance le panier de Claire » | L'agent invente un email générique, sans citer le produit, sans angle de relance | L'agent applique la séquence : rappel à J+1, preuve sociale à J+2, incitation à J+3, avec le produit cité et un lien de désinscription |
| Qualité du résultat | Aléatoire, dépend de la formulation | Stable, conforme à la méthode du skill |
| Ce que vous gardez | Rien — il faut tout réécrire | La méthode, réutilisable à chaque panier abandonné |
| Risque d'erreur métier | Élevé (promesses fausses, oubli des mentions légales) | Faible (la checklist du skill couvre les pièges) |

Autre différence essentielle : le prompt vit dans la conversation, le skill vit dans un dossier. Vous pouvez donc **partager** un skill avec un collègue, **le mettre à jour** quand votre méthode évolue, et **le conserver** quand vous changez d'agent IA. Votre savoir-faire ne s'évapore pas avec l'historique de discussion.

## 1.3 L'anatomie d'un skill : les cinq parties

Chaque skill SkillVault suit la même structure. C'est une force : une fois que vous avez compris un skill, vous les comprenez tous. Voici les cinq parties, dans l'ordre, avec des extraits réels.

### Le frontmatter : la carte d'identité

Le fichier commence par un bloc encadré de deux lignes de tirets `---`. C'est le frontmatter : des informations structurées que l'agent lit pour savoir de quoi parle le skill. Deux champs, toujours les mêmes :

```yaml
---
name: relance-panier
description: Rédiger la séquence de 3 relances pour un panier abandonné, avec un angle différent à chaque message (rappel, preuve sociale, incitation).
---
```

- `name` : le nom technique du skill, en minuscules et sans accents — c'est l'identifiant que l'agent utilise ;
- `description` : une phrase qui résume la compétence. C'est elle qui permet à l'agent de choisir le bon skill quand vous faites une demande. Une bonne description répond à la question « à quoi ça sert ? » en une phrase actionnable.

### Objectif

La première section explique le but du skill en deux ou trois phrases. Elle répond à la question : quel problème ce skill résout-il, et à quoi ressemble un résultat réussi ? Par exemple, pour `relance-panier` : « Récupérer une vente perdue en relançant un client qui a ajouté des produits au panier sans finaliser sa commande. »

Cette section vous est destinée à vous aussi : elle vous permet de vérifier en trente secondes que le skill correspond bien à ce que vous voulez faire.

### Quand utiliser ce skill

Une liste de situations concrètes où le skill s'applique. Cette section fait deux choses : elle aide l'agent à décider si le skill est pertinent pour votre demande, et elle vous aide à choisir le bon skill dans votre collection. Pour `devis-chiffre`, par exemple : « Un prospect vous demande un devis (plomberie, électricité, menuiserie, peinture, maçonnerie, rénovation) » ou « Vous voulez standardiser votre méthode de chiffrage ».

Si votre situation ne figure pas dans cette liste, c'est que le skill n'est pas le bon outil — ou que la situation mérite d'être reformulée.

### Instructions pas à pas

Le cœur du skill. Les étapes numérotées, dans l'ordre, avec pour chacune le détail qui fait la différence. Ces instructions ne sont pas des généralités : elles contiennent les règles métier réelles, les seuils, les pièges. Dans `devis-chiffre`, on trouve par exemple : « Estimez le temps de pose honnêtement : prenez votre temps réel constaté + 15 à 20 % de marge de sécurité » ou « marge brute saine = 25 à 40 % selon le métier ». Dans `relance-panier` : « Terminez chaque message par une phrase d'humain et un lien de désinscription visible — obligatoire en France (RGPD, L.34-5 du Code des postes) ».

C'est cette section qui transforme l'agent en collaborateur métier : il ne vous donne pas « un » email, il vous donne l'email conforme à votre façon de travailler et aux obligations légales de votre métier.

### Exemple concret

Un cas complet, rédigé, chiffré, avec de vrais noms et de vrais prix. Pour `devis-chiffre` : le remplacement d'un ballon d'eau chaude 200 L, poste par poste, jusqu'au total TTC et aux conditions de paiement. Pour `relance-panier` : les trois messages de relance rédigés de bout en bout pour « Claire » et sa cafetière « SteelBrew ».

L'exemple sert de modèle de qualité : c'est le niveau que l'agent doit atteindre, et c'est le niveau que vous devez exiger. Si le résultat de l'agent est nettement en dessous de l'exemple, quelque chose n'a pas fonctionné (nous verrons au chapitre 4 comment corriger).

### Checklist de validation

La dernière section est une liste de cases à cocher : les points de contrôle avant de considérer le résultat comme valide. Par exemple :

```markdown
## Checklist de validation
- [ ] Chaque produit abandonné est cité avec son prix exact.
- [ ] Les 3 relances ont des angles différents (rappel / preuve sociale / incitation).
- [ ] Aucune promesse fausse : l'offre de la relance 3 est réellement applicable.
- [ ] Lien de désinscription présent dans chaque email.
- [ ] Ton cohérent avec la marque (tutoiement ou vouvoiement uniforme).
- [ ] Orthographe vérifiée (relire les accents et la ponctuation française).
```

La checklist est votre outil de contrôle qualité. Vous ne validez pas une sortie parce qu'elle « a l'air bien » : vous la validez parce qu'elle coche les cases. C'est ce qui fait la différence entre déléguer une tâche et la sous-traiter correctement.

## 1.4 Un skill dans son ensemble : l'exemple réel

Voici un skill complet, tel qu'il est livré dans votre pack Artisanat. Lisez-le en entier : c'est votre première rencontre avec un document de travail que vous utiliserez tous les jours.

```markdown
---
name: devis-chiffre
description: Chiffrer un devis artisanal complet : analyse de la demande, postes détaillés, temps de pose réaliste, marge saine et mentions obligatoires.
---

# Chiffrage d'un devis artisanal

## Objectif
Produire un devis professionnel, détaillé et rentable : chaque poste (matériaux, main-d'œuvre, déplacements, imprévus) est chiffré séparément, le total inclut une marge saine, et les mentions légales obligatoires sont présentes.

## Quand utiliser ce skill
- Un prospect vous demande un devis (plomberie, électricité, menuiserie, peinture, maçonnerie, rénovation).
- Vous voulez standardiser votre méthode de chiffrage.

## Instructions pas à pas
1. **Recueillez l'information complète** : surface, état des lieux, accès, photos, plan, matériaux souhaités, délai souhaité.
2. **Listez les postes** : matériaux, main-d'œuvre, déplacements, évacuation, location, sous-traitance.
3. **Estimez le temps de pose honnêtement** : temps réel constaté + 15 à 20 % de sécurité.
4. **Ajoutez la marge** : 25 à 40 % selon le métier, affichée clairement.
5. **Prévoyez les imprévus** : ligne « imprévus (10 %) » ou clause de révision.
6. **Rédigez le devis avec les mentions obligatoires** : identification, validité 30 jours, délai, TVA, conditions de paiement, décennale, signature.
7. **Relisez** : additionnez les postes, vérifiez TVA et orthographe.

## Exemple concret
Remplacement d'un ballon d'eau chaude 200 L : ballon 549 €, accessoires 38 €, main-d'œuvre 4 h × 55 € = 220 €, évacuation 25 €, déplacement 30 €, imprévus 10 % = 86 €. Total HT : 948 €, TVA 10 % : 94,80 €, Total TTC : 1 042,80 €.

## Checklist de validation
- [ ] Chaque poste est chiffré séparément.
- [ ] Temps de pose réaliste (+15-20 % de sécurité).
- [ ] Marge saine intégrée (25-40 %).
- [ ] Ligne imprévus ou clause de révision présente.
- [ ] Mentions obligatoires complètes.
- [ ] Addition et TVA recalculées, orthographe relue.
```

Remarquez ce qui ne figure pas dans ce fichier : aucun jargon technique, aucune instruction de programmation, aucune référence à un outil précis. Le skill est **neutre vis-à-vis de l'agent** : il fonctionne dans Claude Code, Codex, Copilot ou tout autre agent compatible, parce qu'il décrit une compétence métier, pas une manipulation technique.

## 1.5 Pourquoi ce format est devenu un standard

Vous pourriez vous demander : pourquoi ce format plutôt qu'un autre ? Pourquoi SkillVault a-t-il choisi `SKILL.md` ? La réponse tient en une phrase : parce que les plus grands acteurs de l'intelligence artificielle l'ont adopté en même temps.

Le format des skills — un dossier contenant un fichier Markdown structuré avec un frontmatter de description et des instructions — a été popularisé par Anthropic pour son agent Claude Code. Le principe : donner à l'agent une bibliothèque de compétences persistantes, qu'il consulte au moment où il en a besoin, plutôt que de tout lui expliquer à chaque conversation. OpenAI a suivi avec un format équivalent pour Codex, et GitHub a intégré le concept dans Copilot. Aujourd'hui, la grande majorité des agents d'intelligence artificielle acceptent des skills au format Markdown, avec des variantes mineures de dossier de stockage — c'est exactement ce que vous verrez au chapitre 2.

Ce standard partagé est une excellente nouvelle pour vous :

- **Vos skills survivent aux changements d'outil.** Vous achetez vos skills une fois, et vous les installez dans n'importe quel agent compatible, aujourd'hui comme demain. Vous n'êtes pas prisonnier d'un logiciel ;
- **Le format est lisible par un humain.** Un fichier Markdown s'ouvre dans n'importe quel éditeur de texte. Vous pouvez relire, modifier, corriger un skill sans outil spécialisé ;
- **L'écosystème grossit.** Chaque mois, de nouveaux agents et de nouveaux outils acceptent les skills. Votre bibliothèque SkillVault prend de la valeur avec le temps, sans effort de votre part.

Une mise en garde honnête : les agents évoluent, et les dossiers de skills peuvent changer de nom ou d'emplacement selon les versions. C'est le sujet du chapitre 2 — et c'est pourquoi ce guide vous explique comment trouver le bon dossier plutôt que de vous donner un chemin unique gravé dans le marbre.

## 1.6 Ce qu'un skill ne fait pas

Autant être clair tout de suite : un skill n'est pas magique, et il ne remplace pas votre cerveau. Voici ce qu'un skill ne fait pas :

- **Il ne fait rien tout seul.** Un skill est un document d'instructions. Il ne s'exécute pas, ne se déclenche pas, ne surveille rien. C'est vous qui demandez à l'agent d'utiliser le skill, ou qui l'utilisez dans une automatisation ;
- **Il ne connaît pas votre entreprise.** Le skill connaît votre métier, pas vos chiffres. C'est vous qui fournissez le contexte : le produit, le client, le montant, la situation. Le chapitre 4 vous apprend à le faire correctement ;
- **Il ne garantit pas le résultat.** Même avec le meilleur skill, l'agent peut faire des erreurs — oublier une donnée que vous lui avez donnée, mal interpréter une consigne, produire un texte imparfait. C'est pour cela que chaque skill se termine par une checklist de validation : votre relecture fait partie du processus ;
- **Il ne remplace pas votre jugement.** Un skill peut chiffrer un devis, mais c'est vous qui décidez d'accepter le chantier, de baisser la marge, de refuser le client. L'agent propose, vous disposez.

Gardez ces limites en tête : elles ne diminuent pas l'intérêt des skills, elles définissent la bonne façon de les utiliser — comme collaborateur, pas comme remplaçant.

## 1.7 Ce que vous devez retenir de ce chapitre

- Un skill est un dossier contenant un fichier `SKILL.md` : un mode d'emploi structuré que l'agent suit pour produire un résultat métier ;
- Un prompt est jetable ; un skill est une compétence permanente, réutilisable et partageable ;
- Un skill SkillVault a cinq parties : frontmatter, objectif, situations d'usage, instructions pas à pas, exemple concret et checklist de validation ;
- Le format est devenu un standard de l'industrie (Anthropic, OpenAI, GitHub) : vos skills fonctionnent dans plusieurs agents et vous suivent dans le temps ;
- Un skill ne fait rien tout seul : il a besoin de vous pour le contexte, la demande et la validation finale.


---

# Chapitre 2 — Installer vos skills : le guide pas à pas

C'est le chapitre pratique. À la fin, votre premier skill sera installé et votre agent le reconnaîtra. Nous commençons par la méthode générique, valable partout, puis nous détaillons chaque agent populaire.

## 2.1 Préparer vos fichiers : décompresser le ZIP

Tout commence par les fichiers que vous avez reçus par email. Chaque pack est livré sous forme d'archive ZIP. Voici comment la préparer, quel que soit votre système.

### Sur Windows

1. Localisez le fichier ZIP dans votre dossier Téléchargements (ou là où votre email l'a enregistré) ;
2. Faites un clic droit sur le fichier ;
3. Choisissez **Extraire tout** ;
4. Indiquez le dossier de destination, par exemple `C:\MesSkills\Commerce`, puis cliquez sur **Extraire**.

Vous obtenez un dossier `commerce` (ou `artisanat`, `rh`, `compta`, `marketing`) contenant dix sous-dossiers, un par skill.

### Sur macOS

1. Localisez le fichier ZIP dans Téléchargements ;
2. Double-cliquez dessus : macOS crée automatiquement un dossier du même nom, à côté du ZIP ;
3. Vous obtenez un dossier contenant les dix sous-dossiers de skills.

### Sur Linux

1. Ouvrez un terminal dans le dossier où se trouve le ZIP ;
2. Tapez la commande suivante :

```bash
unzip commerce.zip -d ~/MesSkills/commerce
```

Vous obtenez le dossier `~/MesSkills/commerce` avec ses dix skills.

### Vérifiez ce que vous avez

Quel que soit le système, vous devez obtenir une structure de ce type :

```
commerce/
├── argumentaire-vente/
│   └── SKILL.md
├── email-bienvenue/
│   └── SKILL.md
├── fiche-client/
│   └── SKILL.md
├── fiche-produit/
│   └── SKILL.md
├── promo-email/
│   └── SKILL.md
├── relance-commande/
│   └── SKILL.md
├── relance-panier/
│   └── SKILL.md
├── reponse-avis-google/
│   └── SKILL.md
├── reponse-reclamation/
│   └── SKILL.md
└── upsell-croise/
    └── SKILL.md
```

Chaque sous-dossier contient exactement un fichier `SKILL.md`. Si vous voyez autre chose (fichiers en double, dossiers imbriqués supplémentaires), c'est que l'extraction a créé un niveau de dossier en trop : remontez d'un niveau jusqu'à obtenir exactement la structure ci-dessus.

Un conseil : gardez les ZIP d'origine dans un dossier que vous ne touchez plus. Ils vous servent de sauvegarde, et ils vous permettront de réinstaller rapidement si vous changez d'ordinateur ou d'agent.

## 2.2 Le principe universel : copier le dossier dans le dossier de skills de l'agent

Tous les agents compatibles fonctionnent sur le même principe, avec des variantes d'emplacement :

- L'agent possède un **dossier de skills** : un répertoire sur votre ordinateur, dans votre espace utilisateur ou dans votre projet, où il cherche les compétences disponibles ;
- **Installer un skill = copier le dossier du skill dans ce dossier de skills** ;
- L'agent détecte le nouveau skill au démarrage (ou au rechargement) et le rend disponible pour vos demandes.

C'est tout. Il n'y a pas d'installation logicielle, pas de compilation, pas de configuration à écrire. Si vous savez copier un dossier, vous savez installer un skill.

La seule question qui varie d'un agent à l'autre est : **où se trouve le dossier de skills ?** Les sections suivantes répondent pour chaque agent populaire. Pour un agent non listé, la sous-section 2.6 vous donne la méthode pour trouver le bon endroit par vous-même.

## 2.3 Installer dans Claude Code (Anthropic)

Claude Code est l'agent d'Anthropic, utilisable en ligne de commande ou en interface. Deux situations se présentent selon votre version.

### Version récente : la commande d'installation

Les versions récentes de Claude Code proposent une commande intégrée. Dans le terminal (ou dans l'interface de Claude Code), tapez :

```bash
claude skill install /chemin/vers/le/skill
```

Par exemple, pour installer le skill de relance de panier depuis votre dossier de téléchargement :

```bash
claude skill install ~/Téléchargements/commerce/relance-panier
```

La commande copie le dossier au bon endroit et vous confirme que le skill est disponible. Si votre version affiche une erreur « commande inconnue », utilisez la méthode manuelle ci-dessous.

### Méthode manuelle : le dossier .claude/skills

Selon la version de Claude Code, le dossier de skills se trouve à l'un de ces deux emplacements :

1. **Au niveau de votre espace utilisateur** (les skills sont disponibles partout) : `~/.claude/skills/` ;
2. **Au niveau de votre projet** (les skills sont disponibles uniquement dans ce projet) : dans le dossier de votre projet, un sous-dossier `.claude/skills/`.

La méthode de l'espace utilisateur est recommandée pour vos packs métier : vos skills vous suivent dans tous vos projets, ce qui correspond à votre usage — un artisan ne veut pas réinstaller ses skills à chaque nouveau dossier de chantier.

Sur **macOS et Linux**, créez le dossier s'il n'existe pas, puis copiez :

```bash
mkdir -p ~/.claude/skills
cp -r ~/MesSkills/commerce/relance-panier ~/.claude/skills/
```

Sur **Windows** (PowerShell) :

```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.claude\skills"
Copy-Item -Recurse "$HOME\MesSkills\commerce\relance-panier" "$HOME\.claude\skills\"
```

Vous pouvez aussi le faire en glisser-déposer dans l'explorateur de fichiers : ouvrez le dossier `C:\Users\VotreNom\.claude\skills` (l'affichage des fichiers cachés doit être activé) et déposez-y le dossier du skill.

### Vérifier l'installation dans Claude Code

Redémarrez Claude Code, puis tapez dans la conversation :

```
Quels skills sont disponibles ? Utilise le skill relance-panier si je te demande une relance.
```

Si le skill est bien installé, l'agent le reconnaît et le mentionne. Vous pouvez aussi vérifier que le dossier contient bien le fichier :

```bash
ls ~/.claude/skills/relance-panier/
```

Le résultat doit afficher `SKILL.md`.

## 2.4 Installer dans OpenAI Codex

Codex est l'agent de développement d'OpenAI, disponible en ligne de commande et en interface. Comme Claude Code, il accepte les skills au format `SKILL.md`, avec un dossier de skills dédié.

### Localiser le dossier de skills

Selon la version, le dossier de skills de Codex se trouve à l'un de ces emplacements :

- `~/.codex/skills/` — emplacement utilisateur classique ;
- `~/.codex/skillsets/` — sur certaines versions, les skills sont organisés en « ensembles de compétences » ;
- Au niveau du projet : un dossier `.codex/skills/` dans votre répertoire de travail.

Le plus fiable : demandez directement à Codex où se trouve son dossier de skills. Ouvrez Codex et tapez :

```
Quel est le chemin exact de ton dossier de skills sur cet ordinateur ? Donne-moi le chemin absolu.
```

L'agent vous répond avec le chemin exact — la méthode fonctionne pour Codex comme pour n'importe quel agent, et vous pouvez l'utiliser systématiquement en cas de doute.

### Copier les skills

Une fois le chemin connu, créez le dossier si nécessaire et copiez les skills, sur macOS ou Linux :

```bash
mkdir -p ~/.codex/skills
cp -r ~/MesSkills/commerce/* ~/.codex/skills/
```

Sur Windows (PowerShell) :

```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.codex\skills"
Copy-Item -Recurse "$HOME\MesSkills\commerce\*" "$HOME\.codex\skills\"
```

### Vérifier dans Codex

Relancez Codex et testez avec une demande simple :

```
Utilise le skill relance-panier pour rédiger la relance d'un panier contenant une cafetière à 89 €.
```

Si l'agent applique la structure du skill (trois messages, angles différents, désinscription), l'installation est réussie.

## 2.5 Installer dans GitHub Copilot (et Copilot Chat)

Copilot est l'assistant de GitHub, intégré aux éditeurs de code (Visual Studio Code, JetBrains) et disponible en chat. Copilot accepte les skills au format Markdown, avec un emplacement spécifique.

### Le dossier .github/skills

Pour Copilot, les skills se placent dans le dossier `.github/skills/` **à la racine de votre projet**. Chaque skill est un sous-dossier contenant son `SKILL.md` :

```
.votre-projet/
└── .github/
    └── skills/
        ├── relance-panier/
        │   └── SKILL.md
        └── fiche-produit/
            └── SKILL.md
```

La création du dossier se fait simplement dans l'explorateur de fichiers de votre éditeur : créez le dossier `.github`, puis `skills`, puis copiez-y les dossiers de vos skills.

Si vous utilisez la ligne de commande, depuis la racine de votre projet :

```bash
mkdir -p .github/skills
cp -r ~/MesSkills/commerce/* .github/skills/
```

### Une particularité : le fichier SKILL.md à la racine

Pour les versions récentes de Copilot, le fichier `SKILL.md` peut être placé directement à la racine du dossier `.github/skills/` sans sous-dossier par skill, avec le nom du skill en en-tête du fichier. Les deux formats sont acceptés selon la version ; le format « un sous-dossier par skill » (celui des packs SkillVault) reste le plus compatible.

### Vérifier dans Copilot Chat

Ouvrez Copilot Chat dans votre éditeur, puis posez une question qui mobilise le skill :

```
Dans le skill relance-panier, quelle est la structure recommandée pour la deuxième relance ?
```

Si Copilot vous répond en citant la preuve sociale et les règles du skill, l'installation fonctionne. Sinon, vérifiez que le dossier `.github/skills` est bien à la racine du projet ouvert dans l'éditeur, et non dans un sous-dossier.

## 2.6 Installer dans d'autres agents : ChatGPT, Gemini, Cursor, Hermes et les autres

Le format `SKILL.md` se diffuse rapidement, et la liste des agents compatibles grandit chaque mois. Voici comment procéder pour les principaux, et surtout la méthode universelle pour ceux qui ne sont pas listés ici.

### La méthode universelle en trois questions

Quel que soit l'agent, la démarche est la même. Posez ces trois questions à votre agent — oui, à lui, directement :

1. « Acceptes-tu des skills au format SKILL.md ? »
2. « Si oui, quel est le chemin exact du dossier de skills sur cet ordinateur ? »
3. « Comment recharges-tu les skills après installation ? »

Les agents compatibles répondent précisément. Les agents non compatibles vous répondent qu'ils ne supportent pas ce format — dans ce cas, le guide du chapitre 5 vous montrera comment créer un skill « de conversation » qui fonctionne tout de même en collant les instructions.

### ChatGPT (versions récentes)

Les versions récentes de ChatGPT (celles avec la fonctionnalité d'agent) acceptent les skills : vous pouvez téléverser le dossier du skill ou son fichier `SKILL.md` directement dans la conversation, et demander à ChatGPT de le mémoriser pour les échanges suivants. La méthode exacte évolue avec les versions ; en cas de doute, utilisez la méthode universelle ci-dessus.

### Gemini (Google)

Gemini propose des « compétences » dans certains environnements professionnels. La compatibilité avec le format `SKILL.md` dépend de la version et de l'offre. La méthode universelle s'applique : demandez à Gemini s'il accepte le format et où déposer les dossiers. Dans les environnements non compatibles, le plan B du chapitre 5 fonctionne très bien.

### Cursor

Cursor accepte les skills au format Markdown dans le dossier `.cursor/skills/` de votre projet. Copiez simplement vos dossiers de skills à cet endroit :

```bash
mkdir -p .cursor/skills
cp -r ~/MesSkills/commerce/* .cursor/skills/
```

Cursor détecte les skills au rechargement du projet.

### Hermes

Hermes, l'agent de Nous Research, gère ses skills dans un dossier de profil dédié, sous `.hermes/skills/` dans votre espace utilisateur (ou dans un profil spécifique). Copiez vos dossiers de skills dans ce répertoire, puis relancez une session : les skills deviennent disponibles pour toutes vos demandes. La méthode universelle confirme le chemin exact sur votre machine.

### Les autres agents

Pour tout autre agent : appliquez la méthode universelle. Les trois questions donnent la réponse en trente secondes, sans recherche sur Internet. Et rappelez-vous le principe du chapitre 1 : les skills au format Markdown sont lisibles par n'importe quel système, ce qui rend la compatibilité de plus en plus fréquente — et le plan B du chapitre 5 couvre les cas restants.

## 2.7 Le plan B : quand l'agent n'a pas de dossier de skills

Certains agents de conversation classiques (l'interface web de ChatGPT, Gemini, ou un assistant sans fonctionnalité de skills) n'ont pas de dossier de skills. Vous n'êtes pas bloqué pour autant : le plan B consiste à **coller le contenu du skill dans la conversation**.

La démarche :

1. Ouvrez le fichier `SKILL.md` du skill voulu dans n'importe quel éditeur de texte (Bloc-notes, TextEdit) ;
2. Sélectionnez tout le contenu et copiez-le ;
3. Dans la conversation avec l'agent, collez le contenu, puis ajoutez votre demande :

```
Voici un skill que tu dois appliquer pour toutes les tâches de ce type.

[contenu du SKILL.md collé ici]

Applique ce skill pour : [votre demande précise]
```

L'agent applique alors les instructions du skill pour cette conversation. La limite : le skill ne persiste pas d'une conversation à l'autre — il faut le recoller à chaque nouvelle session. C'est moins confortable, mais cela reste infiniment meilleur qu'un prompt jetable, et cela vous permet d'utiliser vos packs avec n'importe quel outil.

Astuce pour les utilisateurs réguliers du plan B : conservez vos fichiers `SKILL.md` dans un dossier facile d'accès, et ouvrez-les dans un éditeur avec un seul clic. Coller un skill prend alors trente secondes.

## 2.8 Les erreurs d'installation les plus fréquentes

Voici les quatre erreurs que nous voyons le plus souvent, et comment les éviter :

| Erreur | Symptôme | Correction |
|---|---|---|
| Copier le ZIP au lieu du dossier décompressé | L'agent ne voit aucun skill | Décompressez d'abord le ZIP (section 2.1), puis copiez les dossiers décompressés |
| Copier le dossier parent au lieu des sous-dossiers | L'agent voit « commerce » mais pas les 10 skills | Copiez les dix sous-dossiers de skills, pas le dossier qui les contient |
| Mauvais dossier de destination | L'agent ne trouve rien | Vérifiez le chemin avec la méthode universelle (section 2.6) ou les chemins des sections 2.3 à 2.5 |
| Oublier de relancer l'agent | L'agent ne connaît pas le skill pourtant installé | Redémarrez l'agent (ou rechargez le projet) après installation |

Si vous installez plusieurs packs : copiez simplement tous les dossiers de skills dans le même dossier de skills de l'agent. Les noms de skills sont uniques (aucun doublon entre les packs), il n'y a aucun conflit. Vous pouvez installer les cinquante skills d'un coup.

## 2.9 Mettre à jour, désinstaller et sauvegarder vos skills

Vos skills sont des fichiers ordinaires : ils se mettent à jour, se désinstallent et se sauvegardent aussi simplement qu'ils s'installent.

### Mettre à jour un skill

Deux cas se présentent : vous avez modifié un skill vous-même (chapitre 5), ou vous recevez une version améliorée d'un pack. Dans les deux cas, la mise à jour consiste à remplacer le contenu du dossier du skill :

1. Ouvrez le dossier du skill dans le dossier de skills de votre agent ;
2. Remplacez le fichier `SKILL.md` par la nouvelle version (ou supprimez l'ancien dossier et copiez le nouveau) ;
3. Relancez l'agent : la nouvelle version est prise en compte.

Conseil de rangement : avant de remplacer, copiez l'ancienne version dans un dossier d'archives (`MesSkills/Archives/`). Vous pourrez revenir en arrière en trente secondes si la nouvelle version ne vous convient pas.

### Désinstaller un skill

Désinstaller, c'est l'inverse d'installer : supprimez le dossier du skill du dossier de skills de l'agent. Au prochain rechargement, l'agent ne le proposera plus. Il n'y a ni registre à modifier, ni configuration à nettoyer : la suppression du dossier suffit.

Avant de supprimer, posez-vous la question de la sauvegarde : un skill que vous n'utilisez plus aujourd'hui peut redevenir utile dans six mois. Déplacez-le vers un dossier d'archives plutôt que de le supprimer définitivement.

### Sauvegarder votre bibliothèque

Vos skills sont votre capital : ils contiennent vos méthodes de travail formalisées. Protégez-les comme vos devis ou vos factures.

1. Une fois par mois, copiez vos dossiers de skills vers un disque externe ou un espace de stockage en ligne ;
2. Gardez les ZIP d'origine de vos packs dans un dossier dédié — ils servent de référence ;
3. Si vous changez d'ordinateur, restaurez en recopiant les dossiers : la procédure du chapitre 2, en sens inverse.

| Action | Comment faire | Effet |
|---|---|---|
| Mettre à jour | Remplacer le `SKILL.md` ou le dossier | Nouvelle version active au rechargement |
| Désinstaller | Supprimer le dossier du skill | Le skill disparaît de l'agent |
| Sauvegarder | Copier les dossiers vers un disque externe | Bibliothèque restaurée à tout moment |

## 2.10 Récapitulatif : installer un skill en 2 minutes

Voici la procédure complète, chronométrée :

1. **Décompressez le ZIP** du pack (30 secondes) ;
2. **Localisez le dossier de skills** de votre agent : `~/.claude/skills/`, `~/.codex/skills/`, `.github/skills/`, `.cursor/skills/`, ou demandez à l'agent (30 secondes) ;
3. **Copiez les dossiers de skills** dans le dossier de skills (20 secondes) ;
4. **Relancez l'agent** (30 secondes) ;
5. **Testez** avec une demande simple qui mobilise le skill (30 secondes).

Total : environ 2 minutes pour le premier skill, moins pour les suivants, puisque le dossier de destination est déjà connu. C'est la promesse de SkillVault : deux minutes, chrono en main.

## 2.11 Ce que vous devez retenir de ce chapitre

- Un skill s'installe en copiant son dossier dans le dossier de skills de l'agent — rien d'autre ;
- Le dossier de skills varie selon l'agent : `.claude/skills` pour Claude Code, `.codex/skills` pour Codex, `.github/skills` pour Copilot, `.cursor/skills` pour Cursor, `.hermes/skills` pour Hermes ;
- Quand vous ne connaissez pas le dossier, demandez à l'agent lui-même : il connaît son propre chemin ;
- Les agents sans dossier de skills restent utilisables : collez le contenu du `SKILL.md` dans la conversation ;
- Relancez toujours l'agent après l'installation, et testez avec une demande qui mobilise le skill.


---

# Chapitre 3 — Votre premier skill en action

L'installation est terminée. Il est temps de faire travailler votre premier skill, avec deux exemples réels issus de vos packs : `relance-panier` pour le commerce et `devis-chiffre` pour l'artisanat. Nous allons voir mot à mot comment décrire la tâche, ce que vous devez attendre comme résultat, et comment le valider avec la checklist.

## 3.1 La méthode en trois temps

Toute utilisation d'un skill se déroule en trois temps :

1. **Vous décrivez la situation** : vous donnez à l'agent le contexte, les faits, les chiffres. Pas de formule magique : des faits ;
2. **L'agent applique le skill** : il lit les instructions, les suit, et vous produit le résultat ;
3. **Vous validez avec la checklist** : vous vérifiez le résultat point par point avant de l'utiliser.

Ce chapitre vous montre ces trois temps sur deux cas concrets. Vous pourrez ensuite reproduire la méthode avec n'importe quel skill de vos packs.

## 3.2 Premier cas : relance de panier abandonné (Pack Commerce)

### La situation de départ

Vous gérez une boutique en ligne. Un client nommé Karim a ajouté une lampe de bureau design à 129 € dans son panier il y a deux heures, puis a quitté le site sans payer. Vous voulez lui envoyer une séquence de relances.

### Temps 1 : décrire la tâche à l'agent

Ouvrez votre agent et tapez un message de ce type :

```
Utilise le skill relance-panier.

Contexte : Karim a abandonné un panier il y a 2 heures sur ma boutique.
Produit dans le panier : lampe de bureau « Lumen » à 129 €, livraison offerte dès 100 €.
La boutique tutoie ses clients.
Ma marque : éclairage design, ton chaleureux et honnête, pas de fausses promos.
Je n'ai pas de vrai code promo à offrir : pour la 3e relance, propose seulement de garder le prix et la livraison offerte pendant 48 h.

Rédige la séquence complète des 3 messages, prêts à envoyer dans mon outil d'emailing.
```

Décomposons ce message, parce que chaque phrase a un rôle :

- « Utilise le skill relance-panier » : vous indiquez explicitement le skill. Même si l'agent pourrait le deviner grâce à la description, le nommer supprime toute ambiguïté ;
- « Contexte : ... » : les faits. Qui (Karim), quoi (la Lumen à 129 €), quand (il y a 2 heures) ;
- « livraison offerte dès 100 € » : une contrainte réelle de votre boutique, qui sera utilisée dans les messages ;
- « La boutique tutoie ses clients » : une règle de ton. Sans elle, l'agent hésitera entre tutoiement et vouvoiement ;
- « pas de fausses promos... propose seulement de garder le prix et la livraison offerte pendant 48 h » : la contrainte la plus importante. Le skill interdit les promesses fausses ; vous donnez à l'agent l'incitation réelle à proposer.

### Temps 2 : le résultat attendu

Voici le type de résultat que vous devez obtenir — la structure exacte du skill appliquée à votre cas :

**Message 1 (J+1, rappel bienveillant) :**

> Bonjour Karim, vous avez laissé la lampe Lumen dans votre panier. C'est elle qui diffuse une lumière douce et réglable, parfaite pour un bureau — et elle est en stock, avec livraison offerte dès 100 €. On vous la garde de côté : [Finaliser ma commande].

**Message 2 (J+2, preuve sociale) :**

> 300 lampes testées avant de choisir la Lumen. Sophie R. écrit : « Le rendu est magnifique, je ne travaille plus sans elle ». La question n'est pas de savoir si vous la voulez, mais où vous l'installerez. [Voir mon panier].

**Message 3 (J+3, incitation limitée dans le temps) :**

> Dernière étape : nous gardons la Lumen à 129 € avec livraison offerte jusqu'à dimanche minuit. Ensuite, le panier est libéré. [Je finalise].

Un message d'humain conclut chaque relance : « Une question ? Répondez simplement à cet email », suivi du lien de désinscription.

Ce résultat n'est pas tombé du ciel : il suit point par point les instructions du skill — produits cités avec leur prix exact, trois angles différents, aucune fausse promesse, désinscription présente, tutoiement uniforme.

### Temps 3 : valider avec la checklist

Avant d'envoyer quoi que ce soit, ouvrez la checklist du skill et cochez :

- [x] Chaque produit abandonné est cité avec son prix exact — la Lumen à 129 € figure dans les trois messages ;
- [x] Les 3 relances ont des angles différents : rappel, preuve sociale, incitation ;
- [x] Aucune promesse fausse : la relance 3 promet exactement ce que vous pouvez tenir (prix bloqué 48 h + livraison offerte) ;
- [x] Lien de désinscription présent dans chaque email ;
- [x] Ton cohérent : tutoiement uniforme partout ;
- [x] Orthographe vérifiée : relisez les accents (« déjà », « très », « pourra ») et la ponctuation.

Si une case n'est pas cochée, ne validez pas : corrigez le message avec l'agent, ou à la main. La checklist est votre filet de sécurité — ne la sautez jamais pour gagner deux minutes.

### Variante : le cas sans skill

Pour mesurer la différence, comparez avec ce que donnerait la même demande sans le skill :

```
Écris-moi des relances de panier abandonné pour un client.
```

Le résultat typique : trois emails génériques, sans le nom du produit, avec un angle identique (tous les trois « revenez finir votre achat »), une promesse inventée (« -20 % ») que vous ne pouvez pas tenir, et aucune mention de désinscription. C'est exactement le type de sortie que le skill empêche.

## 3.3 Deuxième cas : chiffrage d'un devis artisanal (Pack Artisanat)

### La situation de départ

Vous êtes plaquiste. Un particulier vous demande de chiffrer la pose de plaques de plâtre dans une pièce de 20 m², avec doublage d'un mur extérieur. Il veut un prix sous 48 heures. Vous avez posé les questions nécessaires : surface 20 m², murs en bon état, accès facile (rez-de-chaussée), matériaux non fournis, pas de peinture.

### Temps 1 : décrire la tâche à l'agent

```
Utilise le skill devis-chiffre.

Travaux : doublage et cloisons en plaques de plâtre dans une pièce de 20 m² (pièce à vivre).
État des lieux : murs sains, accès facile au rez-de-chaussée, électricité déjà en place.
Matériaux : non fournis par le client, à inclure dans le devis.
Prestation : pose seule, pas de peinture, pas d'électricité.
Mes données : je facture ma main-d'œuvre 52 €/heure, mon fournisseur me coûte 6,80 €/m² de plaque fournie avec rails et visserie.
Délai souhaité par le client : démarrage sous 3 semaines.
TVA applicable : 10 %.

Rédige le devis complet avec les postes détaillés, le total TTC et les mentions obligatoires.
```

Là encore, chaque élément a un rôle : les faits (surface, état, accès), vos chiffres réels (52 €/h, 6,80 €/m²), les contraintes (TVA 10 %, délai), et la demande précise (devis complet avec mentions obligatoires).

### Temps 2 : le résultat attendu

Le skill applique sa méthode : recueil de l'information (déjà fait), postes détaillés, temps de pose réaliste, marge, imprévus, mentions légales. Le résultat doit ressembler à ceci :

**Devis — Doublage et cloisons, pièce de 20 m²**

| Poste | Détail | Montant HT |
|---|---|---|
| Matériaux | 58 m² de plaques + rails + visserie à 6,80 €/m² | 394,40 € |
| Main-d'œuvre | 24 h estimées × 52 €/h (pose + finitions) | 1 248,00 € |
| Déplacement | Forfait | 40,00 € |
| Évacuation des chutes | Forfait | 35,00 € |
| Imprévus (10 %) | Sécurité | 171,74 € |
| **Total HT** | | **1 889,14 €** |
| TVA 10 % | | 188,91 € |
| **Total TTC** | | **2 078,05 €** |

**Conditions** : devis valable 30 jours, démarrage sous 3 semaines, acompte de 30 % à la commande, solde à la réception des travaux. **Mentions obligatoires** : votre identification complète, assurance décennale, « bon pour accord » et signature.

Le point crucial : le temps de pose. Le skill impose votre temps réel + 15 à 20 % de sécurité. Vous savez que cette pièce prend 20 heures de pose : 24 h (20 h × 1,2) est l'estimation honnête qui vous protège des dépassements.

### Temps 3 : valider avec la checklist

- [x] Chaque poste est chiffré séparément : matériaux, main-d'œuvre, déplacement, évacuation, imprévus ;
- [x] Temps de pose réaliste : 24 h = temps réel + 20 % de sécurité ;
- [x] Marge saine intégrée : votre taux horaire de 52 €/h inclut vos charges et votre marge ;
- [x] Ligne imprévus (10 %) présente ;
- [x] Mentions obligatoires complètes : identification, validité 30 jours, TVA, délai, acompte, décennale ;
- [x] Addition et TVA recalculées : 1 889,14 × 1,10 = 2 078,05 €. Vérifiez ce calcul vous-même avant envoi — toujours.

### Le réflexe à garder

Dans les deux exemples, la démarche est identique : **donner des faits, exiger la structure du skill, valider avec la checklist**. Ce réflexe — que vous allez maintenant appliquer aux quarante-huit autres skills — est la compétence la plus importante de tout ce guide.

### 3.4 Troisième cas : la fiche de poste (Pack RH)

### La situation de départ

Vous dirigez une boutique de 4 salariés et vous embauchez votre premier commercial. Vous savez ce que vous attendez de lui, mais vous n'avez jamais rédigé de fiche de poste. Le skill `fiche-de-poste` va structurer votre intuition en document professionnel.

### Temps 1 : décrire la tâche à l'agent

```
Utilise le skill fiche-de-poste.

Contexte : je recrute mon premier commercial pour ma boutique d'éclairage design (4 salariés, CA 600 000 €). Il aura pour missions : développer les ventes auprès des architectes d'intérieur, suivre les devis, fidéliser les clients existants. Il travaillera en autonomie, avec un reporting mensuel.
Contraintes : poste à temps plein, basé à Lyon, salaire fourchette 28 000 à 34 000 € brut annuel selon expérience, voiture non fournie, tickets restaurant.
Format : fiche de poste complète avec mission, activités, compétences requises et conditions.
```

### Temps 2 : le résultat attendu

Le skill produit une fiche structurée : intitulé du poste, mission principale en deux phrases, activités détaillées (prospection, devis, suivi, reporting), compétences requises (négociation, organisation, connaissance du secteur de l'éclairage) et conditions (salaire, localisation, avantages). Chaque activité est décrite par un résultat attendu, pas par une liste de tâches vagues.

### Temps 3 : valider avec la checklist

- [x] La mission tient en deux phrases compréhensibles par un candidat ;
- [x] Chaque activité décrit un résultat attendu, pas une simple tâche ;
- [x] Les compétences sont réalistes (pas de « maîtrise parfaite de 8 logiciels ») ;
- [x] Les conditions sont complètes : salaire, lieu, temps de travail, avantages ;
- [x] Le ton est neutre et professionnel, sans formule stéréotypée.

### L'enseignement de ce cas

Ce cas montre deux choses. D'abord, les skills RH transforment une intention floue (« je veux embaucher quelqu'un pour vendre ») en document professionnel exploitable. Ensuite, les skills s'enchaînent : cette fiche de poste servira de base au skill `annonce-emploi` pour rédiger l'annonce, puis à `grille-entretien` pour préparer les questions d'embauche. Un même besoin mobilise plusieurs compétences de la bibliothèque.

## 3.5 Et si le résultat ne ressemble pas à l'exemple ?

Trois cas possibles, trois réponses :

1. **Le résultat est générique** (aucun produit cité, aucune règle métier) : le skill n'a probablement pas été utilisé. Reformulez en nommant explicitement le skill, et vérifiez son installation (chapitre 2) ;
2. **Le résultat suit la structure mais contient une erreur** (mauvais calcul, mauvaise date) : c'est normal et rattrapable. Corrigez l'erreur, puis dites à l'agent « corrige le point suivant » — il s'améliore immédiatement pour la suite ;
3. **Le résultat vous semble incomplet** : relisez le skill et comparez section par section. Si une partie du skill n'a pas été traitée (par exemple la désinscription dans les emails), demandez explicitement : « tu as oublié la partie X du skill, reprends-la ».

Dans tous les cas : ne partez pas du principe que « l'IA a raté » — partez du principe qu'une instruction manque ou a été mal comprise, et précisez-la. C'est la différence entre un utilisateur passif et un pilote efficace. Le chapitre 4 développe cette posture.

## 3.6 Dix demandes types pour votre première semaine

Pour démarrer sans réfléchir, voici dix demandes prêtes à copier. Remplacez les éléments entre [crochets] par vos données, ajoutez vos contraintes, et lancez.

1. **Commerce — relance-panier** : « Utilise le skill relance-panier. Panier abandonné il y a 2 h : [produit] à [prix] €. Je n'ai pas de vrai code promo. Rédige les 3 relances. »
2. **Commerce — fiche-produit** : « Utilise le skill fiche-produit. Produit : [nom], prix [prix], usage [usage], matériaux [matériaux]. Rédige la fiche complète avec titre, description et FAQ. »
3. **Artisanat — devis-chiffre** : « Utilise le skill devis-chiffre. Travaux : [description]. Mon taux horaire : [taux] €/h. TVA [10 ou 20] %. Rédige le devis détaillé avec mentions obligatoires. »
4. **Artisanat — planning-rdv** : « Utilise le skill planning-rdv. Cette semaine : [liste des rendez-vous et lieux]. Construis le planning avec les temps de déplacement. »
5. **RH — fiche-de-poste** : « Utilise le skill fiche-de-poste. Poste : [intitulé], missions [missions], conditions [salaire, lieu]. Rédige la fiche complète. »
6. **RH — message-candidat-refuse** : « Utilise le skill message-candidat-refuse. Candidat : [nom], poste : [intitulé], motif réel : [motif]. Rédige le refus respectueux et personnalisé. »
7. **Comptabilité — relance-impaye** : « Utilise le skill relance-impaye. Facture n° [numéro] de [montant] €, due depuis [jours]. C'est le [1er, 2e, 3e] niveau de relance. Rédige le message. »
8. **Comptabilité — suivi-tresorerie** : « Utilise le skill suivi-tresorerie. Voici mes soldes et mes échéances : [données]. Analyse les tensions à venir et propose un plan. »
9. **Marketing — post-linkedin** : « Utilise le skill post-linkedin. Sujet : [votre expérience ou votre métier]. Public : [cible]. Rédige le post avec accroche et appel à l'engagement. »
10. **Marketing — reponse-avis-negatif** : « Utilise le skill reponse-avis-negatif. Avis reçu : [texte de l'avis]. Ma réponse possible : [ce que vous pouvez faire]. Rédige la réponse publique et la proposition privée. »

Ces dix demandes couvrent les cinq packs : une par pack, deux par pack. Après les avoir testées, vous saurez exactement lesquelles entrent dans votre rituel hebdomadaire.

## 3.7 Ce que vous devez retenir de ce chapitre

- Décrire une tâche = donner les faits (qui, quoi, quand, combien), les contraintes réelles et le résultat attendu ;
- Nommer explicitement le skill dans votre demande supprime toute ambiguïté ;
- Le résultat attendu suit la structure du skill : c'est votre référence de qualité ;
- La checklist du skill est votre outil de validation : cochez chaque case avant d'utiliser le résultat ;
- Un résultat imparfait se corrige en précisant la demande, pas en abandonnant l'outil.

---

# Chapitre 4 — Piloter vos skills au quotidien

Vous savez installer et utiliser un skill. Ce chapitre vous transforme en pilote : choisir le bon skill, décrire efficacement, valider rigoureusement, et éviter les cinq erreurs qui coûtent le plus cher aux débutants.

## 4.1 Choisir le bon skill

Cinquante skills, c'est une bibliothèque. Voici comment trouver le bon en quelques secondes.

### Lire la description (frontmatter)

Chaque skill commence par une phrase de description. C'est votre index. Par exemple : « Gérer une facture impayée en 3 niveaux de relance (courtoise, ferme, mise en demeure) avec les bons délais et les bonnes formules ». Si votre besoin correspond à cette phrase, le skill est le bon.

### Vérifier la section « Quand utiliser ce skill »

Avant d'utiliser un skill pour la première fois, lisez sa section d'usage. Elle liste les situations où le skill s'applique — et par contraste, celles où il ne s'applique pas. Un skill de relance de panier ne sert pas à rédiger une relance de facture impayée : les enjeux, les délais et les formules n'ont rien à voir. Le pack Comptabilité a son propre skill `relance-impaye`, fait pour cela.

### Le tableau de choix rapide

Voici les situations fréquentes et le skill correspondant :

| Votre besoin | Skill à utiliser | Pack |
|---|---|---|
| Un client abandonne son panier | relance-panier | Commerce |
| Un avis négatif sur Google | reponse-avis-google (commerce) ou reponse-avis-negatif (marketing) | Commerce / Marketing |
| Chiffrer un chantier | devis-chiffre | Artisanat |
| Un client ne paie pas sa facture | relance-impaye | Comptabilité |
| Recruter un collaborateur | fiche-de-poste puis annonce-emploi | RH |
| Publier sur LinkedIn | post-linkedin | Marketing |
| Vérifier sa trésorerie du mois | suivi-tresorerie | Comptabilité |
| Un client se plaint d'une commande | reponse-reclamation | Commerce |

Notez que certains besoins ont deux skills possibles : la réponse à un avis négatif existe en version « commerce » (tournée vers la réputation locale) et en version « marketing » (tournée vers la gestion de crise en ligne). Choisissez selon votre activité principale.

### Le doute ?

Si vous hésitez entre deux skills, demandez à l'agent de trancher en décrivant votre situation :

```
J'ai un besoin : [décrivez la situation en 2 phrases]. Parmi mes skills, lequel est le plus adapté, et pourquoi ?
```

L'agent lit les descriptions des skills et vous recommande le bon — c'est une utilisation du skill de sélection qui évite bien des erreurs.

## 4.2 Décrire une tâche efficacement : la méthode des quatre blocs

La qualité de ce que vous obtenez dépend directement de la qualité de ce que vous donnez. La méthode des quatre blocs couvre tout ce dont l'agent a besoin :

**Bloc 1 — Le skill.** « Utilise le skill X. » Une phrase, en ouverture. Elle oriente l'agent vers la bonne méthode.

**Bloc 2 — Le contexte.** Les faits : qui est concerné, quel produit ou service, quel montant, quelle date, quel historique. L'agent n'invente pas ce que vous ne lui dites pas : un contexte pauvre produit un résultat pauvre.

**Bloc 3 — Les contraintes.** Ce qui est interdit ou obligatoire : « pas de fausse promo », « tutoiement », « mentionner la garantie », « ne pas dépasser 2 pages », « délai de réponse sous 24 h ». Les contraintes sont vos règles d'entreprise : plus vous en donnez, plus le résultat vous ressemble.

**Bloc 4 — Le format attendu.** Ce que vous voulez recevoir : « une séquence de 3 emails », « un devis en tableau », « une fiche en 6 sections », « un texte de 150 mots ». Un format précis évite les allers-retours.

Un exemple complet des quatre blocs :

```
Utilise le skill reponse-reclamation. (Bloc 1 : le skill)
Cliente : Mme Moreau, commande n°4582 livrée hier, la lampe arrive avec un socle fissuré. Elle a écrit un message mécontent ce matin. (Bloc 2 : le contexte)
Règle : proposer un échange ou un remboursement sous 48 h, ne jamais contester l'état des lieux du client, garder un ton professionnel et chaleureux. (Bloc 3 : les contraintes)
Donne-moi le message de réponse complet, prêt à envoyer, avec l'objet de l'email. (Bloc 4 : le format)
```

Avec ces quatre blocs, vous obtenez un résultat utilisable au premier essai dans la grande majorité des cas.

### Le réflexe inverse : ne jamais demander sans contexte

« Fais une relance », « Écris une fiche de poste », « Prépare la compta » : ces demandes sans contexte forcent l'agent à deviner — et il devinera mal. Avant de taper, posez-vous trois questions : quels faits l'agent doit-il connaître ? Quelles règles ne doit-il pas enfreindre ? Quel format je veux recevoir ? Trente secondes de réflexion évitent trois allers-retours.

## 4.3 Valider les sorties : la règle des trois lectures

Un résultat validé passe par trois lectures rapides :

1. **Lecture structure** (10 secondes) : le document a-t-il la forme attendue ? Les sections du skill sont-elles traitées ? La checklist du skill est-elle respectée dans le contenu ?
2. **Lecture chiffres et faits** (30 secondes) : les montants, dates, noms, quantités correspondent-ils à ce que vous avez fourni ? Refaites les additions, vérifiez les TVA, contrôlez les dates. C'est la lecture la plus importante : les erreurs de chiffres sont les plus coûteuses ;
3. **Lecture ton et orthographe** (30 secondes) : le texte est-il conforme à votre ton ? L'orthographe et les accents sont-ils corrects ? Un document avec des fautes envoyé à un client vous coûte plus cher que trente secondes de relecture.

Trois lectures, moins de deux minutes, zéro erreur envoyée. C'est le prix de la délégation réussie.

## 4.4 Les cinq erreurs courantes (et comment les éviter)

### Erreur n° 1 : le prompt trop vague

**Le symptôme** : « Fais une relance pour mon client. » L'agent ne sait ni qui est le client, ni ce qui est en jeu, ni ce que vous attendez. Résultat : un texte générique inutilisable.

**Le correctif** : appliquez la méthode des quatre blocs. Une relance, c'est : le skill, le client, la situation, la règle, le format. Cinq informations, trente secondes.

### Erreur n° 2 : oublier de donner le contexte

**Le symptôme** : le skill est bien nommé, mais les faits manquent — pas de produit, pas de montant, pas d'historique. L'agent applique la méthode sur du vide, et le résultat ne mentionne rien de concret.

**Le correctif** : avant d'envoyer la demande, vérifiez que les cinq W sont couverts : qui, quoi, quand, où, combien. Si l'un manque, complétez.

### Erreur n° 3 : accepter une sortie non relue

**Le symptôme** : vous envoyez le texte de l'agent sans le relire. Une coquille, une date erronée, une promesse impossible partent au client. La confiance dans l'outil est légitime ; la confiance aveugle ne l'est pas.

**Le correctif** : la règle des trois lectures (section 4.3). C'est non négociable pour tout document partant vers un client, un salarié ou un fournisseur.

### Erreur n° 4 : promettre des délais irréalistes

**Le symptôme** : le devis dit « livraison sous 48 h » alors que votre fournisseur livre sous 10 jours. L'email dit « réponse sous 24 h » alors que vous partez en congés. L'agent écrit ce que vous ne précisez pas — et il écrira des promesses optimistes.

**Le correctif** : donnez vos délais réels dans le bloc des contraintes. « Délai de livraison réel : 10 jours ouvrés », « je réponds sous 48 h », « démarrage possible début du mois prochain ». L'agent n'invente plus rien.

### Erreur n° 5 : mélanger les métiers

**Le symptôme** : utiliser le skill de relance commerciale pour une relance d'impayé, ou le skill de réponse aux avis pour une réclamation. Les méthodes, les tons et les obligations ne sont pas les mêmes : une relance d'impayé suit un cadre juridique strict, une relance de panier est une démarche commerciale légère.

**Le correctif** : vérifiez la section « Quand utiliser ce skill » avant usage. En cas de doute, laissez l'agent choisir (section 4.1).

### Le tableau des cinq erreurs

| Erreur | Coût typique | Correctif |
|---|---|---|
| Prompt trop vague | Résultat inutilisable, frustration | Méthode des quatre blocs |
| Contexte manquant | Résultat vide de faits | Vérifier qui / quoi / quand / où / combien |
| Sortie non relue | Erreur envoyée au client | Règle des trois lectures |
| Délais irréalistes | Promesse non tenue, crédibilité | Donner vos délais réels |
| Mélange des métiers | Méthode inadaptée, risque légal | Lire « Quand utiliser ce skill » |

### 4.5 Automatiser et mesurer : le quotidien du pilote

### Automatiser : la bonne place des skills dans vos outils

Une question revient souvent : « Est-ce que le skill va automatiser tout seul mes relances de panier ? » Réponse honnête : non, et c'est voulu. Un skill est un document d'instructions ; il ne se connecte pas à votre boutique ni à votre outil d'emailing. En revanche, il joue un rôle précis dans votre automatisation : **il produit le contenu** que vos outils envoient.

Concrètement, pour une automatisation de panier abandonné : votre outil d'emailing (Klaviyo, Brevo, Mailchimp) déclenche l'envoi à J+1, J+2 et J+3. C'est lui qui gère le déclenchement et l'envoi. Le skill, lui, rédige les trois messages conformes à votre méthode et à vos contraintes. Vous placez ensuite ces textes dans votre scénario d'automatisation, une fois — et l'outil s'occupe du reste.

Cette séparation est saine : l'outil automatise l'envoi, le skill garantit la qualité du message. Quand votre offre change, vous régénérez le contenu avec le skill et vous mettez à jour votre scénario : deux minutes, au lieu d'une rédaction complète.

### Mesurer : le petit tableau qui change tout

La délégation ne se pilote pas au ressenti. Tenez un suivi simple, dans un carnet ou un tableur, avec quatre colonnes :

| Semaine | Tâche déléguée | Skill utilisé | Résultat validé (oui/non) |
|---|---|---|---|
| 1 | Relance panier abandonné | relance-panier | Oui |
| 1 | Réponse avis Google | reponse-avis-google | Oui |
| 2 | Devis salle de bain | devis-chiffre | Oui |
| 2 | Point de trésorerie | suivi-tresorerie | Oui |

En fin de semaine, comptez : combien de tâches déléguées, combien de résultats validés, combien de temps estimé gagné. L'objectif de la première semaine : cinq tâches déléguées. La quatrième semaine : dix. Vous verrez le rituel s'installer tout seul — parce que les chiffres le montrent.

### Le coût réel de la délégation

Soyons précis sur l'économie de temps. Chaque tâche déléguée coûte : deux minutes pour la demande (les quatre blocs), deux minutes pour la validation (les trois lectures). Total : environ quatre minutes. Ce qu'elle rapporte : le temps de faire la tâche vous-même — quinze minutes pour une relance soignée, une heure pour un devis complet — plus la régularité du résultat. Sur dix tâches par semaine, l'économie se compte en heures, dès la première semaine.

## 4.6 Organiser son usage : le rituel hebdomadaire

Les skills donnent le meilleur d'eux-mêmes dans un rituel régulier. Voici une proposition simple, à adapter à votre semaine :

**Lundi matin (15 minutes)** : ouvrez votre agent, listez vos tâches récurrentes de la semaine, et pour chacune, identifiez le skill correspondant. Cinq tâches, cinq demandes, cinq résultats prêts dans la matinée.

**En cours de semaine** : à chaque tâche récurrente, déléguez au lieu de faire. Un email de suivi de commande, une réponse d'avis, un point de trésorerie : le skill est là, la demande prend trente secondes.

**Vendredi (10 minutes)** : faites le bilan. Quelles tâches avez-vous déléguées ? Lesquelles pourriez-vous déléguer la semaine prochaine ? La liste de vos cinq tâches les plus récurrentes se précise — c'est l'objectif de la promesse de ce guide.

Le rituel fonctionne parce qu'il ne demande aucun effort technique : seulement la décision de déléguer.

## 4.7 Aller plus loin : enchaîner les skills

Les skills se combinent. Un même dossier client peut mobiliser plusieurs compétences : le skill `fiche-client` (commerce) pour préparer le profil, puis `argumentaire-vente` pour la proposition, puis `email-bienvenue` après la vente. Vous pouvez demander à l'agent d'enchaîner :

```
Utilise le skill fiche-client pour préparer la fiche de Mme Moreau (cliente depuis 2023, achète des lampes, budget moyen 150 €, dernière commande annulée), puis le skill argumentaire-vente pour préparer ma proposition de la nouvelle collection.
```

L'agent enchaîne les deux méthodes et vous livre un dossier complet. C'est ainsi que la bibliothèque de cinquante skills devient un système de travail, pas une collection de fichiers.

## 4.8 Ce que vous devez retenir de ce chapitre

- Choisissez le skill par sa description et sa section d'usage ; en cas de doute, laissez l'agent choisir ;
- Décrivez en quatre blocs : skill, contexte, contraintes, format attendu ;
- Validez en trois lectures : structure, chiffres et faits, ton et orthographe ;
- Les cinq erreurs se corrigent toutes par de la précision — plus de contexte, plus de contraintes, plus de relecture ;
- Adoptez un rituel hebdomadaire : déléguez les tâches récurrentes, mesurez votre progression.


---

# Chapitre 5 — Créer vos propres skills

Les cinquante skills de vos packs couvrent les tâches les plus répandues. Mais votre métier a forcément des tâches qui n'appartiennent qu'à vous : votre façon de préparer un chantier, votre rituel de clôture de caisse, votre processus de traitement des demandes. Ce chapitre vous apprend à transformer ces savoir-faire en skills — c'est la compétence qui rend l'outil vraiment vôtre.

## 5.1 Ce qu'est un bon skill : le test des trois critères

Avant de rédiger quoi que ce soit, vérifiez que votre tâche mérite un skill :

1. **La tâche est récurrente** : vous la faites au moins une fois par mois. Une tâche faite une fois par an ne vaut pas un skill ;
2. **La tâche a une méthode** : elle se déroule en étapes identifiables, avec des règles et des pièges. Si vous ne savez pas expliquer votre méthode, commencez par l'écrire pour vous-même ;
3. **La tâche produit un résultat standard** : un document, un message, un calcul, une décision — quelque chose de vérifiable.

Si les trois critères sont réunis, la tâche est un excellent candidat. Sinon, gardez-la hors des skills.

## 5.2 La méthode en six étapes

### Étape 1 — Définir la tâche précisément

Écrivez en une phrase ce que le skill doit produire, et en une phrase ce qu'il ne doit pas produire. Exemple : « Ce skill produit la séquence complète des relances de paiement en trois niveaux. Il ne produit pas de mise en demeure légale — cela relève d'un professionnel du droit. » Cette délimitation empêche le skill de déborder sur d'autres sujets.

### Étape 2 — Écrire la description (frontmatter)

La description est la phrase que l'agent lit pour décider si le skill correspond à une demande. Une bonne description :

- commence par un verbe d'action (« Rédiger », « Chiffrer », « Préparer », « Analyser », « Organiser ») ;
- précise le résultat (« une séquence de 3 relances », « un devis complet », « une fiche en 5 sections ») ;
- reste en une seule phrase, lisible en dix secondes.

Exemple réel tiré de vos packs : « Chiffrer un devis artisanal complet : analyse de la demande, postes détaillés, temps de pose réaliste, marge saine et mentions obligatoires. » Verbe, résultat, précisions : tout y est.

### Étape 3 — Lister les instructions pas à pas

C'est le cœur du travail. Écrivez les étapes dans l'ordre où vous les faites réellement — pas dans l'ordre idéal, dans l'ordre réel. Pour chaque étape, ajoutez le détail qui fait la différence : le seuil, le piège, la règle. « Vérifiez le dossier » est une mauvaise instruction ; « Vérifiez que les trois justificatifs sont présents et datés de moins de 3 mois » est une bonne instruction.

Rédigez entre 4 et 10 étapes. Moins de 4 : la tâche est trop simple pour un skill. Plus de 10 : découpez en deux skills.

### Étape 4 — Rédiger un exemple concret

L'exemple est ce qui distingue un skill d'une simple liste d'instructions. Il montre le niveau de résultat attendu. Utilisez un cas réel que vous connaissez par cœur : un vrai client, de vrais chiffres, un vrai résultat. L'exemple sert de jauge : si l'agent produit nettement moins bien, vous le saurez immédiatement.

### Étape 5 — Écrire la checklist de validation

Listez les points de contrôle : ce qui doit être vrai pour que le résultat soit acceptable. Reprenez vos propres erreurs passées : chaque erreur que vous avez déjà faite sur cette tâche devient une case de la checklist. C'est la manière la plus rapide d'améliorer votre qualité réelle.

### Étape 6 — Tester le skill

Installez le skill (chapitre 2), puis faites-lui exécuter la tâche trois fois avec des contextes différents. Comparez les résultats à votre exemple : structure conforme ? Règles respectées ? Pièges évités ? Corrigez le `SKILL.md` à chaque écart, jusqu'à ce que le résultat soit stable. Un skill est un document vivant : il s'améliore avec l'usage.

## 5.3 Le gabarit complet à copier-coller

Voici le gabarit de base, directement copiable dans un fichier nommé `SKILL.md`, lui-même placé dans un dossier portant le nom de votre skill (par exemple `cloture-caisse/SKILL.md`).

```markdown
---
name: nom-du-skill
description: Verbe d'action + résultat précis en une phrase, avec les précisions utiles.
---

# Titre du skill en français

## Objectif
Deux ou trois phrases qui décrivent le but du skill et à quoi ressemble un résultat réussi.

## Quand utiliser ce skill
- Situation concrète n° 1 où le skill s'applique.
- Situation concrète n° 2.
- Situation où le skill ne s'applique PAS (pour éviter les erreurs de choix).

## Instructions pas à pas
1. **Première étape** : détail actionnable, seuil ou piège éventuel.
2. **Deuxième étape** : détail actionnable.
3. **Troisième étape** : détail actionnable.
4. **Quatrième étape** : détail actionnable, règle métier éventuelle.
5. **Cinquième étape** : vérification intermédiaire avant de continuer.

## Exemple concret
Décrivez un cas réel : contexte, données, résultat complet attendu.

## Checklist de validation
- [ ] Point de contrôle n° 1 (obligatoire).
- [ ] Point de contrôle n° 2 (chiffre, date ou fait à vérifier).
- [ ] Point de contrôle n° 3 (ton, format, orthographe).
- [ ] Point de contrôle n° 4 (règle métier respectée).
```

### Les règles d'or de la rédaction

- **Le nom du skill** : minuscules, tirets entre les mots, pas d'accents (`cloture-caisse`, pas `clôture-caisse`). C'est l'identifiant technique ;
- **Les accents dans le texte** : le contenu du fichier, lui, est en français parfaitement accentué. C'est un document de travail, pas un identifiant ;
- **Les instructions précises** : chaque étape doit être exécutable sans votre intervention. Si une étape nécessite une information que vous n'avez pas prévue, ajoutez une instruction « Demandez au préalable : ... » ;
- **La cohérence** : le ton du skill (tutoiement ou vouvoiement) doit être celui de votre entreprise, puisque l'agent le reproduira dans les résultats.

## 5.4 L'Atelier Skill : votre outil gratuit pour créer un squelette valide

Rédiger un skill sur une page blanche peut sembler intimidant. C'est pourquoi SkillVault met à votre disposition l'Atelier Skill : un générateur en ligne, gratuit, accessible depuis le site skillvault.fr.

### À quoi sert l'Atelier Skill

L'Atelier Skill vous pose quelques questions simples — le nom de la tâche, une phrase de description, les étapes principales — et génère un squelette de `SKILL.md` valide : frontmatter correct, sections au bon endroit, structure prête à compléter. Vous obtenez un fichier propre en deux minutes, que vous n'avez plus qu'à enrichir avec vos détails métier.

### Comment l'utiliser

1. Rendez-vous sur le site SkillVault et ouvrez la page Atelier Skill ;
2. Remplissez les champs : nom du skill, description, objectif, étapes principales, exemple, points de contrôle ;
3. Téléchargez le fichier `SKILL.md` généré ;
4. Ouvrez-le dans un éditeur de texte, complétez les détails (vos seuils, vos pièges, votre exemple réel) ;
5. Placez le fichier dans un dossier portant le nom de votre skill, puis installez-le comme au chapitre 2.

### Le rôle de l'Atelier

L'Atelier ne rédige pas votre savoir-faire à votre place — personne ne le peut. Il s'occupe de la forme (structure valide, frontmatter correct, sections conformes) pour que vous vous concentriez sur le fond (votre méthode, vos règles, vos exemples). C'est la différence entre partir d'une page blanche et partir d'un cadre prêt à remplir.

### 5.5 Un skill créé de A à Z : l'exemple complet

Pour voir la méthode en action, suivons la création complète d'un skill : « le point de caisse du soir », une tâche que tout commerçant connaît.

**Étape 1 — Définir** : produire le point de caisse quotidien : encaissements par moyen de paiement, écart éventuel, et message de récapitulatif. Ne produit pas : la comptabilité, qui reste chez l'expert-comptable.

**Étape 2 — Décrire** : « Préparer le point de caisse de fin de journée : total par moyen de paiement, détection des écarts, message de récapitulatif. »

**Étape 3 — Instructions** : lister les encaissements par moyen de paiement (espèces, carte, chèques, tickets restaurant), comparer au ticket Z de la caisse, identifier l'écart, décider de la suite selon le seuil (écart inférieur à 5 € : noter ; supérieur : vérifier le détail des opérations), rédiger le message de récapitulatif.

**Étape 4 — Exemple** : un soir réel avec les chiffres, l'écart constaté et le message rédigé.

**Étape 5 — Checklist** : les quatre points de contrôle : total par moyen de paiement présent, écart calculé et expliqué, seuil appliqué, message prêt à envoyer.

**Étape 6 — Tester** : trois soirs avec des données différentes, correction des imprécisions.

Le résultat, prêt à être placé dans `point-caisse-soir/SKILL.md` :

```markdown
---
name: point-caisse-soir
description: Préparer le point de caisse de fin de journée : total par moyen de paiement, détection des écarts, message de récapitulatif.
---

# Point de caisse du soir

## Objectif
Produire le point de caisse quotidien : encaissements par moyen de paiement, écart éventuel par rapport au ticket Z, et message de récapitulatif prêt à envoyer.

## Quand utiliser ce skill
- Chaque soir de fermeture, après le tirage du ticket Z.
- Après un service où les paiements ont été nombreux (week-end, jour de marché).

## Instructions pas à pas
1. **Listez les encaissements par moyen de paiement** : espèces, carte, chèques, tickets restaurant. Vérifiez les totaux de votre TPE.
2. **Comparez au ticket Z** : le total de vos encaissements doit correspondre au total du ticket Z de la caisse.
3. **Calculez l'écart** : total ticket Z moins total encaissements. Écart positif = argent manquant ; écart négatif = surplus.
4. **Appliquez le seuil** : écart inférieur à 5 €, notez-le dans le message et passez à la suite ; écart supérieur, vérifiez le détail des opérations avant de conclure.
5. **Rédigez le message de récapitulatif** : total du jour, répartition par moyen de paiement, écart éventuel, consigne pour le lendemain.

## Exemple concret
Soir du mardi : espèces 312 €, carte 1 048 €, tickets restaurant 64 €, total 1 424 €. Ticket Z : 1 421,50 €. Écart : 2,50 € d'argent manquant, sous le seuil de 5 € — noté, sans blocage. Message : « Mardi : 1 424 € encaissés (312 espèces, 1 048 carte, 64 tickets resto). Écart de 2,50 € au ticket Z, à surveiller. »

## Checklist de validation
- [ ] Total par moyen de paiement présent et cohérent.
- [ ] Écart calculé par rapport au ticket Z et expliqué.
- [ ] Seuil appliqué : écart supérieur à 5 € vérifié en détail.
- [ ] Message de récapitulatif rédigé, prêt à envoyer.
```

Ce skill tient en une page, contient une vraie méthode (le seuil de 5 €), un exemple chiffré et une checklist actionnable. C'est exactement le standard des skills SkillVault — et maintenant, c'est le vôtre aussi.

## 5.6 Améliorer un skill existant

Vos packs ne sont pas figés : vous pouvez adapter un skill à votre façon de travailler. La démarche :

1. Ouvrez le `SKILL.md` concerné dans un éditeur de texte ;
2. Modifiez les instructions pour refléter votre méthode (vos seuils, vos délais, vos règles) ;
3. Remplacez l'exemple par un cas qui vous parle ;
4. Ajoutez des cases à la checklist si vous connaissez des pièges non couverts ;
5. Sauvegardez : les modifications sont immédiatement prises en compte au prochain rechargement de l'agent.

Conseil : gardez une copie des fichiers d'origine dans un dossier séparé, pour pouvoir revenir en arrière si besoin.

## 5.7 Partager et protéger vos skills

Un skill est un fichier texte : il se partage en l'envoyant, comme n'importe quel document. Si vous créez des skills pour votre équipe, déposez-les dans un dossier partagé (serveur, espace de stockage en ligne) et demandez à chacun de les installer selon le chapitre 2.

Une remarque de bon sens : un skill contient votre méthode de travail, qui fait partie de votre valeur. Partagez ce que vous voulez partager, et gardez pour vous ce qui fait votre différence.

## 5.8 Ce que vous devez retenir de ce chapitre

- Un bon skill répond à trois critères : tâche récurrente, méthode identifiable, résultat standard ;
- Six étapes : définir, décrire, lister les instructions, exemplifier, checker, tester ;
- Le gabarit du chapitre couvre la structure ; vos détails métier font la valeur ;
- L'Atelier Skill génère un squelette valide en deux minutes, gratuitement ;
- Un skill est vivant : testez-le, corrigez-le, améliorez-le avec l'usage.

---

# Chapitre 6 — Le skill sur-mesure et l'offre entreprise

Vos packs couvrent cinquante tâches, mais votre entreprise a des besoins spécifiques. C'est ce que couvrent les offres sur-mesure : des skills rédigés pour vous, sur votre métier, avec votre méthode.

## 6.1 Le skill sur-mesure du Pack Complet

Le Pack Complet (89 €) inclut, au-delà des cinquante skills et du guide, **un skill rédigé sur-mesure pour vous** : une tâche spécifique à votre activité, formalisée selon la structure SkillVault (frontmatter, objectif, instructions, exemple, checklist).

### Comment le commander

1. **Décrivez votre besoin** en quelques lignes : la tâche, sa fréquence, le résultat attendu, vos contraintes ;
2. Envoyez la description par email à contact@skillvault.fr, avec votre numéro de commande ;
3. L'équipe SkillVault vous pose d'éventuelles questions de précision (une seule série de questions en général) ;
4. **Livraison sous 5 jours ouvrés** : vous recevez le dossier complet du skill, prêt à installer.

### Bien décrire son besoin : exemples

Une bonne demande de skill sur-mesure ressemble à ceci :

> « Je suis fleuriste. Je veux un skill qui prépare la commande d'un mariage : chiffrage par poste (fleurs, main-d'œuvre, livraison, location de vases), planning de la journée J, et messages de suivi client avant et après l'événement. Fréquence : 2 à 3 fois par mois. Contrainte : devis valable 15 jours, acompte 40 %. »

> « Je suis indépendant en menuiserie. Je veux un skill qui rédige les messages de relance des clients qui n'ont pas donné suite à leur devis signé, sur un ton non insistant, avec un rappel des travaux inclus et une question de relance. Fréquence : toutes les semaines. »

> « Je gère un food-truck. Je veux un skill qui prépare le point de caisse de fin de journée : rapprochement des encaissements (espèces, carte, tickets resto), détection des écarts, et message de récapitulatif pour mon associé. »

La structure gagnante : le métier, la tâche précise, le résultat attendu, la fréquence, les contraintes.

### Exemples de demandes à éviter

- « Un skill pour tout gérer » : trop vaste, aucune méthode n'est formalisable. Découpez en tâches ;
- « Un skill comme celui de mon concurrent » : chaque entreprise a sa méthode ; décrivez la vôtre ;
- « Un skill qui fait de la comptabilité complète » : la comptabilité complète relève de votre expert-comptable ; ciblez une tâche précise comme le rapprochement ou le pointage.

## 6.2 La Licence Entreprise : 10 personnes, 5 skills personnalisés

La Licence Entreprise (197 €) s'adresse aux structures qui veulent équiper une équipe : les cinq packs complets, **l'usage pour 10 personnes**, **5 skills personnalisés** rédigés pour votre organisation, et un **cadrage de 45 minutes** pour bien démarrer.

### Le cadrage de 45 minutes

Le cadrage est une visioconférence (ou un échange approfondi par écrit si vous préférez) avec l'équipe SkillVault. Son but : identifier les cinq tâches qui vous feront gagner le plus de temps, formaliser vos méthodes, et définir la bonne façon de déployer les skills dans l'équipe. Vous repartez avec une feuille de route.

### Le déroulé de la Licence Entreprise

1. **Commande et paiement** : vous recevez les cinq packs immédiatement, comme pour toute commande ;
2. **Cadrage (45 min)** : sous quelques jours, échange pour identifier les besoins ;
3. **Rédaction des 5 skills personnalisés** : livrés **sous 10 jours ouvrés** après le cadrage ;
4. **Déploiement** : chaque membre de l'équipe installe les skills selon le chapitre 2 ; le guide vous sert de support de formation interne.

### Les cas typiques d'usage entreprise

- Une **agence de communication** qui équipe ses 10 collaborateurs des packs Marketing et Commerce, plus des skills maison : traitement d'un brief client, rédaction d'un rapport de campagne, relance de prospects ;
- Une **entreprise de bâtiment** qui déploie les packs Artisanat et Comptabilité auprès de ses conducteurs de travaux et de son administratif, plus des skills maison : préparation de réunion de chantier, relevé de réserves, suivi de sous-traitants ;
- Une **TPE de services** qui standardise ses procédures RH et son suivi commercial grâce aux packs RH et Commerce, plus des skills maison : accueil téléphonique, traitement des demandes clients, préparation des comités.

### Ce que l'équipe gagne

Le déploiement des skills en équipe standardise les méthodes : chacun produit avec les mêmes règles, la même qualité, les mêmes formats. C'est la différence entre une équipe où chacun fait « à sa façon » et une équipe où la méthode est écrite, partagée et appliquée.

## 6.3 Les délais, honnêtement

Les délais annoncés sont des engagements : **5 jours ouvrés** pour le skill sur-mesure du Pack Complet, **10 jours ouvrés après le cadrage** pour les skills personnalisés de la Licence Entreprise. La rédaction d'un skill demande du soin : analyse de votre besoin, formalisation de la méthode, rédaction, test. Un délai court mais tenu vaut mieux qu'un délai rapide non respecté — c'est la règle de l'entreprise.

Si votre besoin est urgent, dites-le dès la commande : l'équipe vous dira franchement ce qui est possible.

## 6.4 La garantie 14 jours s'applique aussi au sur-mesure

Toutes les offres, y compris les services sur-mesure, bénéficient de la garantie satisfait ou remboursé de 14 jours. Si un skill livré ne correspond pas à votre besoin après échange, vous êtes remboursé. La règle est simple : vous ne gardez que ce qui vous sert.

## 6.5 Ce que vous devez retenir de ce chapitre

- Le Pack Complet inclut un skill sur-mesure livré sous 5 jours ouvrés : décrivez métier, tâche, résultat, fréquence et contraintes ;
- La Licence Entreprise offre 5 skills personnalisés sous 10 jours ouvrés après un cadrage de 45 minutes, et couvre 10 utilisateurs ;
- Les bons exemples de demande sont précis et circonscrits ; les mauvais sont vastes et vagues ;
- La garantie 14 jours couvre aussi le sur-mesure.

---

# Annexes

## Annexe A — Le catalogue des 50 skills

Voici les cinquante skills de vos packs, avec leur description en une ligne. Les noms techniques sont sans accents (c'est leur identifiant) ; les descriptions sont en français complet.

### Pack Commerce

| Skill | Description |
|---|---|
| relance-panier | Rédiger la séquence de 3 relances pour un panier abandonné, avec un angle différent à chaque message. |
| reponse-avis-google | Répondre aux avis Google (positifs et négatifs) pour soigner la réputation locale. |
| fiche-produit | Rédiger une fiche produit e-commerce complète qui vend sans exagérer. |
| argumentaire-vente | Construire un argumentaire de vente structuré, prêt à utiliser en entretien ou par message. |
| email-bienvenue | Rédiger la séquence d'emails de bienvenue qui lance la relation commerciale. |
| relance-commande | Rédiger les messages de suivi de commande qui rassurent et réduisent les demandes au support. |
| reponse-reclamation | Gérer une réclamation client par écrit, de l'accusé de réception à la clôture. |
| upsell-croise | Proposer des produits complémentaires au bon moment, sans être intrusif. |
| fiche-client | Rédiger une fiche client opérationnelle pour personnaliser la relation et la vente. |
| promo-email | Rédiger un email promotionnel efficace, avec une offre réelle et une urgence honnête. |

### Pack Artisanat

| Skill | Description |
|---|---|
| devis-chiffre | Chiffrer un devis complet : postes détaillés, temps de pose réaliste, marge saine, mentions obligatoires. |
| relance-chantier | Relancer les prospects et chantiers en attente avec des messages professionnels et non insistants. |
| planning-rdv | Organiser les rendez-vous clients avec un planning réaliste qui respecte les temps de déplacement. |
| facture-acompte | Émettre une facture d'acompte conforme et encaisser le solde sans friction. |
| reponse-appel-offres | Répondre à un appel d'offres avec un dossier de candidature complet et conforme. |
| message-commercial | Rédiger le premier message de prospection d'un artisan : personnalisé, concret, sans jargon. |
| suivi-chantier-client | Tenir le client informé de l'avancement de son chantier avec des messages courts et réguliers. |
| fiche-technique-materiaux | Préparer une fiche technique claire (matériaux, quantités, mise en œuvre) pour un chantier. |
| reception-travaux | Organiser la réception des travaux : visite de contrôle, PV, réserves et levée des réserves. |
| maintenance-preventive | Mettre en place les rappels de maintenance qui fidélisent et lissent l'activité. |

### Pack RH

| Skill | Description |
|---|---|
| fiche-de-poste | Rédiger une fiche de poste complète, base du recrutement, de l'intégration et de l'évaluation. |
| grille-entretien | Préparer une grille d'entretien d'embauche structurée, avec notation objective. |
| onboarding-30-jours | Construire le programme d'intégration des 30 premiers jours d'un nouvel arrivant. |
| annonce-emploi | Rédiger une annonce d'emploi efficace et conforme, avec missions réelles et fourchette salariale. |
| entretien-annuel | Préparer et conduire l'entretien annuel : bilan, vigilance, objectifs, plan de développement. |
| plan-formation | Construire le plan de formation annuel : besoins, priorités, budget et calendrier. |
| message-candidat-refuse | Rédiger le refus de candidature : clair, respectueux, personnalisé, sans formule blessante. |
| gestion-conflits | Désamorcer un conflit entre collègues : écouter, recadrer, trouver une solution commune. |
| entretien-depart | Conduire l'entretien de départ : recueillir les raisons réelles et capitaliser. |
| planning-conges | Organiser le planning des congés : priorités, équité, continuité d'activité, communication. |

### Pack Comptabilité

| Skill | Description |
|---|---|
| relance-impaye | Gérer une facture impayée en 3 niveaux de relance, avec les bons délais et les bonnes formules. |
| note-de-frais | Vérifier et traiter une note de frais : justificatifs, catégories, remboursement. |
| suivi-tresorerie | Analyser la trésorerie mensuelle et détecter les tensions avant la rupture. |
| facture-conforme | Émettre une facture avec toutes les mentions obligatoires. |
| declaration-tva | Préparer la déclaration de TVA : encaissements, TVA collectée et déductible, délais. |
| rapprochement-bancaire | Réaliser le rapprochement bancaire mensuel et identifier les écarts. |
| seuil-rentabilite | Calculer le seuil de rentabilité : charges fixes, marge, point mort. |
| pointage-fournisseurs | Contrôler les factures fournisseurs avant paiement et détecter erreurs et doublons. |
| cloture-mensuelle | Réaliser la clôture mensuelle : caisse, banque, TVA, factures, point de trésorerie. |
| previsionnel-cashflow | Construire un prévisionnel de trésorerie sur 12 semaines avec plancher de sécurité. |

### Pack Marketing

| Skill | Description |
|---|---|
| post-linkedin | Rédiger un post LinkedIn professionnel qui engage, sans clichés. |
| calendrier-contenu | Construire un calendrier de contenu sur 4 semaines : piliers, formats, rythme. |
| reponse-avis-negatif | Répondre à un avis négatif en ligne : désamorcer, proposer une solution privée. |
| offre-promo | Concevoir une offre promotionnelle solide, sans brader sa marge. |
| titre-accrocheur | Formuler 10 titres et accroches percutants, sans promesses fausses. |
| page-vente | Rédiger une page de vente complète avec des arguments réels et vérifiables. |
| email-newsletter | Rédiger une newsletter éditoriale qui fidélise sans spammer. |
| brief-agence | Rédiger un brief clair pour un prestataire : contexte, objectif, livrables, budget. |
| slogan-marque | Concevoir des slogans structurés, testés pour l'honnêteté et la mémorisation. |
| rapport-campagne | Rédiger le rapport de fin de campagne : objectifs, résultats, analyse, recommandations. |

## Annexe B — Glossaire

**Agent IA (ou agent d'intelligence artificielle)** : un programme qui exécute des tâches sur demande, en utilisant un modèle de langage. Claude Code, Codex, Copilot, Cursor et Hermes sont des agents ; ChatGPT et Gemini le sont aussi dans leurs versions récentes.

**Checklist de validation** : la liste de points de contrôle qui termine chaque skill. Elle définit ce qui doit être vrai pour qu'un résultat soit acceptable.

**Frontmatter** : le bloc d'informations structurées en tête d'un fichier `SKILL.md`, encadré par deux lignes de tirets, contenant le nom et la description du skill. C'est la carte d'identité que l'agent lit pour choisir le bon skill.

**LLM (Large Language Model, modèle de langage)** : le programme qui génère les textes et les raisonnements de l'agent. Le LLM lit vos demandes et le contenu des skills, et produit les réponses. Vous n'avez jamais à interagir directement avec lui : l'agent fait l'intermédiaire.

**Markdown** : un format de texte simple qui structure les documents avec des titres, des listes, des tableaux. Les fichiers `.md` s'ouvrent dans n'importe quel éditeur de texte.

**Prompt** : la demande que vous tapez dans la conversation avec l'agent. Un prompt isolé est jetable ; associé à un skill, il déclenche une compétence structurée.

**Skill** : une compétence métier formalisée dans un dossier contenant un fichier `SKILL.md`. Le skill contient la méthode, les règles, un exemple et une checklist.

**SKILL.md** : le fichier central d'un skill. Toujours nommé ainsi, en majuscules, placé dans le dossier du skill.

**ZIP** : un format d'archive qui regroupe plusieurs fichiers en un seul, pour faciliter le transfert. Vos packs sont livrés en ZIP ; il faut les décompresser avant installation.

## Annexe C — La FAQ du guide

**1. Faut-il savoir programmer pour installer et utiliser les skills ?**
Non. L'installation consiste à copier des dossiers, et l'utilisation consiste à écrire des demandes en français. Aucune ligne de code n'est nécessaire.

**2. Les skills fonctionnent-ils avec mon agent gratuit ?**
Si votre agent accepte le format `SKILL.md`, oui, la version gratuite ou d'essai suffit. Les agents qui n'acceptent pas le format restent utilisables avec le plan B : coller le contenu du skill dans la conversation (chapitre 2, section 2.7).

**3. Puis-je installer les mêmes skills dans plusieurs agents ?**
Oui. Un skill est un dossier de fichiers : copiez-le dans le dossier de skills de chaque agent. Vos skills vous suivent partout.

**4. Que se passe-t-il si je change d'ordinateur ?**
Vous réinstallez les skills : décompressez vos ZIP de sauvegarde et copiez les dossiers dans le dossier de skills du nouvel agent. Deux minutes par pack.

**5. L'agent peut-il faire une erreur dans un chiffre ou une date ?**
Oui, comme un collaborateur humain. C'est pour cela que chaque skill se termine par une checklist, et que la règle des trois lectures (chapitre 4) fait partie de la méthode. Vous validez, l'agent exécute.

**6. Puis-je modifier un skill pour l'adapter à ma méthode ?**
Oui, et c'est recommandé. Ouvrez le `SKILL.md` dans un éditeur de texte, modifiez les instructions, l'exemple ou la checklist, et sauvegardez. Les changements sont pris en compte au prochain rechargement de l'agent.

**7. Que faire si un skill ne donne pas le résultat attendu ?**
Vérifiez d'abord que le skill est bien installé et nommé dans votre demande, puis que vous avez fourni le contexte complet (chapitre 4). Si le résultat reste insuffisant, précisez votre demande et relancez. Les skills s'améliorent aussi avec vos corrections.

**8. Mes données sont-elles en sécurité ?**
Les skills sont des fichiers locaux : ils restent sur votre ordinateur. Les informations que vous tapez dans la conversation avec l'agent sont traitées par l'éditeur de votre agent selon ses conditions d'utilisation — ne communiquez jamais de données sensibles (coordonnées bancaires, mots de passe) dans une conversation d'IA.

**9. Que couvre la garantie de 14 jours ?**
Toutes les offres sont garanties satisfait ou remboursé pendant 14 jours après l'achat. Si le contenu ne correspond pas à ce qui était annoncé, contactez le support pour être remboursé.

**10. Les skills fonctionneront-ils encore dans cinq ans ?**
Le format `SKILL.md` est devenu un standard partagé par les principaux éditeurs (chapitre 1) : vos skills sont des fichiers texte standard, lisibles par tout système. Ils évolueront avec les agents, et ce guide vous donne la méthode pour les adapter à chaque changement.

## Annexe D — Checklist finale : avant de lancer votre premier skill

Imprimez cette page ou gardez-la ouverte pendant votre première session. Chaque case cochée vous rapproche d'un premier résultat réussi.

**Avant de commencer**
- [ ] Mon pack est décompressé et la structure est correcte (un dossier par skill, un `SKILL.md` par dossier) ;
- [ ] Mon agent IA est installé et fonctionne (version gratuite ou payante) ;
- [ ] J'ai identifié le dossier de skills de mon agent (chapitre 2).

**Première installation**
- [ ] J'ai copié les dossiers de skills dans le bon dossier ;
- [ ] J'ai relancé l'agent après l'installation ;
- [ ] J'ai vérifié l'installation avec une demande de test.

**Première utilisation**
- [ ] J'ai choisi le bon skill en lisant sa description et sa section d'usage ;
- [ ] J'ai décrit la tâche avec les quatre blocs : skill, contexte, contraintes, format ;
- [ ] J'ai nommé le skill explicitement dans ma demande.

**Validation**
- [ ] J'ai relu la sortie avec la règle des trois lectures (structure, chiffres, ton) ;
- [ ] J'ai vérifié la checklist du skill, case par case ;
- [ ] J'ai corrigé les éventuels écarts avant d'utiliser le résultat.

**Dans la semaine**
- [ ] J'ai identifié 5 tâches récurrentes à déléguer ;
- [ ] J'ai délégué au moins la première avec un skill ;
- [ ] J'ai noté les améliorations à apporter (contexte, contraintes) pour la prochaine fois.

## Annexe E — Les tâches à déléguer en premier, pack par pack

Pour ceux qui ne savent pas par où commencer, voici pour chaque pack les deux tâches qui donnent le résultat le plus visible le plus rapidement.

| Pack | Tâche à déléguer en premier | Skill | Gain immédiat |
|---|---|---|---|
| Commerce | Relancer les paniers abandonnés | relance-panier | Des ventes récupérées sans y penser, des textes prêts à coller dans votre outil d'emailing |
| Commerce | Répondre aux avis Google | reponse-avis-google | Votre réputation soignée en 10 minutes par semaine, au lieu d'une journée de procrastination |
| Artisanat | Chiffrer vos devis | devis-chiffre | Des devis complets et rentables, avec les mentions obligatoires — sans oublier la marge |
| Artisanat | Suivre les chantiers en attente | relance-chantier | Des chantiers reportés qui redémarrent, sans message insistant |
| RH | Rédiger la fiche de poste de votre prochaine embauche | fiche-de-poste | Un document professionnel qui structure tout le recrutement |
| RH | Intégrer un nouvel arrivant | onboarding-30-jours | Un salarié opérationnel et rassuré dès le premier mois |
| Comptabilité | Relancer les factures impayées | relance-impaye | De l'argent encaissé plus vite, avec les bons niveaux de relance |
| Comptabilité | Analyser la trésorerie du mois | suivi-tresorerie | Les tensions détectées avant la rupture, le mois suivant |
| Marketing | Rédiger vos posts LinkedIn | post-linkedin | Une présence régulière sans y passer ses soirées |
| Marketing | Construire votre calendrier de contenu | calendrier-contenu | Un mois de contenu planifié en une heure, au lieu d'une décision chaque matin |

Le principe commun : choisissez la tâche qui vous coûte le plus de temps ou de stress, déléguez-la cette semaine, et validez le résultat avec la checklist. La semaine suivante, ajoutez-en une deuxième. Au bout d'un mois, vos cinq tâches les plus récurrentes sont déléguées — c'est la promesse de ce guide, tenue.

Voilà. Vous avez maintenant tout ce qu'il faut : comprendre, installer, utiliser, valider, créer. Les skills sont installés, la méthode est claire, il ne reste qu'à déléguer. Votre agent attend votre première demande — et vous savez exactement comment la formuler.

L'équipe SkillVault — contact@skillvault.fr
