# SAE5.02

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
