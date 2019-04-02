# WG back-end, meeting memo
Thu 24.1.2019 14-16 EET (UTC+2), Virtual

## Participants:
Roope Tervo , lead architect<br>
Mikko Rauhala, head of production<br>
Håvard Futsæter, lead api development<br>
Ivar Seierstad, lead Yr development, incl the data flow<br>
Tomas Karlsson, lead architect<br>

## Agenda
Set-up, introductions: 10 min
Background: 15 min
ToR: 30 min
Goals & timeline: 30 min
Group set-up: 10 min
Working methods: 10 min
Next (face-to-face) meeting: 10 min

## Notes

### Background
\-

### ToR

End report:

> ## Vision
> We identified that in working collaboration in the field of back-end services:

> 1. Back-end services support front-end applications and workstations by providing a common interface for operational data in each countries. That interface is based on some existing commonly used standard (e.g. OGC, WIS, INSPIRE, OpenWeather, etc.).
> 2- Every institute has opportunity to use each other’s data as an operational backup and as part of meteorologists’ workflow.
> 3. Our developers would meet at least twice a year.
> 4. We have shared slack channel(s).
> 5. Whenever new projects are started in any institute, other ones are informed so that new collaboration can be considered.
> ## Scope of Services
> We noted that common interface should at least contain:
> * warnings (CAP)
> * Time series (observations and forecasts)
> * WMS (images)
> * Gridded data

> It is notable that gridded data access is required in MetCoOp collaboration for several different use cases. In order to minimize lead time from HPC output to operations, common API for accessing the data is needed. UK MetOffice is establishing similar API in their Decoupler project. Common API is also required for accessing archived data.

> In the future, probably also some processing capabilities should be added. For a start, filtering support could be added but also calculating EPS statistics would be beneficial.

## Notes regarding to ToR:

We noted that following scopes should be considered to be added into scope:
- Data for visualisation (like geojson, topojson)
- HPC operations are important, but it is a large project. Similar interfaces could be tested with post-processing or other production which need all data from each country.

We noted that we should start small and build incrementally. We also noted that implementation should be done as fast as possible, ideally we could create straight working code which could shipped with docker images. In practice thou, it may be challenging to find all necessary development resources.  

Pre-requirements for any topic are that we can find relatively straight path to production and we have real use cases.

Tomas stated that we should integrate to MetCoop development team. It is an open question how to keep good and active connection the development team but still remain fast and agile enough.

## Goals & timeline

We discussed about active projects in each institute:

Relevant projects in MET:
- implementation of CAP
- timeseries

Relevant projects in SMHI:
- re-definition of alerts (impact based)

Relevant projects in FMI:
- timeseries (WFS3)
- warnings as CAP

We also discussed about possibility to start with requirements cast by common post-processing. Planning of the post-processing starts in March (in working-days). We concluded that we should be in touch with that group to clarify their requirements. We also noted that sharing observations between countries is relevant for post-processing. Observations used in running the model shared in MetCoop is not a complete set and could be fulfilled with more stations. That could possibly be a use case for defining a common timeseries interface API. NetAtmo data (specially quality controlled data) could be shared via common API as well.  SMHI is joining UKMO WOW which could maybe be shared within MetCoop via the same API.

We also noted that some kind of interface is required for archiving (common or separate) as well.

We discussed about sharing warnings in opendata. SMHI share warnings as JSON and XML (like CAP). MET provides the observations as CAP (with some extensions). FMI is not providing warnings as opendata at the moment but is about to add them in autumn 2019.

We also discussed about timeseries APIs in each institute. We noted that they are used a lot in workstations as well and they are an active topic (under development) in FMI and MET.

We also discussed about API for forecast and observations:
- FMI use the same interface and data model (but open data and internal interface are not the same)
- SMHI use different interfaces
- MetNo use different interfaces

We also discussed about open data and whether we should provide raw or processed data via API. We noted that different groups exist with different needs. Timeseries API is the most used and it should be as simple as possible. Raw data has to be provided as well.


We discussed about what we should do first. We concluded that relevant topics found so far are:
- post-processing
- warnings
- timeseries

## Decisions:
- We take warnings as the first topic
- We discuss with post-processing team about their needs (Roope)
- We share progress and plans about timeseries (Roope adds it to next agendas)

Goal for warnings intefaces:
- converge specification for CAP and interfaces (RSS)
- get a reference implementation
- To be done in end of year
Group set-up
Every institute find warnings specialist to join our group

We need following people:
- it-people
- product owner
- user

## Working methods
We discussed that we will arrange face-to-face workshops for specific topics. We anticipated that warnings will require two workshops: preliminary the first one in March and the second one in mid Autumn. Each institute try to ensure if this timeline fits for their internal plans.

In between the workshops, we try to arrange a video meeting roughly once a month. We start with Google meet as it worked the best in this meetings.

We decided that all outcome to open github repository. Preferably, we would use a separate metcoop-github organisation. Roope will ask if we can get that. Other options is google docs, which have real-time collaborative editing. Tomas noted that it would be beneficial if many people are writing the same report. GitHub have same functions but without real time editing. We decided to try the github.

## Next (video) meeting:
- in a month
- Roope sends a doodle
