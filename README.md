# FXMP.org Tools — téléchargements

Ce dépôt public distribue les installateurs Windows, les paquets signés pour l’updater Tauri et le manifeste `latest.json` de FXMP.org Tools. Le code source de l’application reste dans le dépôt privé [`fxmp-tools`](https://github.com/Mesrine67/fxmp-tools).

## Télécharger

- [Dernière version stable](https://github.com/Mesrine67/fxmp-tools-releases/releases/latest)
- Le programme d’installation **NSIS** est recommandé pour la plupart des utilisateurs.
- Le paquet **MSI** convient aux installations gérées par Windows ou par un administrateur.

Les versions actuellement distribuées ciblent Windows x64. Une version Linux n’est pas encore publiée. L’application peut aussi télécharger une mise à jour depuis le manifeste public `latest.json`.

## Signaler un problème

Utilisez le [formulaire de signalement](https://github.com/Mesrine67/fxmp-tools-releases/issues/new/choose). Indiquez la version, Windows utilisé et les étapes permettant de reproduire le problème. N’incluez pas de jeton, mot de passe, clé privée ni donnée personnelle dans un rapport public.

## Signatures et intégrité

Les fichiers `.sig` et la propriété `signature` de `latest.json` sont des signatures **Tauri updater**. L’application les vérifie avant d’installer une mise à jour.

Cette signature n’est pas une signature **Windows Authenticode**. Aucun certificat Authenticode public n’étant configuré, Windows peut afficher « Éditeur inconnu » ou un avertissement SmartScreen lors du téléchargement ou du lancement de l’installateur. Ne supprimez pas et ne remplacez pas séparément un installateur ou son fichier `.sig`.

## Contenu de ce dépôt

Les binaires et manifestes sont attachés aux [releases GitHub](https://github.com/Mesrine67/fxmp-tools-releases/releases). GitHub Releases est le canal de distribution prévu pour ces installateurs ; aucun paquet GitHub Packages distinct n’est nécessaire.
