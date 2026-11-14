# ECC Essentials — Mistral Edition

Sélection essentielle portée depuis [affaan-m/ECC](https://github.com/affaan-m/ECC) (MIT) et adaptée aux agents de code Mistral (Vibe Code, et tout agent qui lit un `AGENTS.md`).

**Contenu** : 41 skills, 10 agents, 10 commandes — soit 66 éléments choisis pour couvrir le cycle `plan → test → implement → review → verify`, sans les hooks ni les scripts runtime d'ECC (spécifiques à Claude Code).

## Utilisation avec un agent Mistral

1. **Déposez ce dossier à la racine de votre projet** (ou dans un sous-dossier référencé).
2. L'agent lit `AGENTS.md` à l'entrée de session : c'est l'index qui décrit quand activer chaque skill, agent ou commande.
3. Invoquez en langage naturel (« review ce PR », « planifie cette feature ») ou par nom (`/plan`, `/code-review`) — l'agent ouvre le fichier correspondant dans `commands/` et suit les instructions.

Aucun plugin, aucun hook, aucune dépendance : tout est en Markdown lisible par n'importe quel modèle.

## Structure

```
AGENTS.md            # Index et règles — lu automatiquement par l'agent
skills/<nom>/SKILL.md  # Workflows détaillés (TDD, sécurité, vérification…)
agents/<nom>.md      # Personas de spécialistes (architecte, reviewer…)
commands/<nom>.md    # Modèles de prompts (/plan, /code-review…)
```

## Ce qui a été adapté

- Suppression des champs frontmatter Claude (`model: sonnet`, etc.).
- `CLAUDE.md` → `AGENTS.md`, chemins `.claude/` → `.agent/`.
- Suppression des dépendances aux scripts runtime ECC (détecteur de package manager, hooks de qualité).
- Références API génériques (ex. Mistral API dans les exemples d'architecture).

## Crédits et licence

Contenu dérivé d'ECC par Affaan Mustafa et contributeurs, licence MIT. Les fichiers conservent leur langue d'origine (anglais) ; ce README et l'usage sont documentés en français.
