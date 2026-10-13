# Contribuer

Les contributions sont les bienvenues : coquilles, précisions techniques, nouvelles
questions, corrections d'exemples de commandes.

## Ce qui est attendu

1. **Le document doit rester autonome.** N'ajoutez pas de `\input{...}` ou
   `\include{...}` vers un fichier hors du dépôt : `ssh-indep.tex` doit se compiler seul.
   La CI vérifie ce point.
2. **Le document doit compiler.** Toute PR déclenche la compilation ; si elle échoue,
   la fusion est bloquée.
3. **Une modification par PR, une intention claire.** Décrivez dans la PR ce que vous
   changez et pourquoi (une commande SSH erronée, une explication ambiguë, un cas
   manquant).
4. **Vérifiez techniquement ce que vous avancez.** Les commandes de ce TP sont exécutables :
   testez-les sur deux VMs (un bastion exposé sur 2222, une cible en réseau interne)
   avant de proposer une correction.

## Avant d'ouvrir la PR

```bash
latexmk -pdf -shell-escape ssh-indep.tex
```

Le PDF doit être produit sans erreur. Les avertissements `multiply defined` sur les
labels de questions sont connus et acceptés (effets de `\printanswers` /
`\noprintanswers`).

## Cycle de revue

1. Vous ouvrez une PR depuis une branche de votre fork.
2. La CI compile le document et publie le PDF en artifact : téléchargez-le pour relire
   le rendu, pas seulement le diff.
3. Le check `compile` doit être vert.
4. L'auteur relit, demande des changements éventuellement, puis fusionne.

## Style

- Le document est en français.
- Les blocs de commandes utilisent l'environnement `bashcode` (minted) ; les réponses
  sont dans `\begin{solution}...\end{solution}` pour rester masquables.
- Les questions sont dans l'environnement `questions` avec `\question`.
