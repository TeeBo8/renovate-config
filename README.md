# renovate-config

Configuration Renovate commune à tous les repos TeeBo8 (`default.json`). Chaque repo l'utilise avec :

```json
{ "extends": ["local>TeeBo8/renovate-config"] }
```

## Règles (option a, décidée le 2026-11-20)

| Mise à jour de Next.js | Ce qui se passe |
|---|---|
| Correctif (16.4.2 → 16.4.6) | PR ouverte, **fusionnée toute seule** si la preview Vercel est verte, sur tous les repos (clients compris) |
| Mineure (16.4 → 16.5) | PR ouverte, fusion à la main |
| Majeure (16 → 17) | PR ouverte, fusion à la main (gros changements : commande `/maj-next` depuis teebostudio) |

- Next.js, `eslint-config-next` et `@next/*` partent dans une seule PR par projet.
- Une version n'est proposée qu'après 1 jour de publication (protection contre une version piégée ou retirée).
- Les autres dépendances ne sont pas suivies pour l'instant (`enabled: false`) : pour en ajouter, ajouter une règle ici, ça vaut pour tous les repos.
- Chaque repo a un ticket « Dependency Dashboard » qui liste ce qui est en attente.

Pour changer une règle : modifier `default.json` ici, c'est tout.
