# La répartition des musées Français dans les différentes Régions de France.
#JEUX DE DONNEES

#OPENREFINE
``` json
[
  {
    "op": "core/mass-edit",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "columnName": "Lieu",
    "expression": "value",
    "edits": [
      {
        "from": [],
        "fromBlank": true,
        "fromError": false,
        "to": "Inconnue"
      }
    ],
    "description": "Mass edit cells in column Lieu"
  },
  {
    "op": "core/column-removal",
    "columnName": "Téléphone",
    "description": "Remove column Téléphone"
  },
  {
    "op": "core/column-removal",
    "columnName": "URL",
    "description": "Remove column URL"
  },
  {
    "op": "core/column-removal",
    "columnName": "REF_Deps",
    "description": "Remove column REF_Deps"
  },
  {
    "op": "core/mass-edit",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "columnName": "Code Postal",
    "expression": "value",
    "edits": [
      {
        "from": [],
        "fromBlank": true,
        "fromError": false,
        "to": "81000"
      }
    ],
    "description": "Mass edit cells in column Code Postal"
  },
  {
    "op": "core/mass-edit",
    "engineConfig": {
      "facets": [],
      "mode": "row-based"
    },
    "columnName": "Adresse",
    "expression": "value",
    "edits": [
      {
        "from": [],
        "fromBlank": true,
        "fromError": false,
        "to": "Inconnue"
      }
    ],
    "description": "Mass edit cells in column Adresse"
  },
  {
    "op": "core/column-removal",
    "columnName": "Lieu",
    "description": "Remove column Lieu"
  }
]

```


#données



<iframe frameborder="0" width="800" height="600" src="https://data.opendatasoft.com/map/embed/g__/?&static=false&scrollWheelZoom=false"></iframe>


#La réaprtion des musées Francais dans les différentes Régions de France.
Après avoir fait une représentation des données sous forme de carte, nous avons fait une représenation graphique sous forme de colonne sur OPENDATASOFT afin de connaitre le nombre de musées exacts dans chaque région avec toutes les infiormation nécessaires dès que mets le souris sur une bande selon la couleur et la région.

<iframe src="https://data.opendatasoft.com/chart/embed/g__/?&static=false&datasetcard=false" width="800" height="600" frameborder="0"></iframe>


##Wikidata
###REQUETE
```sparql
#defaultView:Timeline
SELECT  ?item ?name ?coord  ?pic ?date   
WHERE
{

 ?item wdt:P31 wd:Q33506 .
   ?item wdt:P17 wd:Q142 .
 ?item wdt:P625 ?coord .
 #?item p:P625 ?coordinate .
 #?coordinate psv:P625 ?coordinate_node .
  # ?coordinate wdt:P131 ?region.
# ?coordinate_node wikibase:geoLatitude ?lat .
# ?coordinate_node wikibase:geoLongitude ?lon .
 OPTIONAL {?item wdt:P18 ?pic. }
  
  OPTIONAL {  ?item wdt:P571 ?date.}
  
 SERVICE wikibase:label {bd:serviceParam wikibase:language "fr" .
 ?item rdfs:label ?name
 }
}
```

##Resulats 
defaultView:Timeline
<iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3ATimeline%0ASELECT%20%20%3Fitem%20%3Fname%20%3Fcoord%20%20%3Fpic%20%3Fdate%20%20%20%0AWHERE%0A%7B%0A%0A%20%3Fitem%20wdt%3AP31%20wd%3AQ33506%20.%0A%20%20%20%3Fitem%20wdt%3AP17%20wd%3AQ142%20.%0A%20%3Fitem%20wdt%3AP625%20%3Fcoord%20.%0A%20%23%3Fitem%20p%3AP625%20%3Fcoordinate%20.%0A%20%23%3Fcoordinate%20psv%3AP625%20%3Fcoordinate_node%20.%0A%20%20%23%20%3Fcoordinate%20wdt%3AP131%20%3Fregion.%0A%23%20%3Fcoordinate_node%20wikibase%3AgeoLatitude%20%3Flat%20.%0A%23%20%3Fcoordinate_node%20wikibase%3AgeoLongitude%20%3Flon%20.%0A%20OPTIONAL%20%7B%3Fitem%20wdt%3AP18%20%3Fpic.%20%7D%0A%20%20%0A%20%20OPTIONAL%20%7B%20%20%3Fitem%20wdt%3AP571%20%3Fdate.%7D%0A%20%20%0A%20SERVICE%20wikibase%3Alabel%20%7Bbd%3AserviceParam%20wikibase%3Alanguage%20%22fr%22%20.%0A%20%3Fitem%20rdfs%3Alabel%20%3Fname%0A%20%7D%0A%7D%0A" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" ></iframe>
