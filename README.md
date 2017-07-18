## Synopsis

This is a splunk app contains all of the index definitions and their related settings/parameters. 

## Code Example

Index definitions:

```
# CUSTOMER INDEXES

[test]
homePath   = volume:primary/test/db
coldPath   = volume:primary/test/colddb
thawedPath = $SPLUNK_DB/test/thaweddb
maxTotalDataSizeMB = 50000
frozenTimePeriodInSecs = 2592000

[syslog]
homePath   = volume:primary/syslog/db
coldPath   = volume:primary/syslog/colddb
thawedPath = $SPLUNK_DB/syslog/thaweddb
```

## Motivation

This app allows the splunk administrator to modify all index settings in one location instead of per-app.

## Installation

This app should be placed in /opt/splunk/etc/apps  - this assumes the contents of "spl_indexer_vol" has already been installed to define data volume locations. If this is not the case, modifications will need to be made to all homePath and coldPath locations to correspond to an existing data path on the system.