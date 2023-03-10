<h1>URL : <a href="https://apiv1.skylord.fr/">https://apiv1.skylord.fr/</a></h1>

Route : <b>/api/joueur</b>

<b>Récupérer la money d'un joueur</b>
```json
{"GET" : "/money",
"Value" : ["application/json","Access-Control-Allow-Origin"],
"Paramètres" : [
   {"pseudo" : "Le pseudo du joueur"}
],
"Réponse" : [
  {"Format": "{@Money du joueur : STR}"},
  {"Devise": "{@Symbol de la money : INT}"}
]}
```

Exemple : <br>
``https://api.skylord.fr/api/joueur/money?pseudo=VOTE_PSEUDO``


<b>Récupérer le wallet d'un joueur</b>
```json
{"GET" : "/wallet",
"Value" : ["application/json","Access-Control-Allow-Origin"],
"Paramètres" : [
   {"pseudo" : "Le pseudo du joueur"}
],
"Réponse" : [
    {"wallet": [
        {"{@Crypto sous format en USDT : STR}": "{@Nombre de crypto du joueur : FLOAT}"}
    ]}
]}
```

Exemple : <br>
``https://apiv1.skylord.fr/api/joueur/wallet?pseudo=VOTE_PSEUDO``


<b>Récupérer les jobs d'un joueur</b>
```json
{"GET" : "/jobs",
"Value" : ["application/json","Access-Control-Allow-Origin"],
"Paramètres" : [
   {"pseudo" : "Le pseudo du joueur"},
   {"jobs" : "Le Job du joueur (Bucheron, Pecheur, Aventurier, Architecte, Chasseur, Fermier, Mineur, all)"}
],
"Réponse" : [
    {"Resultat": "{@Code de résultat, 404 = Non trouvable, 01 = Trouvable : STR}"},
    {"jobs": [{
        "{@Nom du job : STR}": [{
            "jlevel": "{@Valeur : FLOAT}"
        }, {
            "jmaxlvl": "{@Valeur : FLOAT}"
        }, {
            "jexp": "{@Valeur : FLOAT}"
        }, {
            "jmaxexp": "{@Valeur : FLOAT}"
        }]
    }]
}],
"Erreurs" : [
    {"01" : "Le serveur arrive a récupérer les informations"},
    {"998" : "Le joueur n'est pas en ligne ou n'existe pas"},
    {"404" : "Le job est introuvable"},
]}
```

Exemple : <br>
``https://apiv1.skylord.fr/api/joueur/jobs?pseudo=VOTE_PSEUDO&jobs=all``<br>
``https://apiv1.skylord.fr/api/joueur/jobs?pseudo=VOTE_PSEUDO&jobs=Mineur``
