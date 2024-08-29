# Homes Plugin 🏠


## Features 🛠️

---
- Configurable: Commande, Config, Messages, etc...
- Mise à jour: Plugin mise à jour régulièrement.

## Commande 📜

---

| Commande   | Description                            | Usage               | Alias   | Permission               |
|------------|----------------------------------------|---------------------|---------|--------------------------|
| /sethome   | Définir un home                        | /sethome <nom>      | /sh     | synopsie.homes.sethome   |
| /delhome   | Supprimer un home                      | /delhome <nom>      | /dh     | synopsie.homes.delhome   |
| /home      | Téléportation à un home                | /home <nom>         | /h      | synopsie.homes.home      |
| /adminhome | Permet d'obtenir les homes d'un joueur | /adminhome [joueur] | /adminh | synopsie.homes.adminhome |

## Configuration 📝

---
```yaml
# Config for Homes Plugin

commands:
  sethome:
    name: sethome
    description: Définir un home
    usage: /sethome <nom>
    aliases:
      - sh
    permission:
      name: synopsie.homes.sethome
      default: user
  delhome:
    name: delhome
    description: Supprimer un home
    usage: /delhome <nom>
    aliases:
      - dh
    permission:
      name: synopsie.homes.delhome
      default: user
  home:
    name: home
    description: Téléportation à un home
    usage: /home <nom>
    aliases:
      - h
    permission:
      name: synopsie.homes.home
      default: user
  adminhome:
    name: adminhome
    description: Permet d'obtenir les homes d'un joueur
    usage: /adminhome [joueur]
    aliases:
      - adminh
    permission:
      name: synopsie.homes.adminhome
      default: operator


#########
# operator
# console
# user
#########
permissions.homes:
  3:
    permission: synopsie.homes.3
    default: user
  4:
    permission: synopsie.homes.4
    default: operator
max.home.limit: 15

#Activer cette option permet d'envoyer des logs lorsque le joueur défini un home,
#supprime un home ou alors lors de l'utilisation de l'adminhome.
# Attention les premiers temps, si beaucoup de joueurs poses des homes en supprime ou autre cela peut bloquer le webhook.
logs:
  sethome: true
  delhome: true
  adminhome: true
  home: true # Activer cette option permet d'envoyer des logs lors un joueur tente de se téléporter à un home est que la téléportation a échoué.
logs.webhook: "https://discord.com/api/webhooks/1278019510330462258/uvjqx5KlNYip000OTz8c-0yQrKbMRCgiBukqoAj9jk1DU6TKYrRZQY61VTUXMwMlF5oR"

use.cooldown.for.tp: true # Activer cette option permet d'ajouter un cooldown pour la commande /home <nom>
cooldown.tp: 5 # Temps en secondes
message.type: popup # popup, actionbar, chat, tip, title ou NULL pour désactiver les messages
message.cooldown: "Téléportation dans §e%time% secondes§f."
permission_bypass:
  name: synopsie.cooldown.bypass
  default: console

use.sound: true # Le son s'activera lors du cooldown de la téléportation un home.
sound.name: mob.endermen.portal
sound.volume: 100

homes.max.limit: "§cVous avez atteint le nombre maximum de homes."
homes.already.exists: "§cUn home avec ce nom existe déjà."
home.set: "§aHome §e%name% §adéfini avec succès."
home.not_found: "§cHome §e%home% §cintrouvable."
home.delete: "§aHome §e%home% §asupprimé avec succès."
home.list.header: "§fVoici la liste de vos homes (§e%count%§f): \n%homes%"
home.list.format: "§6#%number% §e%name% §7- §e%world% §f\n"
home.list.empty: "§cVous n'avez aucun home."
home.list.footer: "§f§oIl vous reste §e%count% §fhome(s) à définir."
home.player.not_found: "§cJoueur introuvable."
home.teleporter: "§aVous avez été téléporté au home §e%home%§a."

adminhome.form.title: "§eHomes"
adminhome.form.content: "§fSélectionnez un joueur pour voir ses homes."
adminhome.form.button: "§e%player%"
adminhome.form.content.home: "§fChoisissez un home de §e%player%§f."
adminhome.form.button.homes: "§e%home% \n§8%level"
adminhome.form.content.informations: "§fInformations sur le home §e%home%§f: \n Monde: §e%level% §f\n X: §e%x% §f\n Y: §e%y% §f\n Z: §e%z% §f\n Yaw: §e%yaw% §f\n Pitch: §e%pitch% §f\n Créé le: §e%date%"
adminhome.form.button.teleport: "§aTéléporter"
adminhome.form.button.delete: "§cSupprimer"
adminhome.form.button.back: "§8Retour"
```

## Support 📜

---
Pour des questions, ou une demande d'aide, rendez-vous sur notre [discord](https://discorD.gg/JkpT7BJPXR)
