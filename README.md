San Diego Crime Data
========

  * Account: `sandiego`
  * Project: `crime`
  * Key: `de0128c1cb7b70f583f56dd71da857df`

Access it in JavaScript:

```
var stretchr = new Stretchr.Client("sandiego","crime","de0128c1cb7b70f583f56dd71da857df");
```

Or in a Terminal:

```
curl https://sandiego.stretchr.com/api/v1.1/crime/incidents?key=de0128c1cb7b70f583f56dd71da857df
```

## Overview

#### Raw data

    https://sandiego.stretchr.com/api/v1.1/crime/incidents?key=de0128c1cb7b70f583f56dd71da857df)

Example record:

```
{
  address: "8300 Block Jane Street",
  asr_zone: 1,
  city: "SndSAN",
  comm_pop: 42779,
  community: "SanRNC",
  coun_pop: 143957,
  council: "San005",
  date: "2008-09-19",
  day: 3184,
  desc: "ILLEGAL POSSESS TEAR GAS/ETC",
  dow: 5,
  gcquality: 54,
  gctype: "cns/segment",
  hour: 13,
  id: "",
  is_night: 0,
  lampdist: 3162,
  lat: 32.9573366666,
  lon: -117.143776738,
  month: 9,
  nbrhood: "SanRNC",
  segment_id: 46189,
  time: "13:00:00",
  type: "WEAPONS",
  week: 37,
  year: 2008,
  ~created: 1395897195,
  ~id: "5333b36bb600303af700015c",
  ~updated: 1395897195
}
```

### Safest communities `group(community).count()&order=count`

    https://sandiego.stretchr.com/api/v1.1/crime/incidents.json?key=de0128c1cb7b70f583f56dd71da857df&agg=group(community).count()&order=count

### Communities with most crime `group(community).count()&order=-count`

    https://sandiego.stretchr.com/api/v1.1/crime/incidents.json?key=de0128c1cb7b70f583f56dd71da857df&agg=group(community).count()&order=-count

### Types of crimes per community `group(community).uniqueSet(type).count()`

    https://sandiego.stretchr.com/api/v1.1/crime/incidents.json?key=de0128c1cb7b70f583f56dd71da857df&agg=group(community).uniqueSet(type).count()&order=count
    
### Crime stats by year `agg=group(year).count()`

    https://sandiego.stretchr.com/api/v1.1/crime/incidents.json?key=de0128c1cb7b70f583f56dd71da857df&agg=group(year).count()&order=-count
    
### Crime by time of day `group(time).count()`

    https://sandiego.stretchr.com/api/v1.1/crime/incidents.json?key=de0128c1cb7b70f583f56dd71da857df&agg=group(time).count()&order=-count