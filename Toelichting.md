# Toelichting ImZTC 2.2

Het objecttype CATALOGUS voorziet in de behoefte aan vele organisatie- en domeinspecifieke zaaktypecatralogi. Daarmee worden alle ZAAKTYPEN en daaraan gerelateerde objecten 
en attributen voor een specifiek domein gebundeld tot één geheel. Het domein waarop zo’n catalogus van toepassing is, kan sterk uiteenlopen. Er zullen catalogi zijn die met 
de ZAAKTYPEn van één overheidsorganisatie worden gevuld, maar ook catalogi worden ontwikkeld die veel breder reiken; denk aan een sectorale catalogus voor alle 
overheidsorganisaties die binnen een sector actief zijn of een ketencatalogus voor ketenpartners. Het informatiemodel voorziet daarom in een unieke identificatie van een 
CATALOGUS: de combinatie van het RSIN van de ‘eigenaar’ van de CATALOGUS en het Domein waarop de CATALOGUS van toepassing is.

In één CATALOGUS worden op het hoogste niveau verschillende objecttypen onderscheiden. Het belangrijkst is natuurlijk het objecttype ZAAKTYPE; een zaaktypecatalogus definieert 
immers de verschillende ZAAKTYPEn die relevant zijn voor het domein waarop de CATALOGUS betrekking heeft en bepaalt zo de gegevens die worden vastgelegd van zaken van het 
ZAAKTYPE. Historie is in het model zodanig opgenomen dat versies van zaaktypen onderscheiden kunnen worden, met telkens bij elke versie van een zaaktype alle daarbij behorende 
waarden van het zaaktype en van de ‘onderliggende’ objecttypen zoals statustypen, informatieobjecttypen en resultaattypen.

De CATALOGUS bevat, op hetzelfde niveau als het ZAAKTYPE, de objecttypen BESLUITTYPE en INFORMATIEOBJECTTYPE (voorheen Documenttype). Deze objecttypen zijn zo te gebruiken in 
alle ZAAKTYPEn die in de CATALOGUS worden gedefinieerd. Omdat de waardenlijsten van deze objecttypen fors kunnen zijn, kan in elk ZAAKTYPE worden geconfigureerd welke 
BESLUITTYPEn en INFORMATIEOBJECTTYPEn relevant zijn voor zaken van het ZAAKTYPE. De objecttypen BESLUITTYPE en INFORMATIEOBJECTTYPE zijn - met kleine aanpassingen en 
aanvullingen - overgenomen uit het RGBZ.

Binnen elk ZAAKTYPE zijn de objecttypen STATUSTYPE, ZAAKOBJECTTYPE, ROLTYPE, EIGENSCHAP en RESULTAATTYPE gemodelleerd.

Het STATUSTYPE is overgenomen uit het RGBZ en wordt in het ImZTC eveneens gemodelleerd binnen een ZAAKTYPE . De reden hiervoor is dat de herbruikbaarheid van STATUSTYPEn beperkt 
is; er is weliswaar een aantal generieke STATUSTYPEn denkbaar (bijvoorbeeld ‘Ontvangen’ of ‘Afgehandeld’), maar in een groot aantal gevallen krijgt een STATUSTYPE en de daarbij 
horende attributen een ZAAKTYPE-specifieke invulling.

Het ZAAKOBJECTTYPE is een objecttype dat noch in het RGBZ, noch in versie 1 voorkomt. Het objecttype is in versie 2 geïntroduceerd om vooraf - per ZAAKTYPE - de relatie tussen 
een ZAAK en de basis- en kerngegevens die relevant zijn voor ZAAKen van dat ZAAKTYPE inzichtelijk te maken en - belangrijker - registratie daarvan tijdens de behandeling van 
een ZAAK te kunnen afdwingen. Denk aan het niet kunnen zetten van een STATUS als niet eerst een relevant basis- of kerngegeven via ZAAKOBJECT is gerelateerd aan de zaak.

Ook het ROLTYPE is een objecttype dat niet in het RGBZ of versie 1 voorkomt. Het voorziet in de behoefte om per ZAAKTYPE een duidelijke typering te kunnen geven aan de 
BETROKKENEn die in een - door het ROLTYPE - bepaalde hoedanigheid ‘acteren’ in zaken van een bepaald ZAAKTYPE. Het ROLTYPE beoogt zo vooral ondersteuning te bieden aan het - via 
het ROLTYPE - onderscheiden van groepen BETROKKENEn en daarvoor specifieke functionaliteit aan te bieden. Denk bijvoorbeeld aan het instellen van autorisaties voor bepaalde 
ROLTYPEn, of het informeren van BETROKKENEn in één of meer ROLTYPEn over de voortgang van de behandeling van zaken van een bepaald ZAAKTYPE.

Het ImZTC modelleert het objecttype EIGENSCHAP als objecttype bij een ZAAKTYPE. Een EIGENSCHAP is een voor het betreffende ZAAKTYPE specifiek gegeven dat voor de - besturing van 
de - behandeling van een zaak van dat ZAAKTYPE van groot belang is. Denk aan de EIGENSCHAP ‘Datum evenement’: dit gegeven is relevant voor de behandelaar van aanvragen voor een 
evenementenvergunning, bijvoorbeeld om evenementen te sorteren op datum en aanvragen voor evenement die de komende weken zijn gepland eerder te behandelen dan evenementen die 
pas over enkele maanden zullen plaatsvinden.

Verder kent het ImZTC bij een ZAAKTYPE het RESULTAATTYPE: een objecttype dat niet in het RGBZ voorkomt, maar wel al in versie 1 werd geïntroduceerd. Het RGBZ kent overigens bij 
een zaak wel het attribuut Resultaatomschrijving dat bij een fysieke zaak een waarde heeft die ontleend wordt aan de RESULTAATTYPEn bij het ZAAKTYPE van die zaak. Het is in 
versie 2 in meer detail gemodelleerd met het doel betere ondersteuning te bieden aan het correct en integraal kunnen archiveren van zaken van een bepaald ZAAKTYPE en daarbij 
geautomatiseerd te bepalen wat de datum is waarop een zaakdossier vernietigd of overgebracht (naar een archiefbewaarplaats) moet worden. In uitzonderingsgevallen moet een 
individueel informatieobject in een zaakdossier eerder vernietigd worden dan de zaak als geheel. In het correct archiveren van dergelijke gevallen voorziet de relatie van 
RESULTAATTYPE naar ZAAK-INFORMATIEOBJECT-TYPE.

Dan resten nog de relaties tussen ZAAKTYPEn onderling. In het ImZTC worden twee relatiesoorten onderscheiden: de relatie tussen een ZAAKTYPE en deel-ZAAKTYPEn en de relatie 
tussen (om andere redenen) gerelateerde ZAAKTYPEN. De tweede relatiesoort betreft de relatie tussen een ZAAKTYPE en de ZAAKTYPEn die een noodzakelijk vervolg zijn op het 
erstgenoemde ZAAKTYPE, de relatie tussen een ZAAKTYPE en de ZAAKTYPEn die een bijdrage leveren aan de behandeling van het eerstgenoemde ZAAKTYPE en de relatie tussen een 
ZAAKTYPE en andere ZAAKTYPen waarop het eerstgenoemde ZAAKTYPE betrekking heeft. Al deze relaties maken het mogelijk om ZAAKTYPEn zuiver af te bakenen, overeenkomstig 
bedrijfsprocessen, en grip te behouden op samenhang en samenwerking tussen bedrijfsprocessen, binnen de eigen organisaties en tussen organisaties, teneinde een passend 
antwoord te verkrijgen op de aanleiding voor een zaak.