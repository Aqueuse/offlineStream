# offlineStream

A simple twitch game

## bot twitch :
    [twitch functions]
    scopes needed :
    * delete message : moderator:manage:banned_users,
    * timeout : moderator:manage:banned_users,
    * send mp : whispers:edit

    function timeout("user-id", timeoutDuration)
    function mpRules("user-id")

    [audio/obs functions]
    https://crates.io/crates/obws
    function sceneSwitch("scene name")
    function glitchWord()
    function playSound("name")
    function stopStream()

    [json functions]
    function playerExist("user-id")
    function addPlayer("user-id")
    function editPlayerRule("user-id", "rule")
    function increasePlayerTimeout("user-id")
       look the player timeout in json
       increase it
       save value in json


## json conf file :
{
	"word" : "",
	"players" : [
		{
			"user-id" : "",
			"rule" : "",
			"timeout" : ""
		},
		{
			"user-id" : "",
			"rule" : "",
			"timeout" : ""
		}
    ]
}

# AUDIO/VIDEO

* son :
    - bruit rose compressé
    - les interactions déclenchent des instruments inquiétants

* vidéo :
    - scène 1 : écran TV + boucle video bruit VHS
    - scène 2 : écran TV  + MIRE SVG éditable 


# RULES

* but du jeu : trouver le mot du stream

si tu écris le bon mot :
* tu peux écrire UN message dans le chat
* tu peux relancer le jeu :
        * avec un nouveau mot aléatoire
        * mais tu ne pas peux rejouer
        * mais tu peux ban UNE personne pendant 12 heures
        * tu peux mettre fin au stream quand tu veux


si tu écris le mauvais mot : 
* le message est supprimé
* première fois :
     ça déclenche un mire avec une musique pendant 4 secondes
     (le mot peut apparaitre de façon furtive ou pas)
* chaque fois : tu augmente ta durée de ban
  (incrémental, jusqu'à 12 heures)

## commands

si tu écris un message avec un point d'exclamation au début :
    * le message est supprimé
    * chaque fois : tu augmente ta durée de ban
        (incrémental, jusqu'à 12 heures)
    * ça t'envoie un mp avec les règles