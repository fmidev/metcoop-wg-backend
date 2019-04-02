# WG back-end, meeting memo
Tue 2.4.2019 10-11:30 EET (UTC+2), Virtual

## Participants:
Roope Tervo , lead architect, FMI<br>
Petri Vuorio, alert expert, FMI<br>
Ville Karppinen, head of group, FMI<br>
Håvard Futsæter, lead api development, MET<br>
Ivar Seierstad, lead Yr development, incl the data flow, MET <br>
Helen Korsmo, system developer, MET<br>
Tomas Karlsson, lead architect, SMHI<br>
Linus Larsson, web architect, SMHI<br>

## Agenda
GENERAL<br>
Set-up, introductions: 10 min<br>
ToR: 20 min<br>
Needs of post-processing and archiving groups: 20 min<br>

ALERTS<br>
Current status in every country: 15 min<br>
Starting point for common format: 10 min<br>
Issues in encoding: 15 min<br>
Common interface: 10 min<br>

 Next (face-to-face) meeting: 10 min<br>

## Notes

### General

#### ToR
- next to be introduced to steering groups

#### Needs of post-processing and archiving groups
- metcoop days discussed about post-processing
- scope would be mainly ensemble calibration
- no concrete plan so far
- allocated resources are asked from the steering group
- calibration should be done based on new CMEPS
- output most probably GRID products

### Alerts
- SMHI rewriting whole alert system this year
- All data should be provided via Open Data

#### Current status in every country

MET Norway
- CAP provided in 2016
- 2018 extreme weather warnings provided in CAP
- WMO guidelines followed
- syncrhonised with ENVI? (hydrology) (how to updata/cancel? how to issue warnings)
- incident name added (name of the storm)
- report written in Norwegian:
- CAP editor added to existing editor xx (written C++)
- consider joining GeoWeb
- RSS feed: (incl. images)
- languages: norwegian and english

SMHI:
- CAPS district based warnings
- send to meteoalarm
- publish to as open data
- this and next year project for impact based alerts
- only land warnings
- free area
- json as internal format
- complete renewal
- meteoalarm can't use impact based warnings, district based warnings are required
- Atom feed: xx + API (XML + JSON): xx
- SMHI provide all warnings (weather + flood)  
- SMHI have no instructions but have category of warnings called messages (notifications), not delivered to MeteoAlarm

FMI:
- SmartMet Alert tool launched in 2015
- CAP provided to meteoalarm in 2016
- CAP not edited (generated based on edited warnings)
- free area
- free area --> districts conversion done automatically
- languages: finnish, swedisth and english
- data not provided openly (PoC atom feed running, providing MeteoAlarm CAP files)
- data provided via WFS (GeoServer, XML + JSON) to clients
- currently specific instructions are not provided, mobile app UI provides some general static instructions in UI

#### Starting point for common format

- core elements and extensions?
- meteoalarm? good examples? some country?

- Examples of CAP messages to Git Repo. Roope create a folder. Named like: _institute-type-time.xml_
- meteoalarm format is missing some expression power
- end time added to as special parameter in Norway, open discussion in SMHI, FMI has end time
- try to achieve that same things are always presented in the same way
- it would be good to provide recommendation how to use this open data
- we need to check if we can be aligned with Google recommendations
- we need to check WMO alert hub recommendations

Possible starting point:
- Take MeteoAlarm CAP as starting point and start to extend and adjust that

Working methods:
- two full day workshops

#### Issues in encoding
see above

#### Common interface
- RSS/Atom feed/WFS?
- In RSS/Atom messages need to be combined together --> should all messages be presented? Ordering of messages? How to move message to headers?
- Cancellation and updates are important issue
- Atom feed/RSS need to be enriched with JSON status feed

### Next meeting
- 27th May in Oslo (full day meeting)

## Tasks
- we need to check if we can be aligned with Google recommendations
- we need to check WMO alert hub recommendations
- Examples of CAP messages to Git Repo. Roope create a folder. Named like: _institute-type-time.xml_
- we need to check:
-- how we are compatible with each others? what are issues we need to address?
-- how we are compatible with WMO and Google?
-- as the result we need list of issues as a document
