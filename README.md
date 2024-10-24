# **SimcompanieCommunity**

# readme

# Sommaire

 - [API](#api)
    - [Gestionaire des discord communautere](#Gestionaire-des-discord-communautere)
 
# api

## Gestionaire des discord communautere

### GET /DiscordCommunity/get
> Renvois les group discord ciblé

Authentification : open

Query :
- **firstsector**
    - Cible les serveur avec comme principal secteur ...
    - `=SECTEUR&` || exemple `=0&12&14`
- **?secondesector**
    - Cible les serveur avec comme seconde secteur ...
    - `=SECTEUR&` || exemple `=0&12&14`
- **langue**
    - Cible les langue souhaité
    - `=LANGUE&` || exemple `=FR&RU`
- **minmember**
    - Cible les serveur avec un minimum de membre
    - `=NUMBER` || exemple `=200`
- **maxmember**
    - Cible les serveur avec un maximum de membre
    - `=NUMBER` || exemple `=500`
- **?name**
    - Cible les serveur avec le nom
    - `=NOM` || exemple `=group total`
- **?minscore**
    - Cible les serveur avec un minimum de score
    - `=SCORE` || exemple `=4`
 - **?partner**
    - Cible les serveur partener
    - `=BOOLEAN` || exemple `=true`



Reponce :
```json
  [
  {
    "id": 84246687,
    "langue": ["FR", "RU"],
    "member": 302,
    "first_sector": [0, 98, 112],
    "second_sector": [5, 78],
    "score": 7.9,
    "partner": true
  }
]
```

### POST /DiscordCommunity/new
> Enregistre un nouveaux group discord

Authentification : ?

Json : 
```json
{
    auth : 
    values : {
        name : "Total Group", //unique, notnull
        url : "https://", //unique, notnull
        logo : "https://", 
        ?namechef : "toako",
        firstsector : [0, 12],
        ?secondesector : [5]
    }
}
```


Reponce :
```json
  [
    {
      "id": 84246687,
      "langue": ["FR", "RU"],
      "member": 302,
      "first_sector": [0, 98, 112],
      "second_sector": [5, 78],
      "score": 7.9,
      "partner": true
    }
  ]
```
