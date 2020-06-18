# bloomsky-pwswx-data-integration
### Azure logic app for API based ETL integration between Bloomsky &amp; PWSWeather

This Azure logic app integration was created out of a need to get Bloomsky (Sky 2 & Storm) data into PWSWeather (AerisWeather) so that it can be used by my Rachio irrigation controller for weather intelligence.  

By default, this workflow fires every 10 minutes and should only cost ~$0.65/month.

Assuming you have an active Azure subscription, deploy the template, then set these configuration parameters:

- CFG_BSKY-API-KEY - This is your Bloomsky API key (retrieve from dashboard.bloomsky.com and click 'Developers')<br>
- CFG_PWSWX-PASSWORD - This is the password for your PWSWeather account (create account at https://www.pwsweather.com/register/)
- CFG_PWSWX-STATIONID - This is the station ID you registered after creating a PWSWeather account (note, this is NOT your PWSWeather login ID!)
- CFG_PWSWX-SWTYPE - Arbitrary field for defining system sending data.. default value should be fine.

Once set, enable the logic app and monitor for success.  This is simplistic right now, so I don't have any error handling or anything in place, but will add that at some point.  It will take a few days of pushing data to PWSWeather before you will show up on the 'map', as they validate data quality.
