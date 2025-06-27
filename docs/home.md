# Informatie Visualisatie

Dennis Chan 15833526 

Stanley Si Lin Wu 15417190 

Michael Dong 15804232 

Sander Neele 15857719 

Groep nummer: B1 (#1) 


## Inleiding

Wat bepaalt het succes van een film of serie? Nu streamingdiensten zoals Netflix, HBO en Disney Plus onze kijkgewoontes beïnvloeden, wordt het steeds belangrijker om te begrijpen waarom bepaalde titels populairder zijn dan andere. Het platform IMDb verzamelt enorme hoeveelheden publiek data, waarmee we kunnen analyseren wat het publiek waardeert. 

In dit project analyseren we gegevens van de best beoordeelde films en series op IMDb. We gebruiken twee datasets met elk de top 1000 best beoordeelde films of series. Via interactieve visualisaties onderzoeken we hoe factoren zoals genre en populariteit samenhangen met de waardering van het publiek. We benaderen dit onderwerp vanuit twee invalshoeken. Enerzijds kijken we naar de groeiende voorkeur voor series: ze bieden meer diepgang, langere verhaallijnen en passen beter bij het kijkgedrag van de moderne gebruiker.

## Dataset and preprocessing
We gebruiken twee vergelijkbare IMDb-datasets van Kaggle: één met de top 1000 films en één met de top 1000 series. Beide bevatten informatie over genres, releasejaar, stemmen en beoordelingen. Dankzij de identieke structuur zijn ze goed te vergelijken en geschikt om trends en succesfactoren binnen de populaire cultuur te analyseren.


omschrijving van de gebruikte variabelen
Dataset 1 en 2:
Title: Titel van de film of serie
Genres: De genres behorend bij de film of serie
averageRating: de gemiddelde rating
numVotes: Aantal stemmen op een film of serie
releaseYear: verschijningsjaar



## Geen cleaning

We hebben geen cleaning gebruikt, want er waren geen ontbrekende of inconsistente waarden die cleaning vereist. Daarnaast bevat de dataset ook maar 6 variables, wat cleaning overbodig maakt.



## Aggregation 

Voor het samenvoegen van de films en series hadden we beide datasets samengevoegd tot pd.concat(), zodat alle films en series in één tabel staan. We hebben de label ‘serie’ voor series gegeven en voor films de label ‘film’ gegeven. 

Bij de eerste aggregatie (combined_votes_by_year.csv) hebben we voor numvotes ‘sum’ gebruikt. Hierbij telt het totale aantal stemmen per jaar op van zowel films als series. Ook hebben we gebruik gemaakt van ‘lambda x: “ | “.join(x) ‘. DIt combineert alle titels per jaar met een | als scheidingsteken. De groepering is op release Year gebaseerd. HIerdoor konden we films en series samen analyseren
Bij de tweede aggregatie (combined_stats_by_year.csv) is de groepering ook gebaseerd op release Year. De variabeles: averagerating, numvotes, title en type werden hierbij gebruikt. Hierdoor konden we trends per jaar bekijken (stemmen en ratings) Bij de derde aggregatie (combined_stats_by_genre_year.csv) hebben we de genres gesplitst, want één film of serie kan meerdere genres bevatten. Hierbij hebben we de gemiddelde rating per genre per jaar geanalyseerd (mean_rating). Totale stemmen per genre per jaar (numVotes) en vervolgens de titel (title). Hierdoor was het mogelijk om inzicht te krijgen welke genres populair waren in bepaalde jaren. 



