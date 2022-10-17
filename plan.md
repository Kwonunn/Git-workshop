# Git workshop

## Structuur

1. Introductie
   1. Uitleg wat git is
      1. Versiegeschiedenis
      2. Code remote opslaan
      3. Samenwerken
2. Git installeren
   1. Installing
      1. Git for Windows: `https://gitforwindows.org/`
      2. Git op Linux: `apt install git`
      3. Git op Mac: Command line dev tools
   2. Basic config
      1. Naam instellen: `git config --global user.name [git_username]`
      2. Email instellen: `git config --global user.email [git_email]`
3. Lokaal git gebruiken
   1. Repository is een map waarin alles wordt bijgehouden
   2. Initialiseren met `git init`
   3. Status bekijken met `git status`
   4. Een commit is een verandering in een aantal bestanden met een naam
   5. Je kan kiezen welke changes je wil committen. 
   6. `git add [files]` om bestanden toe te voegen
   7. `git add .` om alles toe te voegen
   8. `git commit` om een commit te maken
   9. `git commit -m "Berichtje"` om de message direct toe te voegen
   10. `git log` om commit geschiedenis te bekijken
   11. van boven naar beneden informatie over alle commits
   12. Commits zijn alleen de veranderingen
       1.  Eerste keer een bestand maken is van niets naar het bestand gaan
       2.  Tweede commit is alleen de veranderingen in het bestand, niet de hele nieuwe versie
4. Remote repositories
   1. Met git kan je makkelijk je code naar een server sturen, en het daar vandaan ophalen
   2. Git laat je heel veel soorten remotes toevoegen
   3. Git server providers komen het meest voor
      1. GitHub, GitLab, Bitbucket, Azure Repos
      2. Windesheim Gitlab is er, maar is heel stom
   4. GitHub account aanmaken
      1. `https://github.com/signup`
      2. Key genereren
         1. Public/private key pairs zijn de standaard manier van encryptie voor git verkeer
         2. op eigen computer in command line `ssh-keygen` uitvoeren
            1. Standaard key locatie
            2. Passphrase hoeft niet, mag wel
         3. Keys bekijken in `~/.ssh`
         5. Key toevoegen aan GitHub
         6. Ga naar GitHub settings > SSH and GPG keys
         7. New SSH key
         8. Title > iets leuks
         9. Key type > Auth key
         10. Key > De public key
            1. De inhoud van het `id_rsa.pub` tekstbestand
   5. Lokale repository naar GitHub sturen
      1. Eerst GitHub remote aanmaken
         1. GitHub Dash > Create repository
         2. Naam > naam van het project
         3. Visibility
            1. Private, alleen voor jou en mensen die je specifiek toevoegt
            2. Public, voor de hele wereld te vinden
         4. Niet initializen
         5. Repository SSH url kopieeren
      2. Nieuwe remote toevoegen aan repo
         1. `git remote add origin [repo_url]`
         2. origin is de standaard naam voor de remote als je er maar een hebt
         3. je kan meerdere remotes toevoegen
      3. Code naar de remote sturen
         1. Eerste keer `git push -u origin main`
         2. Dit stelt in dat de branch `main` standaard naar `origin` gaat
         3. Daarna `git push` om naar de standaard remote te sturen
      4. Kijk op github naar de gepushete code
   6. Code uit een remote ophalen
      1. `git clone` om een remote repository op te halen
      2. Ga naar een andere map dan waar het repository al staat
      3. `git clone [repo_url]` om in de map het repository te clonen
      4. Dit stelt standaard de remote in als de origin remote, dus kan direct `git push` gebruiken
5. Samenwerken met git
   1. Kies een buddy om remotes mee uit te proberen
   2. Voeg elkaar's GitHub accounts toe aan elkaars repositories
      1. Repository Pagina > Settings > Collaborators
      2. Voeg elkaar bij username toe 
      3. In sommige Git Remote services moet je rechten toevoegen aan collaborators
   3. Clone het repository van de ander
   4. Branches
      1. Commits in git zitten op een bepaalde branch
      2. Standaard wordt een repo aangemaakt met een `main` of `master` branch.
      3. Je kan zelf branches maken om commits te organiseren
      4. Kan voor features, bugs, fixes, whatever
      5. In grotere teams worden branches gebruikt om workflows te doen
   5. Maak een nieuwe branch aan in het geclonede repository met `git branch [branch name]`
   6. Wissel heen en weer tussen branches met `git checkout [branch name]`
   7. Verander iets op de nieuwe branch, of maak een nieuw bestand aan
   8. Commit de changes
   9. Stuur de branch met de commits naar de remote met `git push -u origin [branch name]`
   10. Haal nu de branch van de ander op
       1.  Ververs eerst de lijst met remote branches met `git fetch`
       2.  Wissel naar de nieuwe branch met `git checkout [nieuwe branch]`
       3.  Zie dat de changes van de ander nu in de bestanden staan
   11. Ten slotte, mergen.
       1.  Om changes uit een branch terug te stoppen in bijvoorbeeld de main branch, gebruiken we merge
       2.  Wissel naar de branch waar de changes uiteindelijk naartoe moeten met `git checkout`
       3.  Haal nu de changes uit de andere branch binnen met `git merge [andere branch]`
       4.  Git doet hierbij zijn best om alle bestanden samen te voegen
       5.  Als dit niet lukt, omdat er conflicterende changes zijn, zal er een merge conflict ontstaan
       6.  Je moet dan zelf de bestanden openen en de goede changes samenvoegen
       7.  Als dit klaar is gebruik je `git add .` en `git commit` om de merge te committen in een speciale "merge commit"
       8.  Deze heeft een standaard bericht, laat dit zo staan
6.  Laatste punten
    1.  Git is in basis de command line tool, maar meestal hoef je deze niet te gebruiken
        1.  Er zijn specifieke programma's die het proces vergemakkelijken
        2.  De meeste IDE's hebben ingebouwde git tools
        3.  Bijvoorbeeld PHPStorm 
    2.  Als er iets niet lukt, Google kan vaak helpen met git problemen
        1.  Zoek in het engels, StackOverflow heeft vaak goede antwoorden
        2.  Als alles helemaal in de soep loopt, repo verwijderen en opnieuw clonen van de remote
