# Windows and IANA time zones
PostgreSQL function to convert between Windows and IANA time zone names
```sql
FUNCTION timezone_names(windows_tz text DEFAULT NULL, iana_tz text DEFAULT NULL, territory text DEFAULT NULL)
RETURNS TABLE(windows_timezone text, liana_timezone text, territory_abbrev text)
```
Examples:
```sql
-- List of all Windows and IANA time zones and territory codes (as to store in a table)
select * from timezone_names();
-- Data for Bulgaria by IANA time zone name
select * from timezone_names(iana_tz => 'Europe/Sofia');
 -- Data for Bulgaria by Windows time zone name and territory
select * from timezone_names(windows_tz => 'FLE Standard Time', territory => 'BG');
```
