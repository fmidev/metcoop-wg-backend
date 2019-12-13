**DRAFT. NOT USED IN OPERATIONS**

Following defines MetCoOp CAP profile defined together by SMHI, FMI and MET Norway. This profile is made to ensure that meteorological alerts are provided in **technically** harmonised format and via similar services. The profile is fully CAP 1.2. (http://docs.oasis-open.org/emergency/cap/v1.2/CAP-v1.2-os.html) compatible.

This profile aims for technical harmonisation -- content of the alerts may still differ in each countries. Several warnings may also be issued to the same area by different senders.

Discussion behind this profile is documented in meetings folder and in issues in this project.

## CAP Elements

Following defines how each element is used in the profile.

### alert
Mandatory

One alert message, specifying CAP OASIS standard with xml namespace.

#### identifier
Mandatory

Unique string, in time and space, for an alert message identifying the message/document.

Must not be used to convey any information, except the identity of the message.

Format: Does not matter to FMI, MET and SMHI.

#### sender
Mandatory

Format: WMO Organization ID (OID).

#### sent
Mandatory

The time the message was produced.

#### status
Mandatory

Recommendation: Always have a valid "Test" message.

#### msgType
Mandatory

UPDATE and CANCEL events by the rules of Google Public Alerts CAP-elements-Definitions.pdf

We ignore "Ack" and "Error" messages types.

#### source
Not used

#### scope
Mandatory

Always Public

#### restriction
Not used

#### code
Mandatory

Identifies the message as following MetCoOP CAP Standard, versioned.

Format: Link to the versioned specification document.

#### note
Not used

#### references
Optional

Clarification: UPDATE msgType must refer to all previous messages that it updates.

#### incidents
Optional

If used, it will be specific to the sender issuing the message.

### info
Mandatory

Only a single info container pr. language. So, if multiple info containers, its exact same information translated into multiple languages.

#### language
Mandatory

#### category
Mandatory

#### event
Mandatory

Controlled vocabulary, issued by OASIS/WMO: https://docs.google.com/spreadsheets/d/1n5hvh7S9jCqyhmr6acP0FBHq4a9O2MBlxg39J6_eUoQ/edit#gid=40743640, shall be used when applicable.

#### responseType
Optional

"AllClear" for cancelling with UPDATE msgTYpe shall be used.

#### urgency
Mandatory

Note, different usage of the terms between countries may cause confusion, but a solution requires harmonising how forecasting is done in each nation.

"Unknown" shall not be used.

#### severity
Mandatory

Note, different usage of the terms between countries may cause confusion, but a solution requires harmonising how forecasting is done in each nation.

"Minor" shall not be used to publish "No Warnings" messages.

"Unknown" shall not be used.

#### certainty
Mandatory

Different usage of the terms between countries may cause confusion, but a solution requires harmonising how forecasting is done in each nation.

"Unknown" shall not be used.

#### audience
Not used

#### eventCode
Optional

MetCoOp-harmonised evenCode list is to be defined and used in the future.

Issuers may use additional eventCodes as well.

#### effective
Not used

#### onset
Mandatory

When the alert starts. If the warning is updated after the event has started, it will be the same as <sent>. 

#### expires
Optional

The alert is valid until expired or cancelled, NOT denoting the time when the weather is getting better.

Meaningful expires value shall be used.

#### senderName
Mandatory

Official names, localised, names.

#### headline
Mandatory

Short summary of the entire message(140 characters)

#### decription
Mandatory

#### instruction
Optional

#### web
Mandatory

Link to more human readable information about this alert. If possible, should link to the specific, localised, resource.

#### contact
Mandatory

Url to a contact information.

#### parameter
Mandatory

Parameter with valueName *color* and value having value one ('green', 'yellow' and 'orange', 'red') as defined in MeteoAlarm CAP profile parameter *awareness_level* shall be used.

*awareness_type* and *awareness_level* parameters are not used.

Parameter with valueName *eventEndingTime* should be used when applicable as defined in: https://www.weather.gov/media/alert/CAP_Transition_Guide_030717.pdf.

Additional parameter may be used.

#### resource
Optional

### area
Mandatory

If the alert is in area with several areaDesc (i.e. multiple provinces), multiple area elements shall be used. Multiple polygons and/or geocodes are allowed in the single area element.

#### areaDesc
Mandatory

#### polygons
Mandatory

Coastlines and country borders should be followed as accurately as possible. However, polygons *may* extend country borders although alerts are only valid in the issuing country.

Resolution of the polygons should be defined conservatively reducing number of points so that the polygons can be processed in a reasonable time.

#### circle
Optional

#### geocode
Optional

URIs should preferably be used as valueNames with a descriptive part in it.

EMMA_IDs shall not be used.

#### altitude
Optional

#### ceiling
Optional
