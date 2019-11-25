# WG back-end, meeting memo
Mon 25.11.2019 10:00-11:50 (UTC+2), Remote

## Participants:
Roope Tervo , lead architect, FMI<br>
Petri Vuorio, alert expert, FMI<br>
Mikko Rauhala, head of production, FMI<br>
Helen Korsmo, system developer, MET Norway<br>
Tomas Karlsson, lead architect, SMHI<br>
Håvard Futsæter, Lead API development, MET <br>

## Feed and Filtering Services

### Current status

MET:
- RSS-feed
 - filtering service with one point (lat & lon): https://api.met.no/weatherapi/metalerts/1.1/documentation
- quite much logic in the presentation layer
 - overlapping polygons

SMHI:
- no filtering
- separate XML and JSON files (same information)
- based on CAP-information model

FMI:
- no open feed available
- prototype atom-feed open but not public
- private WFS service with JSON-format, provided to clients as well

### Desired status and plans

MET:
- Service for simplified feed
 - JSON-format next year?
 - CAP meant primarly for data exchange

SMHI:
- internal data model, turned to CAP and other formats
- discussion to provide a simpler JSON-format
- push service for professionals (common portal in Sweden, VIS)

FMI:
- going to open public feed soon (atom, RSS or both)
- no plans for other public services but those could be provided

### Harmonising services

#### RSS/Atom/other
- RSS and Atom dying format?
- WMO and MeteoAlarm will require that also in the future
- All institutes will need to provide this feed at least for some time still
- SMHI use more Atom feeds in open data general
- what should be used in id (atom) / identifier (rss), the same id with CAP data format
- OASIS CAP Feed Specification (https://docs.oasis-open.org/emergency-adopt/cap-feeds/v1.0/cap-feeds-v1.0.html) says that both RSS and Atom is good (used also by WMO)
- SMHI prefers Atom
- Both are fine to FMI
- MET could most probably provide the both feeds
- Helen will email to WMO

#### OGC API Features (WFS3)
- would be most probably popular among open data users
- (Geo)JSON-format encoding?
- API and data format needs to be defined still
- possibilities to create common translation/backend software
  - FMI has node OGC API Features service
  - MET use java, go and python (node could be ok as well)
  - SMHI have services using node (old system done with java)  
- KNMI need to be contacted
- check status early next year if we have resources to go ahead
- very rough estimate about required resources (6 man months)

## Next meetings
- 13th Dec 13:00 UTC+1
- 12th Feb 10-11 UTC+1
