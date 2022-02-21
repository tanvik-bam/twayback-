# Twayback : Télécharger des Tweets supprimés de la Wayback Machine, en toute simplicité
<div align="center">
  

[![windows](https://img.shields.io/badge/Télécharger-le%20fichier%20EXE-blue?style=for-the-badge&logo=Microsoft)](https://github.com/Mennaruuk/twayback/releases/download/02%2F18%2F2022/twayback.exe)
[![python](https://img.shields.io/badge/Télécharger-Script%20Python-red?style=for-the-badge&logo=python)](https://github.com/Mennaruuk/twayback/releases/download/02%2F18%2F2022/twayback.zip)
  
  
![screenshot](https://i.imgur.com/5YP0U4l.jpg)

</div>

Trouver et télécharger des Tweets supprimés prend beaucoup de temps. Heureusement, avec cet outil, cela devient facile ! 🎂

Twayback est un portmanteau de *Twitter* et de *Wayback Machine*. Entrez votre nom d'utilisateur Twitter et laissez Twayback faire le reste !

## Caractéristiques
 - Il peut télécharger une partie ou la totalité des Tweets archivés et supprimés d'un utilisateur.
 - Il vous permet d'extraire le texte des Tweets vers un fichier texte (oui, même les retweets entre guillemets !)
 - Il a la capacité de faire des captures d'écran de Tweets supprimés.
 - Il permet de personnaliser la plage de temps pour restreindre la recherche des Tweets supprimés archivés entre deux dates.
 - Il fait la différence entre les comptes actifs, suspendus, ou qui n'existent pas/plus.
 - Il vous permet de savoir si les Tweets archivés d'une poignée cible ont été exclus de la Wayback Machine.

## Mode d'emploi
>    twayback -u nom d'utilisateur [OPTIONS]
    
    -u, --username                                        Spécifiez le nom d'utilisateur Twitter
    
    -from, --fromdate                                     Recherche restreinte de Tweets supprimés
                                                          *archivés* à partir de cette date.
                                                          (Il peut être combiné avec -to)
                                                          (format YYYY-MM-DD or YYYY/MM/DD
                                                          or YYYYMMDD, Ça n'a pas d'importance)
                                            
    -to, --todate                                         Recherche restreinte de Tweets supprimés
                                                          *archivés* à cette date et avant celle-ci.
                                                          (Il peut être combiné avec -from)
                                                          (format YYYY-MM-DD or YYYY/MM/DD
                                                          or YYYYMMDD, Ça n'a pas d'importance)
    Exemples:
    twayback -u taylorswift13                             Il télécharge tous les Tweets supprimés
                                                          de @taylorswift13.
    
    twayback -u jack -from 2022-01-05                     Il télécharge tous les Tweets supprimés
                                                          de @jack *archivés* depuis le 5 janvier,
                                                          2022 jusqu'à maintenant.
    
    twayback -u drake -to 2022/02/09                      Il télécharge tous les Tweets supprimés
                                                          de @drake *archivés* depuis le début
                                                          jusqu'au 9 février 2022.
    
    twayback -u EA -from 2020-08-30 -to 2020-09-15        Il télécharge tous les Tweets supprimés
                                                          de @EA *archivés* entre le 30 août 2020
                                                          et le 15 septembre 2020.

## Installation
### Pour Windows uniquement
 1. Téléchargez le dernier fichier EXE.
 2. Lancez l'invite de commande (Command Prompt) dans le répertoire du fichier EXE.
 3. Exécutez la commande `twayback -u USERNAME` (Remplacez `USERNAME` par votre identifiant cible).

### Pour Windows, Linux et macOS
 1. Téléchargez le dernier fichier ZIP du script Python.
 2. Extrayez le fichier ZIP dans un répertoire de votre choix.
 3. Ouvrez le terminal dans ce répertoire.
 4. Exécutez la commande `pip install -r requirements.txt`.
 5. Exécutez la commande `twayback.py -u USERNAME` (Remplacez `USERNAME` par votre identifiant cible).


Pour plus d'informations, consultez la section [Usage](#usage) ci-dessus.

## Captures d'écran
Les captures d'écran sont réalisées à l'aide de Selenium. Pour réussir à faire des captures d'écran, veuillez suivre les étapes suivantes :

 1. Assurez-vous que vous avez installé Google Chrome.
    - Firefox fonctionne, mais vous devez modifier le script pour remplacer Chrome par Firefox. De plus, Firefox n'est pas génial avec les captures d'écran.
 2. Notez votre version de Chrome.
 3. Allez sur [cette page] (https://chromedriver.chromium.org/downloads) et téléchargez le pilote Chrome approprié pour votre version de Chrome.
 4. Placez le pilote Chrome dans votre répertoire d'installation Python ou ajoutez-le à PATH.
    - Ajouter aux tutoriels PATH : [Windows](https://www.architectryan.com/2018/03/17/add-to-the-path-on-windows-10/), [Linux](https://itsfoss.com/add-directory-to-path-linux/), [macOS](https://www.architectryan.com/2012/10/02/add-to-the-path-on-mac-os-x-mountain-lion/).



## Points à garder à l'esprit
 - La qualité des fichiers HTML dépend de la façon dont la Wayback Machine les a enregistrés. Certains sont meilleurs que d'autres.
 - Cet outil est idéal pour le texte. Vous aurez peut-être un peu de chance avec les photos. Vous ne pouvez pas télécharger de vidéos.
 - Par définition, si un compte est suspendu ou n'existe plus, tous ses Tweets sont considérés comme supprimés.
 - La plage de dates personnalisée ne concerne pas la date à laquelle les Tweets ont été faits, mais plutôt la date à laquelle ils ont été _archivés_. Par exemple, un Tweet de 2011 peut avoir été archivé aujourd'hui.
