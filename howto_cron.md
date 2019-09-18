# How To : cron

## Chaîne standard

`<seconds> <minutes> <hours> <day_of_month> <month> <day_of_week> [year]`

## Eléments de l'expression
|Nom|Requis|Valeurs valides|Caractères spéciaux valides|
|:---|:---|:---|:---|
|seconds|yes|`0-59`|`,` `-` `*` `/`|
|minutes|yes|`0-59`|`,` `-` `*` `/`|
|hours|yes|`0-23`|`,` `-` `*` `/`|
|day_of_month|yes|`1-31`|`,` `-` `*` `/` `?` `L` `W`|
|month|yes|`1-12` ou `JAN-DEC`|`,` `-` `*` `/`|
|day_of_week|yes|`1-7` ou `SUN-SAT`|`,` `-` `*` `/` `?` `L` `#`|
|year|no|vide ou `1970-2099`|`,` `-` `*` `/`|

### Signification des caractères spéciaux

* `*` : toutes les valeurs possible du champ
* `?` : pas de valeur spécifique, utilisée pour expliciter quelque chose dans un champ indépendamment d'un second champ
  * Exemple : `0 0 0 10 * ?` signifie "A minuit pile le 10 de chaque mois, peu importe le jour"
* `-` : un intervalle, toutes les valeurs incluant les bornes
  * Exemple : `3-6` dans le champ hours sélectionne les heures 3, 4, 5 et 6
* `,` : pour donner plusieurs valeurs précises
  * Exemple : `3,6` dans le champ hours sélectionne les heures 3 et 6
* `/` : spécifie des incréments, et parcours toutes les valeurs valides trouvées exactement
  * Exemple : `2/14` dans les secondes signifie les secondes 2, 16, 30 et 44
* `L` : last, son utilisation est différente d'un champ à l'autre
  * Champ day_of_month : sélectionne le dernier jour du mois (le 31 en janvier, le 29 en février d'années bisextiles)
  * Champ day_of_week : utilisé tel quel, sélectionne le samedi. Si une valeur le précède, sélectionne le dernier X jour du mois
    * Exemple : `6L` sélectionne le dernier vendredi du mois
* `W` : weekday, sélectionne le jour ouvré le plus proche
  * Exemple : `15W` dans day_of_month sélectionne le jour ouvré le plus proche du 15 du mois
    * Si le 15 est un samedi, le vendredi 14 est sélectionné
    * Si le 15 est un dimanche, le lundi 16 est sélectionné
  * Exemple : `1W` dans day_of_month, si le 1er est un samedi, le lundi 3 est sélectionné
* `#` : utilisé pour sélectionner le nième jour du mois
  * `6#3` dans day_of_week sélectionne le 3ème vendredi du mois

`LW` dans day_of_month : sélectionne le dernier jour ouvré du mois