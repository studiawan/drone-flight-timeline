# DJI Mavic Pro Testing

## Android drone controller

The parser was first tested on the physical Android .DAT image `df021_flight_android_physical.001`. The log2timeline process completed without errors and psort extraction yielded 19.585 events. As summarized in Table 4.1, the parser successfully identified .DAT logs within the `/media/0/DJI/dji.go.v4/FlightRecord/MCDatFlightRecords/` directory with all columns parsed correctly. Further validation on the specific .DAT artifact `17-08-29 12-58-45_FLY005.DAT` produced 6.100 discrete event. Table 4.2 capturing GPS coordinates, altitude, and acceleration levels without errors.

Table 4.1-txt present sample flight data extracted from the Android forensic image. Each row contains longitude, latitude, height, speed, distance, and flight time. The *display_name* column in Table 4.3-txt shows all records originate from Android .TXT artifact `DJIFlightRecord_2017-08-29_[12-05-27].txt` demonstrating consistent parser performance. Artifact locations are preserved within the image's directory structure, as shown in the *display_name* column.

**Table 4.1: DJI Mavic Pro Android .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T11:58:37. 512739+00:00 | Metadata Modification Time | File stat | `EXT:/data/dji.go.v4/app_bugly/sys_log_1504033117518688.txt` Type: file Owner identifier: 10109 Group identifier: 10109 Mode: 0o600 Number of links: 1 | filestat | `EXT:/data/dji.go.v4/app_bugly/sys_log_1504033117518688.txt` |
| 2017-08-29T11:58:37. 532758+00:00 | Content Modification Time | File stat | `EXT:/data/dji.go.v4/app_crashrecord/1004` Type: file Owner identifier: 10109 Group identifier: 10109 Mode: 0o600 Number of links: 1 | filestat | `EXT:/data/dji.go.v4/app_crashrecord/1004` |
| 2017-08-29T11:58:37. 532758+00:00 | Metadata Modification Time | File stat | `EXT:/data/dji.go.v4/app_crashrecord/1004` Type: file Owner identifier: 10109 Group identifier: 10109 Mode: 0o600 Number of links: 1 | filestat | `EXT:/data/dji.go.v4/app_crashrecord/1004` |

**Table 4.2: DJI Mavic Pro Android .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T11:58:38. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2163995 Latitude: 39.9612154 Height: 2481.343 X_velocity: 0.01 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Pro/Android/17-08-29-12-58-45_FLY005.DAT` |
| 2017-08-29T11:58:38. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2163995 Latitude: 39.9612154 Height: 2481.348 X_velocity: 0.0 Y_velocity: 0.01 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Pro/Android/17-08-29-12-58-45_FLY005.DAT` |
| 2017-08-29T11:58:38. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2163996 Latitude: 39.9612154 Height: 2481.349 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Pro/Android/17-08-29-12-58-45_FLY005.DAT` |

**Table 4.1-txt: DJI Mavic Pro Android .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T11:05:27. 929000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21639931363029 Latitude: 39.9612000043031 Height: 0m Distance: 1.2273155450820923m Speed: 0.0m/s | drone_binary | `EXT:/media/0/DJI/dji.go.v4/FlightRecord/DJIFlightRecord_2017-08-29_[12-05-27].txt` |
| 2017-08-29T11:05:28. 200000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2163993056453 Latitude: 39.9612000046581 Height: 0m Distance: 1.226873517036438m Speed: 0.0m/s | drone_binary | `EXT:/media/0/DJI/dji.go.v4/FlightRecord/DJIFlightRecord_2017-08-29_[12-05-27].txt` |
| 2017-08-29T11:05:28. 305000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2163992949495 Latitude: 39.96119995506872 Height: 0m Distance: 1.227990984916687m Speed: 0.0m/s | drone_binary | `EXT:/media/0/DJI/dji.go.v4/FlightRecord/DJIFlightRecord_2017-08-29_[12-05-27].txt` |

**Table 4.3-txt: DJI Mavic Pro Android .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T11:05:27. 929000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21639931363029 Latitude: 39.9612000043031 Height: 0m Distance: 1.2273155450820923m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-08-29_[12-05-27].txt` |
| 2017-08-29T11:05:28. 200000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2163993056453 Latitude: 39.9612000046581 Height: 0m Distance: 1.226873517036438m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-08-29_[12-05-27].txt` |
| 2017-08-29T11:05:28. 305000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2163992949495 Latitude: 39.96119995506872 Height: 0m Distance: 1.227990984916687m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-08-29_[12-05-27].txt` |

**Table 4.3: DJI Mavic Pro iOS .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-25T19:44:17. 890350+00:00 | Content Modification Time | Plist file | `/ActivityBaseDates/com.apple.suggestd.vacuum` | `plist/plist_default` | `OS:/mnt/d/artifact/DJI_Mavic_Pro/iOS/df021_flight_ios_backup/DF021_MC06_iOS_decrypted/RootDomain/Library/Preferences/com.apple.xpc.activity2.plist` |
| 2017-08-26T10:16:07. 293181+00:00 | Content Modification Time | Plist file | /LastLaunchDate | `plist/plist_default` | `OS:/mnt/d/artifact/DJI_Mavic_Pro/iOS/df021_flight_ios_backup/DF021_MC06_iOS_decrypted/AppDomain-com.dji.go/Library/Preferences/com.dji.go.plist` |
| 2017-08-26T10:24:38. 437774+00:00 | Content Modification Time | Plist file | `/List of known networks/lastJoined` | `plist/plist_default` | `OS:/mnt/d/artifact/DJI_Mavic_Pro/iOS/df021_flight_ios_backup/DF021_MC06_iOS_decrypted/SystemPreferencesDomain/SystemConfiguration/com.apple.wifi.plist` |

## iOS drone controller

Evaluation of the iOS .DAT image `df021_flight_ios_backup.zip` in Table 4.3 successfully extracted 9.334 events without errors. The .DAT file was located at `/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/`. To verify granular parsing, the individual file `2017-08-29_12-43-38_FLY005.DAT` was processed. The results detailed in Table 4.4 yielding 4.311 events with all flight metadata correctly interpreted.

**Table 4.4: DJI Mavic Pro iOS .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T11:43:37. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2162953 Latitude: 39.9612253 Height: 2484.295 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/2017-08-29_12-43-38_FLY005.DAT` |
| 2017-08-29T11:43:37. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2162955 Latitude: 39.9612257 Height: 2484.417 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/2017-08-29_12-43-38_FLY005.DAT` |
| 2017-08-29T11:43:37. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2162959 Latitude: 39.961226 Height: 2484.571 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: -0.01 | dji_logfile | `OS:/mnt/d/artifact/2017-08-29_12-43-38_FLY005.DAT` |

Table 4.3-andro txt present sample flight data extracted from the iOS .TXT forensic image. The *display_name* column indicates all records originate from an identical artifact `DJIFlightRecord_2017-08-29_[11-49-33].txt`. Although the iOS image contained three artifact files, sampling in Table 4.4-txt resulting identical appearances in all tables. The data includes high-precision longitude/latitude coordinates, metric height/speed/distance, and a standardized datetime column based on system time zone.

## Drone internal memory

The iOS drone internal memory image `SDCard_Internal_Intact.001` was processed to retrieve data stored directly on the aircraft. The parser extracting 104.576 events in Table 4.5 and identify multiple .DAT files in the root directory drone's internal memory. Furthermore, Table 4.6 shows targeted test on the artifact `FLY006.DAT` from the drone's internal memory successful extract 7.176 records without error.

**Table 4.3-andro txt: DJI Mavic Pro iOS .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T10:49:35. 204000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21638577285235 Latitude: 39.96120683563408 Height: 0m Distance: 0.1356412172317505m Speed: 2.8284270763397217m/s | drone_binary | `OS:/mnt/d/7f05ad1235cea98920b1112ef14ddd9fdded744a_extract_1746080802362/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2017-08-29_[11-49-33].txt` |
| 2017-08-29T10:49:35. 306000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21638606425957 Latitude: 39.96120660664555 Height: 1m Distance: 0.1712275743484497m Speed: 2.2360680103302m/s | drone_binary | `OS:/mnt/d/7f05ad1235cea98920b1112ef14ddd9fdded744a_extract_1746080802362/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2017-08-29_[11-49-33].txt` |
| 2017-08-29T10:49:35. 405000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21638628921137 Latitude: 39.96120642526294 Height: 2m Distance: 0.1990668773651123m Speed: 1.4142135381698608m/s | drone_binary | `OS:/mnt/d/7f05ad1235cea98920b1112ef14ddd9fdded744a_extract_1746080802362/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2017-08-29_[11-49-33].txt` |

**Table 4.4-txt: DJI Mavic Pro iOS .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-08-29T10:49:35. 204000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21638577285235 Latitude: 39.96120683563408 Height: 0m Distance: 0.1356412172317505m Speed: 2.8284270763397217m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-08-29_[11-49-33].txt` |
| 2017-08-29T10:49:35. 306000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21638606425957 Latitude: 39.96120660664555 Height: 1m Distance: 0.1712275743484497m Speed: 2.2360680103302m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-08-29_[11-49-33].txt` |
| 2017-08-29T10:49:35. 405000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21638628921137 Latitude: 39.96120642526294 Height: 2m Distance: 0.1990668773651123m Speed: 1.4142135381698608m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-08-29_[11-49-33].txt` |

**Table 4.5: DJI Mavic Pro Internal Memory .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-03-16T12:13:15. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -90.1700224 Latitude: 36.9659914 Height: 7722.64 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | TSK:/FLY063.DAT |
| 2018-03-16T12:13:16. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -90.1700224 Latitude: 36.9659914 Height: 7722.64 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | TSK:/FLY063.DAT |
| 2018-03-16T12:13:17. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -90.1700224 Latitude: 36.9659914 Height: 7722.64 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | TSK:/FLY063.DAT |

**Table 4.6: DJI Mavic Pro Internal Memory .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-10-10T09:49:01. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.22082 Latitude: 39.9638475 Height: 2526.508 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/FLY006.DAT` |
| 2017-10-10T09:49:02. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2207819 Latitude: 39.9638514 Height: 2519.397 X_velocity: -0.06 Y_velocity: 0.0 Z_velocity: -0.11 | dji_logfile | `OS:/mnt/d/artifact/FLY006.DAT` |
| 2017-10-10T09:49:02. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2207859 Latitude: 39.9638428 Height: 2518.283 X_velocity: -0.05 Y_velocity: 0.01 Z_velocity: -0.14 | dji_logfile | `OS:/mnt/d/artifact/FLY006.DAT` |
