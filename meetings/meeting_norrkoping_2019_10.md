# WG back-end, meeting memo
Mon 28.10.2019 8:30-15:30 (UTC+1), Norrköping

## Participants:
Roope Tervo , lead architect, FMI<br>
Petri Vuorio, alert expert, FMI<br>
Mikko Rauhala, head of production, FMI<br>
Helen Korsmo, system developer, MET Norway<br>
Tomas Karlsson, lead architect, SMHI<br>
Gjermund Haugen, Deputy head of forecasting division in Tromsø, MET Norway<br>
Håvard Futsæter, Lead API development, MET <br>
Linus Larsson, web architect, SMHI

## Agenda
8:30 - 8:45 Technical <br>
8:45 - 9:00 News from MeteoAlarm<br>
9:00 - 11:30  Finish going through the standard. Area and parameters are important subjects.<br>
11:30 - 12:00 Lunch<br>
12:00 - 14:00 Discuss the feed and filtering services.<br>
14:00 - 15:00 Conclusion and roadmap for the future<br>

## Notes

### MeteoAlarm

- Gjermund and A-J Punkka participated in the meeting at Sep 2019
- Task Team of CAP haven't been activated (not on the roadmap until next summer)

### Standard Profile

- Style guide and libraries/libraries should be published.

Fulfilled elements:
 - ***identifier***: <br>
 Identify only message (not alert), the same id can't be used in different feeds. However, different ids would lead to multiple warnings from the same issue.
 - ***Info***: <br>
 Swedish translation should be harmonised (according OASIS/WMO translation document). Note, for example, document contain only wind. Different wind for land and sea events are used in MetCoOp context. Content specialists could contribute to the translation document.
 - ***eventCode***:<br>
 Content specialists (A-J Punkka, Gjermund Haugen, Åsa Granstrom) will be asked to define harmonised eventCode list. Some material:<br>
  https://en.wikipedia.org/wiki/Specific_Area_Message_Encoding<br>
  https://www.oasis-open.org/committees/download.php/41768/CAP-AP <br>
  Geographical domain shall be added as a evenCode.

 - ***area***:<br>
 MeteoAlarm use their own area definitions (repository of shape files) with EMMA IDs. MeteoAlarm provide geometries in the CAP feed. Polygons should be used to to help users. Free polygons are also needed. Polygons may extend country borders although alerts are only valid in the issuing country. No specific parameters are needed to define which countries are affected.

 - ***polygons***:<br>
 Freehand polygons may be used. Currently they are used only for land areas.

- ***geocodes***:<br>
  ISO standards are currently used for counties but there's no international standard for municipalities. To avoid collisions in values, resolvable URI should be used.

- ***parameter***:<br>
  Triggering parameters were discussed. Decided to leave those out (as well as threshold values) since they may be confusing and used as a weather forecast. They could be in conflict with weather forecast.

  Lot's of discussion since there's awareness_level and awareness_type used in MeteoAlarm. Almost the same information is given in CAP elements responseType, urgency, severity, certainty and eventCode. Do we need to provide this duplicate information as parameter?

  MeteoAlarm is discussing changing *awareness_type* to *eventCode* and *awareness_level* to *color*.

  So far we leave *awareness_level* and *awareness_type* as confusing. We may modify profile to align with MeteoAlarm if necessary.

  Instead we put parameter named *color* defining colors with names ('green', 'yellow' and 'orange', 'red', coming from MeteoAlarm). We need to ask for comments from content specialists with this parameter. Content specialists would define a matrix of severity, certainty and urgency. This could maybe done parameter by parameter.

  Namespace of the additional parameters were discussed.

  *eventEndingTime* is standardised by National Weather Service and Google. MET uses that to all parameters except forest fires and gale warnings. This need to be asked from content specialists.

- ***Resource***:<br>
 MET Norway uses for images. Others don't use.

### Feed and Filtering Services

Not handled

### Next steps

- Roope write a draft profile document
- Roope send the draft to comments, especially for content specialists
- MET and FMI aim to implement the profile before end of 2019
- Issues raised while implementing the profile and from the content specialists are made to github
- Regular (remote) meetings are kept to resolve the issues
- When there are only minor issues left, we suggest the profile to as official profile and accepted by steering group

### Next meetings
Roope will send a doodle

### Next items
- WFS3 for open data
