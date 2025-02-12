# SAE5.02

# Sur la machine virtuelle ubuntu :

# Installer la commande git clone
apt install git

# Cloner le dépôt
git clone https://github.com/Vialle-Joris/SAE5.02

# Naviguer dans le dépôt
cd SAE5.02

# Modifier les droits pour éxéxuter le run.sh
chmod +x run.sh

# Installer les dépendances nécessaires:
./run.sh

# Lancer playbook Minecraft
ansible-playbook deploy_minecraft_server.yml --ask-become-pass

# Lancer le monitoring
ansible-playbook deploy_monitoring.yml

# Accéder aux logs pour vérifier le bon démarrage
docker logs -f minecraft_server

# Voir les graphiques sur Grafana
http://<ip>:3000

# Sur la machine hôte pour jouer sur le serveur :
Installer TLauncher
Lancer TLauncher avec la version Forge 1.20.1
Une fois le jeu lancé, cliquer sur "Multijoueurs"
Puis se connecter avec l'adresse IP resnsigné lors du lancement du playbook install et rajouter le port 25565 (exemple: 192.168.1.1:25565)
