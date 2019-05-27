# WG back-end, meeting memo
Mon 27.5.2019 9-16 EET (UTC+2), Oslo

## Participants:
Roope Tervo , lead architect, FMI<br>
Petri Vuorio, alert expert, FMI<br>
Håvard Futsæter, lead api development, MET Norway<br>
Helen Korsmo, system developer, MET Norway<br>
Tomas Karlsson, lead architect, SMHI<br>
Gjermund, Deputy head of forecasting division in Tromsø, MET Norway<br>

## Agenda
9:00 -  9:20 Introductions, round-a-table, agenda, goals<br>
9:20 -  10:20 Current situation with examples + discussion (20 minutes for each institute)<br>
10:20 - 10:30 Break<br>
10:30 - 11:30 Differences between each institute<br>
11:30 - 12:30 Lunch<br>
12:30 - 15:30 Creating common CAP Example<br>
15:30 - 16:00 Conclusion and next steps<br>

## Notes

### General

#### ToR
- next to be introduced to steering groups

#### Introduction
Round table introduction.

Non-goal: Agreement on how warnings are created and issued, e.g. content of messages. 

Non-goal 2: Waiting on meteoalarm to create services with the common CAP profile.

Goal today: Common CAP example for FMI, MET and SMHI for one type of warning forecast. Intention is to build on this example to create a common CAP profile for the open data alerting services of our three countries. Use this format to either suggest for Meteoalarm adoption, or to harmonize it with the profile Meteoalarm will use.

#### Current situation
##### MET-Norway
Cooperation with NVE(hydrology) and NRK (presentation). Special extensions in our profile to fit both issuing from MET and NVE, and with how NRK wants to do presenation. Also, agreements on how the standard elements should be used(informal agreements on semantics), based on presenation logic needs and issuing. 

NVE and MET produce separate alerting feeds.

Different CAP flavor sent to Meteoalarm, and different presentation to the national presentation web sites.

Color code on awareness_level.

##### SMHI
Dedicated CAP tool(KEPS) for producing warnings in CAP.

New tool, TOVE, that support all text based forecasts, with automated suggestions for text. Serializiation format separated from production.

"Pre" alert messages in CAP-ish? Custom xml format for listing available views of CAP messages. Stable url that includedes all current messages in one response, instead of RSS. Messages presentented in several languages.

Active messages rely on syncing the client with available messages in the web service.

Separate list of ares with polygons, referenced by id in CAP.

Color coded categories of messages in the presentation(e.g forest fire). Also color code on severity(or awareness level?)

Separate message format for risks(not alerts yet).

###### FMI


#### Next steps

### Next meeting
- 27th May in Oslo (full day meeting)

## Tasks
