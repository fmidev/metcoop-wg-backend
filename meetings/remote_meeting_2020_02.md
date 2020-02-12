# WG back-end, meeting memo
Mon 12.2.2020 11:00-12:00 (UTC+2), Remote

## Participants:
Roope Tervo , lead architect, FMI<br>
Petri Vuorio, alert expert, FMI<br>
Mikko Rauhala, head of production, FMI<br>
Gjermund Haugen, MET <br>
Linus Larsson, SMHI <br>
Tomas Karlsson, SMHI <br>


## Agenda:
* RSS and/or Atom feed
* OGC API Feature service
* Issues

## Notes

* Feeds
 * RSS recommend by Eliot Christian ('WMO')
   * MET have only RSS    
 * Some users prefer Atom
 * Fat or thin Atom feed (are warnings included in the feed)?
   * If Atom is supported, it should be fat
 * Language
   * MET have separate feeds for each language but they refer to the same document  
   * No language versions of the CAP, all languages within one document
   * RSS support only one language --> separate feeds for each language
   * Atom support languages but should not be used here
   * We should have different feeds for each language


* OGC API Feature service
 * None of the institutes do not have resources at the moment
 * GeoWeb will need this anyway
   * Roope will contact KNMI and suggest that common definition (and maybe implementation) should be made


* Handled issues
 * https://github.com/fmidev/metcoop-wg-backend/issues/5
 * https://github.com/fmidev/metcoop-wg-backend/issues/6
 * https://github.com/fmidev/metcoop-wg-backend/issues/7
 * Rest of the issues are handled 'offline'
