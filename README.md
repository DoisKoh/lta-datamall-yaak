# LTA DataMall Yaak Collection

A [Yaak](https://yaak.app/) workspace containing all 30 [LTA DataMall](https://datamall.lta.gov.sg/) API endpoints, ready to use for testing and development.

## What's Included

All endpoints from the LTA DataMall API User Guide (v6.7), organized into folders:

| Folder | Endpoints |
|---|---|
| **Public Transport** | Bus Arrival, Bus Services, Bus Routes, Bus Stops, Passenger Volume (Bus Stops, OD Bus Stops, OD Train Stations, Train Stations), Taxi Availability, Taxi Stands, Train Service Alerts, Facilities Maintenance, Station Crowd Density (Real Time, Forecast), Planned Bus Routes |
| **Traffic** | Carpark Availability, Estimated Travel Times, Faulty Traffic Lights, Planned Road Openings, Approved Road Works, Traffic Images, Traffic Incidents, Traffic Speed Bands, VMS/EMAS, Traffic Flow, Flood Alerts |
| **Active Mobility** | Bicycle Parking |
| **Geospatial** | Geospatial Whole Island |
| **Electric Vehicle** | EV Charging Points, EV Charging Points Batch |

## Setup

1. Clone this repo and open the workspace in Yaak (or point Yaak's git sync to it).
2. Set the `AccountKey` environment variable to your LTA DataMall API key.
   - Get a free API key at https://datamall.lta.gov.sg/content/datamall/en/request-for-api.html
3. If using encryption, place your Yaak encryption key in `.yaak-encryption-key` (gitignored).

The workspace has a global `AccountKey` header configured, so all requests inherit it automatically.

## Pagination

Most APIs return 500 records per call. Use the `$skip` query parameter to paginate (e.g. `$skip=500` for the next batch). Each request has `$skip` pre-configured but disabled by default.

## Reference

- [LTA DataMall API User Guide (PDF)](docs/LTA_DataMall_API_User_Guide.pdf)
- [LTA DataMall Portal](https://datamall.lta.gov.sg/)
