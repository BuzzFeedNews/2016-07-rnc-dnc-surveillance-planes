# Aerial Surveillance Of The Republican and Democratic National Conventions

This repository contains data to support the the findings reported in the July 24, 2016 BuzzFeed News article ["The Republican Convention Was Secretly Watched From Above"](https://www.buzzfeed.com/peteraldhous/surveillance-at-the-rnc) and the August 1, 2016 article  ["Government Spy Planes Circled Over The Democratic Convention More Intensely Than GOP Event"](https://www.buzzfeed.com/peteraldhous/surveillance-at-the-dnc).

## Data

The data comes from the aircraft-tracking website [ADSB-Exchange](http://www.adsbexchange.com/), plus the Federal Aviation Administration's (FAA) [aircraft registration database](http://www.faa.gov/licenses_certificates/aircraft_certification/aircraft_registry/releasable_aircraft_download/). ADSB-Exchange takes feeds from aviation enthusiasts who operate radio antennas that can detect transponder signals transmitted by nearby aircraft.

**The repository contains the following files:**

- `rnc.csv` Federal, state, and local government aircraft tracked in the vicinity of the Republican National Convention in Cleveland, from July 15-22 (the convention ran from July 18-21). Includes [two](http://registry.faa.gov/aircraftinquiry/NNum_Results.aspx?NNumbertxt=6968A) [helicopters](http://registry.faa.gov/aircraftinquiry/NNum_Results.aspx?NNumbertxt=6987A) operated by Midwest Aerial Imaging, identified by BuzzFeed News as a front for the federal government: [FAA documents indicate](https://www.documentcloud.org/documents/2997784-N6968-Airworthiness.html#document/p15/a309658) that the helicopters are part of the Department of Homeland Security's fleet.

- `dnc.csv` Federal, state, and local government aircraft tracked in the vicinity of the Democratic National Convention in Philadelphia, from July 22-29 (the convention ran from July 25-28). Includes [a helicopter](http://registry.faa.gov/aircraftinquiry/NNum_Results.aspx?NNumbertxt=614TC) operated by TAFY Consulting, [previously identified](http://buzzfeednews.github.io/2016-04-federal-surveillance-planes/analysis.html) as a front for the FBI.

- `aeroptic.csv` Flights by aircraft operated by [Aeroptic](http://aeroptic.com/), from April 28 to July 25, 2016. Aeroptic is a subsidiary of the defense and intelligence contractor [KEYW](https://www.keywcorp.com/). It specializes in aerial photography and mapping, and in 2013 [was awarded](http://investors.keywcorp.com/releasedetail.cfm?ReleaseID=815033) a [military contract](https://www.usaspending.gov/transparency/Pages/TransactionDetails.aspx?RecordID=B760AC43-7582-4CFE-AB39-D44804199711&AwardID=35651097&AwardType=SC) to provide high-resolution 3D maps to improve battlefield awareness for US troops in Afghanistan and elsewhere. In June 2016, Aeroptic's planes surveyed the two convention cities, Cleveland and Philadelphia.

**The files contain the following fields, for each transponder detection:**

- `adshex` Unique identifier for each aircraft, corresponding to its “[Mode-S](http://www.skybrary.aero/index.php/Mode_S)” code, in hexademical format.
- `reg` Aircraft [registration code](http://www.faa.gov/licenses_certificates/aircraft_certification/aircraft_registry/forming_nnumber/), sometimes called a “tail number.”
- `name` Current registrant for the aircraft, from FAA registration database.
- `name2` Edited from`name`, for consistency, and to reflect government agency behind a front company.
- `type` International Civil Aviation Organization aircraft [type code](https://en.wikipedia.org/wiki/List_of_ICAO_aircraft_type_designators).
- `squawk` Four-digit code transmitted by the transponder. (Codes from 4401 to 4433 [are reserved](http://www.faa.gov/documentLibrary/media/Order/JO_7110.66D_.pdf) for federal law enforcement.)
- `longitude` `latitude` Geographic location in digital degrees.
- `altitude` Altitude in feet.
- `heading` Compass bearing in degrees, with 0 corresponding to north.
- `timestamp` Full UTC timestamp.

The files `dnc.csv` and `rnc.csv` also contain the following fields:

- `loc_timestamp` Timestamp in local time, EST in both cases.
- `loc_date` Local date.


## Questions / Feedback

Email the author Peter Aldhous at [peter.aldhous@buzzfeed.com](mailto:peter.aldhous@buzzfeed.com).