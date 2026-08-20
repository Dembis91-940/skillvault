# SkillVault — Skills métier en français pour agents IA

Catalogue français de compétences métier (format `SKILL.md`) à installer dans un agent IA (Claude Code, Codex, Copilot…). Promesse : **« Installez une compétence métier dans votre agent IA en 2 minutes — en français, calibrée pour votre métier. »**

## Ce que vend le site

| Offre | Prix | Contenu |
|---|---|---|
| Pack Métier | 29 € | 1 pack au choix (10 skills en ZIP) + guide PDF d'installation |
| Pack Complet | 89 € | Les 5 packs (50 skills) + guide 40 pages + 1 skill sur-mesure |
| Licence Entreprise | 197 € | Les 5 packs + usage équipe 10 personnes + 5 skills personnalisés + cadrage 45 min |

## Structure du projet

```
skillvault/
├── index.html          # Landing page (une seule page, tout inclus)
├── chatbot-config.js   # Config du chatbot aux couleurs du site (cobalt #2E6BFF)
├── chatbot.js          # Moteur chatbot (copié depuis ai-course-builder, adapté)
├── README.md
└── packs/
    ├── commerce/    → 10 skills (relance-panier, reponse-avis-google, fiche-produit, …)
    ├── artisanat/   → 10 skills (devis-chiffre, relance-chantier, planning-rdv, …)
    ├── rh/          → 10 skills (fiche-de-poste, grille-entretien, onboarding-30-jours, …)
    ├── compta/      → 10 skills (relance-impaye, note-de-frais, suivi-tresorerie, …)
    └── marketing/   → 10 skills (post-linkedin, calendrier-contenu, reponse-avis-negatif, …)
```

Chaque skill = un dossier avec un `SKILL.md` contenant : frontmatter (`name` + `description`), instructions étape par étape, exemple concret et checklist de validation. **50 skills rédigés, aucun placeholder.**

## Fonctionnement réel de la vente

1. Le visiteur choisit un pack (boutons des cartes d'offres → pré-remplissent le formulaire).
2. Le formulaire envoie une vraie commande via **EmailJS** (service `service_cy1ytdb`, template `template_xpo58cv`, clé publique `8Pui4ZEqxW2jRVF7h`, payload `{site, name, email, question}` avec le récapitulatif complet de la commande).
3. Le vendeur reçoit la commande par email → envoie les coordonnées de paiement (virement ou message privé) + la facture.
4. Livraison des ZIP et du guide par email dès réception du paiement. **Aucun paiement en ligne automatisé** : c'est assumé et écrit sur la page (« paiement par virement ou message privé »).

Le chatbot (en bas à droite) répond aux questions fréquentes (8 FAQs métier) et capture les leads via EmailJS si la question sort de la FAQ.

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
- Chatbot : accent `#2E6BFF` (couleur principale du site), nom « SkillVault », FAQs 100 % spécifiques au business, EmailJS en fallback.

## Déploiement

Ne rien pousser sur GitHub depuis ce dossier : le parent gère le déploiement (repo `Dembis91-940/skillvault`, GitHub Pages avec `build_type=legacy`).

Pour tester en local :

```bash
cd ~/Documents/livrables/skillvault && python3 -m http.server 8080
# → http://localhost:8080
```
