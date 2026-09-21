🛡️ Cerbère Auditeur

Cerbère est un outil d'analyse de sécurité et d'audit de code léger, ultra-rapide et 100% fonctionnel hors-ligne. Il permet d'analyser vos projets logiciels à partir d'un référentiel étendu de 235 points de contrôle, couvrant les vulnérabilités web modernes, les smart contracts, le code système et les agents IA autonomes.

✨ Fonctionnalités clés

- 235 Points de contrôle de sécurité : Couverture complète allant des failles web classiques (OWASP Top 10) aux architectures modernes.
- 100% Local & Hors-ligne : Aucune donnée, aucun fichier ni code source ne quitte votre navigateur lors de l'analyse locale.
- Moteur de détection hybride : 
  - Détection par présence / absence de motifs ou par noms de fichiers.
  - Mode **conditionnel avancé** (ex. détection d'un appel `swap()` sans paramètre `deadline`).
  - Support natif des extensions `.html`, `.js`, `.jsx`, `.ts`, `.tsx`, `.rs`, `.go`, `.sol`, etc.
  - 163 points automatisés sur les 235 du référentiel.
- Traduction FR / EN instantanée : Bascule de l'interface et du référentiel en un clic (en haut à droite) sans perdre le score ou l'état de l'analyse en cours.
- Assistant IA Anthropic (Optionnel) : Intégration directe de Claude pour approfondir l'analyse et poser des questions sur les vulnérabilités détectées.

🔍 Référentiel de Sécurité (235 Points)

Le référentiel intègre les dernières failles identifiées (notamment issues des retours d'expérience *ECC-main*) :

- Frontend Avancé (React / Next.js)** : Sanitisation `dangerouslySetInnerHTML`, validation des URI `javascript:`/`data:`, protections `target="_blank"`, validation Zod sur Server Actions, fuites de secrets `NEXT_PUBLIC_*`, cookies `httpOnly`.
- Rust : Détection de secrets en dur, injections SQL via `format!`, blocs `unsafe` non documentés, absence de `cargo audit`, gestion des erreurs explicites côté client.
- Go : Gestion sécurisée de `os.Getenv`, timeouts réseau explicites via `context.WithTimeout`.
- DeFi & Smart Contracts (Solidity) : Attaques par réentrance (CEI), inflation de vaults, oracles spot manipulables (besoin de TWAP), swaps sans `slippage`/`deadline`, appels `transfer` sans `SafeERC20`, fonctions d'admin sans `onlyOwner`.
- Agents de Trading IA Autonomes : Limites de dépense codées, simulations avant transaction (dry-run), circuit breakers, clés de wallet en dur, protection MEV, validation des prompts contre l'injection.
- Renforts Transverses : En-têtes de sécurité (`Permissions-Policy`, `Referrer-Policy`, CSP sans `unsafe-inline`), validation JWT (audience/issuer), fuite de données dans les logs structurés.

🚀 Installation & Démarrage rapide

Aucune installation complexe, aucun serveur Node.js ni conteneur Docker n'est requis.

1. Télécharger le projet :
   ```bash
   git clone [https://github.com/mikateproduction-wq/Cerbere_auditeur.git](https://github.com/mikateproduction-wq/Cerbere_auditeur.git)
   cd Cerbere_auditeur
Lancer l'application :

Double-cliquez simplement sur le fichier cerbere-auditeur.html pour l'ouvrir dans votre navigateur web (Chrome, Firefox, Edge, Brave, Safari).

🤖 Configuration de l'Assistant IA Anthropic
Cerbère inclut une intégration client-side directe avec l'API Anthropic pour vous aider à corriger les vulnérabilités.

Activation :
Dans l'interface, ouvrez le panneau Assistant IA.

Entrez votre clé API Anthropic (sk-ant-...).

Choisissez votre modèle :

Claude Sonnet (Recommandé : équilibre vitesse/profondeur)

Claude Opus (Pour des analyses très complexes)

Claude Haiku (Pour des réponses ultra-rapides)

Cliquez sur Enregistrer : Un ping de vérification test en direct la validité de la clé auprès de api.anthropic.com.

Note technique : L'appel est effectué en fetch direct via le header anthropic-dangerous-direct-browser-access: true. Vos clés restent stockées uniquement dans votre navigateur (LocalStorage local) et ne sont envoyées à aucun serveur tiers. En cas de perte de connexion, l'outil bascule automatiquement sur le moteur d'analyse local.

📖 Guide d'utilisation
Sélection des fichiers : Glissez-déposez le dossier ou le fichier de votre projet dans la zone d'analyse.

Lancement de l'audit : L'analyse s'exécute instantanément en local.

Consultation du rapport :

Visualisez le score global de sécurité.

Filtrez par catégorie de vulnérabilité ou par niveau de sévérité.

Consultez les preuves de code extraites pour chaque point détecté.

Exportation : Exportez votre rapport au format JSON ou Markdown pour le partager avec vos équipes.

🔒 Confidentialité & Sécurité
Zéro télémétrie : Vos fichiers de code ne sont jamais envoyés sur un serveur distant.

Sécurité des clés : La clé API Anthropic est optionnelle et reste strictement confidentielle au sein de votre navigateur.

Pour toute question, demande de support ou suggestion concernant Cerbère, n'hésitez pas à nous contacter ou à nous rejoindre sur nos canaux différents canaux présents sur sur notre page Github :
