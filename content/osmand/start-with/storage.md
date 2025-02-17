---
title: Storage
intro: How to configure, access and change data storage for maps, tracks and other personal data
versions: '*'
---

- Favorite backups
- Folder structure (iOS / Android)
- 

## Data storage folder
Memory name | Permission access
|-----------|------------------|
| Internal app memory | Only OsmAnd app has access to its data and none of external apps / pc has access| 
| Shared memory | Multiple OsmAnd apps could have access and multiple external apps |
| External storage 1 | Only 1 OsmAnd app has access and Admin apps and USB |
| External storage N | SDCard: Only 1 OsmAnd app has access and Admin apps and USB |
| Multiuser storage | Only 1 OsmAnd app has access but it's shared between multiple Android users |
| Manually specified | Depends on the path |


## Copy raster map package created on PC 

Map package can be saved in two formats: [SQ Lite and Metainfo](/osmand/map/online-raster-maps#sqlite-vs-metainfo-sources).

Next, you need to move your map package file(s) to OsmAnd-tiles directory:

For **Android** OsmAnd - you need to access storage to copy file(s) from PC to the device folder BASE_OSMAND_STORAGE/tiles_ or you can click the file on your email, cloud, or messenger, download it and choose OsmAnd app to open. Map package is added automatically to your online maps list in OsmAnd.

![Import sqlitedb Android](/assets/images/plugins/online-maps/import-sqlitedb-android.png)

For **iOS** OsmAnd - you need to click the file on your iTunes or messenger, download it and choose OsmAnd app to open. Map package is added automatically to your online maps list in OsmAnd.

![Import sqlitedb iOS](/assets/images/plugins/online-maps/import-sqlitedb-ios.png)

(for the Android version only)

## In order to move the OsmAnd home (maps) folder to an external SD card:

-   Go to `Settings (on the start screen) --> OsmAnd Settings --> Data
    storage folder`
-   Change the value to a path pointing to the external SD card, on many
    Android systems it may contain `/storage/extSdCard` or similar.
    Please note that some versions of Android strictly limit your choice
    of which path will be write-accessible for apps.
-   You are then asked if the contents of the OsmAnd data folder should be moved from
    internal memory to the external SD card.
    You may also perform this manually using a built-in file manager app on the device, or via
    connecting the device to a computer as external storage and performing the move from there.

## How do I use my SD card with OsmAnd under Android 4.4+ and 5?

If you update your Android to version 4.4.x, you will experience a known
Android issue with the `WRITE_EXTERNAL_STORAGE` permission: Android has
changed the rules so that from now on no application can write to the
external SD card anywhere outside its new standard folder
`Android/data/[PACKAGE-NAME]`. If OsmAnd was installed prior to updating
your device to Android 4.4.x, it will continue to work (read-only) with
the old, non-standard osmand folder, but won't be able to update any map
and other files there.

Solutions:

-   Move OsmAnd's data folder osmand to the internal storage. \
     **Drawback:** Internal storage can be rather small.
-   Move OsmAnd's data folder osmand into its standard SD folder, \
    for OsmAnd+ : `(extSdCard)/Android/data/net.osmand.plus/files` \
    for OsmAnd : `(extSdCard)/Android/data/net.osmand/files` \
     **Caution:** Whenever you uninstall OsmAnd now, all your data will
    be erased as well! (Unless you unmount your SD card, or rename the
    net.osmand(.plus) folder before de-installation.)

If you manually want to perform the necessary copies/moves, either use a
PC to perform this action on the SD card, or on the device itself use
the file manager tool **which came pre-installed with your Android**
(only these methods will have the necessary write permission). All copy operations
may also be invoked in OsmAnd itself via `Menu/Settings/General/Data
storage folder` but the copy operations may take a long time or result in
errors (e.g. if the SD card is too full).
