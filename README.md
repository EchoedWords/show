# **SimcompanieCommunity**

# Readme

# Sommaire

- [API](#api)
    - [Gestionnaire des Discord communautaires](#gestionnaire-des-discord-communautaires)

# API

## Gestionnaire des Discord communautaires

### GET /DiscordCommunity/get
> Renvoie les groupes Discord ciblés.

Authentification : ouverte

Paramètres de requête :
- **firstsector**
    - Cible les serveurs avec comme secteur principal les identifiants spécifiés.
    - `=SECTEUR&` || exemple `=0&12&14`
- **?secondsector**
    - Cible les serveurs avec comme second secteur les identifiants spécifiés.
    - `=SECTEUR&` || exemple `=0&12&14`
- **langue**
    - Cible les serveurs selon les langues spécifiées.
    - `=LANGUE&` || exemple `=FR&RU`
- **minmember**
    - Cible les serveurs avec un nombre minimum de membres.
    - `=NUMBER` || exemple `=200`
- **maxMembres**
    - Cible les serveurs avec un nombre maximum de membres.
    - `=NUMBER` || exemple `=500`
- **?nom**
    - Cible les serveurs avec un nom correspondant.
    - `=NOM` || exemple `=Groupe Total`
- **?scoreMin**
    - Cible les serveurs avec un score minimum.
    - `=SCORE` || exemple `=4`
- **?partenaire**
    - Cible les serveurs partenaires.
    - `=BOOLÉEN` || exemple `=true`

Réponse :
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
> Enregistre un nouveau groupe Discord.

Authentification : ouverte

JSON :
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

Réponse :
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
