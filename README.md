# sshiutb

TP **R202 : SSH --- TIPS & TRICKS** (clés, agent, bastion, tunnels, multiplexage).
Support de cours du module R202 / M2102, IUT Béziers.

Le document est un fichier LaTeX **autonome** : `ssh-indep.tex` contient son propre
préambule, il n'inclut aucun fichier externe et se compile n'importe où.

## Compilation

```bash
latexmk -pdf -shell-escape ssh-indep.tex
```

ou simplement :

```bash
make
```

Le `-shell-escape` est indispensable : le document utilise `minted` (coloration de code
via Pygments), qui appelle `pygmentize` depuis LaTeX.

Dépendances : TeXLive (classe `exam`, `minted2`, `babel` français, `hyperref`,
`microtype`, `xcolor`, `listings`, `enumitem`, `parskip`) et `pygments`.

Sous Debian :

```bash
sudo apt install latexmk texlive-latex-base texlive-latex-recommended \
                 texlive-latex-extra texlive-fonts-recommended \
                 texlive-lang-french python3-pygments
```

## Contribuer

Le dépôt accepte les pull requests. Voir [CONTRIBUTING.md](CONTRIBUTING.md).

**Une PR ne peut être fusionnée que si la compilation LaTeX réussit** : le check
`compile` de la CI GitHub Actions est obligatoire sur la branche `main`. S'il est rouge
(erreur LaTeX, PDF absent ou vide, dépendance externe introduite), le bouton de merge
est bloqué.

## Contenu

| Fichier | Rôle |
|---|---|
| `ssh-indep.tex` | le TP, autonome (préambule inline) |
| `Makefile` | compilation locale |
| `.github/workflows/build.yml` | vérification de compilation sur chaque PR |

## Licence

À préciser par l'auteur (Jean-Marc Pouchoulon). En l'absence de licence déclarée,
tous droits réservés.
