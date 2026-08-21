# SkillVault — Skills métier en français pour agents IA

Catalogue français de compétences métier (format `SKILL.md`) à installer dans un agent IA (Claude Code, Codex, Copilot…). Promesse : **« Installez une compétence métier dans votre agent IA en 2 minutes — en français, calibrée pour votre métier. »**

## Ce que vend le site

| Offre | Prix | Contenu |
|---|---|---|
| Pack Métier | 29 € | 1 pack au choix (10 skills en ZIP) + guide PDF d'installation |
| Pack Complet | 89 € | Les 5 packs (50 skills) + guide 40 pages + 1 skill sur-mesure |
| Licence Entreprise | 197 € | Les 5 packs + usage équipe 10 personnes + 5 skills personnalisés + cadrage 45 min |

- Garantie satisfait ou remboursé **14 jours**. Livraison par email sous 24 h ouvrées. Skill sur-mesure sous 5 jours ouvrés (Pack Complet), 10 jours (Entreprise, après cadrage 45 min).
- Marges ~97 % (le produit = du markdown rédigé).

## Structure du projet

```
skillvault/
├── index.html              # Landing page (design « atelier sombre ambre »)
├── outil.html              # Atelier Skill : générateur de SKILL.md valide (10 questions, 100 % local)
├── chatbot-config.js       # Config chatbot aux couleurs du site (ambre #ffb340)
├── chatbot.js              # Moteur chatbot (référence ai-course-builder, adapté)
├── guide-installation.md   # Guide 40 pages « Installer et piloter vos skills métier » (16 266 mots)
├── PDF/guide-installation.pdf  # Guide converti (41 pages, %PDF validé)
├── zip/                    # ZIP de livraison réels (5 packs + pack complet 50 skills + guide)
├── emails/                 # Séquence de 3 emails (confirmation, livraison, upsell -15 %)
├── README.md
└── packs/
    ├── commerce/    → 10 skills (relance-panier, reponse-avis-google, fiche-produit, …)
    ├── artisanat/   → 10 skills (devis-chiffre, relance-chantier, planning-rdv, …)
    ├── rh/          → 10 skills (fiche-de-poste, grille-entretien, onboarding-30-jours, …)
    ├── compta/      → 10 skills (relance-impaye, note-de-frais, suivi-tresorerie, …)
    └── marketing/   → 10 skills (post-linkedin, calendrier-contenu, reponse-avis-negatif, …)
```

Chaque skill = un dossier avec un `SKILL.md` contenant : frontmatter (`name` + `description`), instructions étape par étape, exemple concret et checklist de validation. **50 skills rédigés, aucun placeholder.**

## Identité visuelle (design UNIQUE « atelier sombre ambre »)

Fond graphite nuit `#0e1116`, texte ivoire `#f4efe6`, accent ambre `#ffb340` (CTA, titres), violet `#8b7cff` (badges agent), vert `#3ddc84` (chips « prêt à l'emploi »), typo Sora 800 + IBM Plex Mono (Google Fonts), mockup terminal d'installation, grille fine + radials ambre discrets, zéro 3D. Aucune confusion avec les identités existantes du portefeuille (pétrole/or, terracotta, cyber vert, orchidée, cobalt/cyan interdit).

## Fonctionnement réel de la vente

1. Le visiteur choisit un pack (boutons des cartes d'offres → pré-remplissent le formulaire).
2. Le formulaire envoie une vraie commande via **EmailJS** (service `service_cy1ytdb`, template `template_xpo58cv`, clé publique `8Pui4ZEqxW2jRVF7h`, payload `{site, name, email, question}` avec le récapitulatif complet de la commande).
3. Le vendeur reçoit la commande par email → envoie les coordonnées de paiement (virement ou message privé) + la facture.
4. Livraison des ZIP (`zip/`) et du guide PDF (`PDF/`) par email dès réception du paiement. **Aucun paiement en ligne automatisé** : c'est assumé et écrit sur la page (« paiement par virement ou message privé »).

Le chatbot (en bas à droite) répond aux questions fréquentes (9 FAQs business : prix 29/89/197 €, livraison 24 h, garantie 14 j, agents compatibles) et capture les leads via EmailJS si la question sort de la FAQ. Accent ambre `#ffb340` = couleur principale du site, texte sombre `#1a1208` sur accent clair (règle lum()).

## Outil réel (zéro simulateur)

`outil.html` — **Atelier Skill** : générateur de SKILL.md valide et installable. 10 questions (métier, tâche, public, niveau, contraintes, exemples, livrable, fréquence, erreurs, critère de succès, nom) → génère le frontmatter (name, description) + sections instructions/exemple/checklist formatées + bouton **Télécharger le .md** (Blob, réel) + copie presse-papiers. 100 % local (aucune donnée envoyée). Différenciation honnête : le générateur fait UN squelette valide ; les packs = skills testés, calibrés métier, avec scripts et pièges.

## Limites et honnêteté (à savoir avant de promettre plus)

- **Le paiement en ligne n'existe pas encore** (pas de Stripe) : le tunnel est « formulaire → email → virement/DM → livraison manuelle ». Les délais de livraison (« sous 24 h ouvrées ») doivent être tenus par le vendeur.
- **Les skills sont des documents d'instructions** : ils ne font rien tout seuls. Il faut un agent IA (Claude Code, Codex, Copilot, ChatGPT…) où les installer. La page le dit explicitement dans le footer.
- **« 2 minutes »** = temps d'installation du skill (copier un dossier), pas temps de mise en place de l'agent lui-même. La page le précise.
- **Le skill sur-mesure** (Pack Complet, sous 5 jours ouvrés) et **les 5 skills personnalisés** (Licence Entreprise, sous 10 jours après cadrage 45 min) sont des engagements de rédaction à honorer.
- **Garantie satisfait ou remboursé 14 jours** : écrite sur la page, à appliquer réellement.
- Les références aux outils (Claude Code, Codex, Copilot) sont des affirmations de compatibilité de format, pas des certifications officielles — le footer précise que les résultats dépendent de l'outil et des informations fournies par l'utilisateur.

## Vérifications effectuées

- 5 packs × 10 skills = 50 dossiers, chacun avec un `SKILL.md` au frontmatter valide (vérifié par script).
- Aucun placeholder (grep `PLACEHOLDER`/`TODO`/`Lorem` = 0 résultat).
- EmailJS branché dans le formulaire ET dans le chatbot (mêmes service/template/clé).
- JSON-LD (Organization + Product/Offers + FAQPage), OG tags et viewport présents.
- Chatbot : accent `#ffb340` (couleur principale du site), nom « SkillVault », 9 FAQs 100 % business, EmailJS en fallback, ordre des scripts config avant bot.
- Guide PDF : 41 pages, signature `%PDF-` validée, généré via `~/Documents/scripts/md2pdf.py`.
- ZIP de livraison : 6 archives réelles (5 packs + complet 50 skills + guide PDF), 106 fichiers, vérifiées par `unzip -l`.
- Outil : générateur testé (frontmatter parseable, Blob téléchargeable, copie presse-papiers).
- Design refondu en ambre après audit : l'ancienne palette cobalt/cyan/violet (template « sombre cyan/violet » interdit) a été remplacée par l'identité « atelier sombre ambre » imposée par la fiche.

## Déploiement

Repo `Dembis91-940/skillvault`, GitHub Pages avec `build_type=legacy`. Vérification : HTTP 200 + grep du contenu après rebuild (~90 s).

Pour tester en local :

```bash
cd ~/Documents/livrables/skillvault && python3 -m http.server 8080
# → http://localhost:8080
```
