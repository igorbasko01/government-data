# government-data
Collect Israeli government data (Proposed Laws and Votes)

## Data Structure
The data is exposed  through the Knesset API, which is using the ODATA protocol. The API is somewhat documented [here](https://main.knesset.gov.il/Activity/Info/Pages/Databases.aspx).

The data is exposed in several entities, some of them aare listed here:
1. `KNS_Bill` - Proposed Laws.
2. `KNS_BillName` - Proposed Laws historical names.
3. `KNS_BillInitiator` - Proposed Laws initiators.
4. `KNS_BillHistoryInitiator` - Proposed Laws historical initiators that were removed from the bill.
5. `KNS_BillUnion` - Proposed Laws that were merged with other proposed laws.

To see all the available entities, just go to the following URL: `https://knesset.gov.il/Odata/ParliamentInfo.svc/`.

There are different data sources, to see all the available data sources, just go to the following URL: `https://knesset.gov.il/Odata/`.

To list all the available entities with their fields, just go to the following URL: `https://knesset.gov.il/Odata/ParliamentInfo.svc/$metadata`.

## Data Query
To query the data, we use the ODATA query options. 

For example, to get the latest updated bill from the 25th Knesset use the following query:
```
https://knesset.gov.il/Odata/ParliamentInfo.svc/KNS_Bill?$filter=KnessetNum%20eq%2025&$orderby=LastUpdatedDate%20desc&$top=1
```

More info about ODATA query options can be found [here](https://www.odata.org/getting-started/basic-tutorial/#queryData).
