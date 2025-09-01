# ComputerCraft Automated Reactor Controller
# Tutoriel (copier-coller dans un README) — Big Reactors + ComputerCraft (1.7.10)
## Patch Pastebin ➜ Installer le script (FurRg6Ec) ➜ Lancer automatiquement au démarrage


Easily automate your Bigger/Extreme reactor with a pretty graphical UI. <br />

## Features
  <bl>
  <li>One line installation</li>
  <li>Modular displays to customize information shown</li>
  <li>Automatically control your reactor with optional configuration</li>
  <li>Tested on Extreme and Bigger Reactors</li>
  </bl>

### 1) Corriger le programme `pastebin` (URL HTTPS correcte)
#### Dans l’ordinateur ComputerCraft, tape d’abord :
copy rom/programs/http/pastebin pastebin
edit pastebin
#### Quand l’éditeur s’ouvre, remplace le contenu 
"http://pastebin.com/raw.php?i"..textutils.urlEncode( paste )

#### par ce qui suit, puis Ctrl+S et Ctrl+E pour sauvegarder/quitter :
"https://pastebin.com/raw/"..textutils.urlEncode( paste )

### 2) Installer le script cible (ex. code Pastebin : FurRg6Ec)
#### Méthode recommandée : le télécharger localement sous le nom `rc`, puis l’exécuter
pastebin get FurRg6Ec rc
rc

### 3) Démarrage automatique à chaque boot (startup)
#### Crée le fichier `startup` qui lance `rc` automatiquement :
edit startup
#### Colle la ligne suivante, puis Ctrl+S / Ctrl+E :
shell.run("rc")

### 4) (Option) Variante “toujours depuis Pastebin” au démarrage (moins fiable hors-ligne)
#### À mettre à la place de la ligne précédente dans `startup` si tu préfères :
shell.run("pastebin run FurRg6Ec")

### 5) Raccourcis utiles
#### Arrêter un script en boucle :  Ctrl + T
#### Redémarrer l’ordinateur :     Ctrl + R

### 6) Vérification rapide que le réacteur est bien vu
lua
print( peripheral.find("BigReactors-Reactor") and "OK: réacteur détecté" or "KO: aucun réacteur" )





## Installation
  <ol>
    <li>
      Connect an Advanced Computer directly to a reactor or via wired modem network
    </li>
    <li>
      Optionally, you can connect a monitor. Connect it directly to the computer or via wired modem network
    </li>
    <li>
       Make sure that all modems are activated
    </li>
    <li>
      Run the following command in the Computer: <br />
      <code>pastebin run FurRg6Ec</code>
    </li>
  </ol>




## Configuration
  To configure the program, use monitors. Once it is configured,
  the monitors are no longer necessary but can still display information. <br /><br />
  The minimum monitor size is 2x2. Use a height of 4 to have access to all settings. <br />
  If there is not enough space to display a graph you will be unable to enable it.
## Screenshots:
![2021-05-24_20 29 15](https://user-images.githubusercontent.com/18647702/119422445-19adba00-bccf-11eb-95db-68c728e72555.png)
![2021-05-24_20 29 36](https://user-images.githubusercontent.com/18647702/119422446-1a465080-bccf-11eb-85c4-6e60e31b2869.png)
![2021-05-24_20 30 04](https://user-images.githubusercontent.com/18647702/119422448-1a465080-bccf-11eb-8c5d-f479c263da62.png)
![2021-05-24_20 30 35](https://user-images.githubusercontent.com/18647702/119422461-25997c00-bccf-11eb-9be3-9b2ad6b355bf.png)
![2021-05-24_20 30 13](https://user-images.githubusercontent.com/18647702/119422464-27fbd600-bccf-11eb-8a38-61909bb6aae8.png)

## Known Issues
- If the reactor has a very large max RF/t generation capacity but a low RF/t drain, it may oscillate around the target buffer. This is a limitation of the specific PID controller implementation used.
  - Workaround: increase the range of the buffer, YMMV
- Sometimes, the RF/t Drain statistic will fluctuate wildly. I don't think this is caused by the program, but in singleplayer, the issue seems to start when directly interacting with the reactor UI, and seems to get better by relogging.

## Future Plans
- Multi monitor support
- External power bank support
  
## Update History
  <b>05/29/2025:</b> Update future turbine support plans <p>
  <b>12/14/2024:</b> Fix issue with Pastebin API, and some major internal code refactors <p>
  <b>12/04/2023:</b> Changed Control rod insertion logic to use a PID controller <p>
  <b>5/24/2021:</b> Added support for Extreme Reactors and Big Reactors <p>
  <b>5/24/2021:</b> Started tracking update history / Uploaded to GitHub <p>

## Attributions
<ul>
  <li><b>Krakaen: </b><br />
    Gui design influenced by Krakaen's Reactor Program <br />
    http://www.computercraft.info/forums2/index.php?/topic/26019-big-reactors-automatic-control-program/ </li>
  <li><b>Lyqyd: </b><br />
    Buttons use Touchpoint API, though it was slightly modified <br />
    http://www.computercraft.info/forums2/index.php?/topic/14784-touchpoint-api/ </li>
 </ul>
