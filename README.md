# A propos de mon conf
Ce dépôt contient les choses à savoir concernant mon installation de Linux.

[![Aperçu](screenshot.png)](https://raw.githubusercontent.com//k-ndeye/dotfiles/master/screenshot.png)

## Installer les paquets
La liste des paquets installés sont disponibles dans le fichier package.list. Les paquets AUR sont en fin de liste.
Le dossier custom et doit aller au .oh-my-zsh.


```
cat package.list | xargs yaourt -S --needed --noconfirm
```

## Remapper touches du clavier

Pour remplacer une touche par une autre. Je l'utilise pour remplacer la touche puissance 2 par un back-tick.

```
# On génère le fichier de map
xmodmap -pke > ~/.Xmodmap
# On trouve la clef a remap
xev | awk -F'[ )]+' '/^KeyPress/ { a[NR+2] } NR in a { printf "%-3s %s\n", $5, $8 }'
# On modifie le fichier Xmodmap et on teste avec
xmodmap ~/.Xmodmap
```
