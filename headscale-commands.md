# Commandes essentielles pour Headscale

docker exec -it headscale headscale status # Vérifier l’état du serveur Headscale

docker exec -it headscale headscale namespaces list # Lister les utilisateurs (namespaces)


docker exec -it headscale headscale namespaces create mon_utilisateur # Créer un utilisateur (namespace)


docker exec -it headscale headscale namespaces destroy mon_utilisateur # Supprimer un utilisateur (namespace)


# Gestion des clés d’enregistrement

docker exec -it headscale headscale preauthkeys create --expiration 24h mon_utilisateur # Génère une clé d’enregistrement valable **24 heures** pour l’utilisateur `mon_utilisateur`.

docker exec -it headscale headscale preauthkeys list mon_utilisateur # Lister les clés d’enregistrement (pour mon_utilisateur) 


docker exec -it headscale headscale preauthkeys expire clé_ID #Révoque une clé spécifique (remplace `clé_ID` par l’ID affiché dans la liste des clés).

# Gestion des machines

docker exec -it headscale headscale nodes list # Lister les machines enregistrées



docker exec -it headscale headscale nodes approve machine_ID # Approuver une machine manuellement.Approuve une machine nouvellement enregistrée (remplace `machine_ID` par son identifiant).

docker exec -it headscale headscale nodes delete machine_ID # Supprimer une machine de Headscale

# Autres commandes utiles

docker exec -it headscale headscale nodes expire machine_ID # Forcer la reconnexion d’un appareil. Expire l’appareil pour qu’il doive se reconnecter.

docker exec -it headscale headscale version # Vérifier la configuration actuelle de Headscale. Affiche la version de Headscale et vérifie si tout fonctionne correctement.

docker exec -it headscale headscale --help # Afficher l’aide et toutes les commandes disponibles

