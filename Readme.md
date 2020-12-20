

# Web semantic project about a bicycle station sharing system


## Build a database of bicycle-sharing stations
Get open data about bicycle-sharing systems from as many cities as possible. Here is a list of cities that have data on their bicycle-sharing system:

Saint-Étienne
Données ouvertes de Saint-Étienne Métropole
Lyon
Real-time available. See also Grand Lyon data portal.
Rennes
Real time data. See also Rennes Métropoloe data portal.
Montpellier
Real time data. See also OpenData Montpellier Métopole.
Strasbourg
Real time data. See also Strasbourg open data.
Paris
Real time data. See also Paris open data portal.
You can find other data sets for bicycle-sharing systems all over the world by consulting the list of bicycle-sharing systems from Wikipedia. For France specifically, there is a list that contains more details. The open data portal of the French government has data about many bicycle-sharing systems that you can get by going to https://transport.data.gouv.fr/gbfs/city_name_lowercase/station_status.json. For instance https://transport.data.gouv.fr/gbfs/toulouse/station_status.json for Toulouse. Bicycle-sharing systems that are operated by company JC Decaux have data available using a single API with URLs of the form https://api.jcdecaux.com/vls/v1/stations?contract=Cityname&apiKey=your_API_key. You need to register an API key to use it.



+ Setup a triplestore. The simplest is to use Apache Jena Fuseki, but you may also install a OpenLink's Virtuoso server (triplestore used by DBpedia in its backend) or Blazegraph (triplestore used by Wikidata) or Stardog (another commercial triplestore that has a free version). A list of triplestores is available on Wikipedia.
+ Define or reuse a vocabulary for describing bicycle-sharing stations and their availability.
+ Convert static data about the bicycle stations into RDF, and load the resulting data to the triplestore. You can simply generate an RDF file that you load manually to the triplestore, or add the RDF programmatically using SPARQL Update queries.
+ Make a website that will allow one to select a city (in a list or on a map) and get the availability of the bicycles, and bicycle stations. There resulting list should be available in HTML with RDFa. You may also make the data available in RDF (Turtle, RDF/XML, or JSON-LD) based on content negotiation.
+ While the real time data may be generated on the fly, static data should be extracted from the triplestore using a SPARQL query.
The previous steps constitute the bare minimal. You should then try to extend your application by integrated other kinds of data. For example, you may:

+ provide other kinds of availabilities (make sure that you extend the vocabulary for this);
+ integrate other transportation data (find bike stations nearest to train station) or other geospatial data;
+ add information on the prices, street addresses, etc.;
+ store the history of availabilities, and provide statistics;
+ use weather or air quality data as well;
+ provide a trip planning functionality (go from Place 1 to Place 2 by taking the available bike closest to Place  and bringing it to the station with available space, closest to Place 2).
