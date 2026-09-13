# DJI Phantom 4 Testing

## Android drone controller

The drone parser tested on the .DAT `DF005_flight.zip` image successfully extracted a Plaso storage file containing 7,039 events in Table 4.20. The .DAT file was found in the FlightLog folder with a different filename format `FLYXXX.DAT@YY-MM-DD HH-mm-ss-mss`. Android drone flight artifact testing on `FLY004.DAT@17-06-29 11-11-53-822` yielded 4,954 event data records without any errors, as shown in Table 4.21.

**Table 4.20: DJI Phantom 4 Android .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T05:40:44. 000000+00:00 | Content Modification Time | File stat | `ZIP:/FileSystem/Media01/apps/dji.go.v4/f/a/e/7413685996683348.0 Type: file` | filestat | `ZIP:/FileSystem/Media01/apps/dji.go.v4/f/a/e/7413685996683348.0` |
| 2017-06-29T05:40:54. 000000+00:00 | Content Modification Time | File stat | `ZIP:/FileSystem/Media01/apps/dji.go.v4/f/a/e/1713695929331053.0 Type: file` | filestat | `ZIP:/FileSystem/Media01/apps/dji.go.v4/f/a/e/1713695929331053.0` |
| 2017-06-29T05:41:02. 000000+00:00 | Content Modification Time | File stat | `ZIP:/FileSystem/Media01/apps/com.sec.android.daemonapp/db/WeatherClock Type: file` | filestat | `ZIP:/FileSystem/Media01/apps/com.sec.android.daemonapp/db/WeatherClock` |

**Table 4.21: DJI Phantom 4 Android .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T10:11:55. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.216496 Latitude: 39.9611746 Height: 2484.607 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/Android/FLY004.DAT@17-06-29_11-11-53-822` |
| 2017-06-29T10:11:55. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2164961 Latitude: 39.9611746 Height: 2484.609 X_velocity: 0.0 Y_velocity: -0.01 Z_velocity: 0.02 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/Android/FLY004.DAT@17-06-29_11-11-53-822` |
| 2017-06-29T10:12:13. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2164966 Latitude: 39.961174 Height: 2484.479 X_velocity: -0.01 Y_velocity: 0.01 Z_velocity: -0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/Android/FLY004.DAT@17-06-29_11-11-53-822` |

Furthermore, psort was successfully executed on Android .TXT forensic image by generating 5,656 extractions as shown in Table 4.22-txt. Table 4.24-txt demonstrates successfully extracted the binary .TXT artifact `DJIFlightRecord_2017-06-29_[12-39-25].txt`. The resulting timeline confirms the parser's adaptability to variant DJI naming schemas.

**Table 4.22-txt: DJI Phantom 4 Android .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T11:39:28. 385000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648970847946 Latitude: 39.961199612799305 Height: 0m Distance: 0.0m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DF006_flight/FileSystem/Media01/sdcard/DJI/dji.go.v4/FlightRecord/DJIFlightRecord_2017-06-29_[12-39-25].txt` |
| 2017-06-29T11:39:28. 489000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648948640839 Latitude: 39.96119960612798 Height: 0m Distance: 0.01922767609357834m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DF006_flight/FileSystem/Media01/sdcard/DJI/dji.go.v4/FlightRecord/DJIFlightRecord_2017-06-29_[12-39-25].txt` |
| 2017-06-29T11:39:28. 591000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648922050795 Latitude: 39.96119957490419 Height: 1m Distance: 0.01922767609357834m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DF006_flight/FileSystem/Media01/sdcard/DJI/dji.go.v4/FlightRecord/DJIFlightRecord_2017-06-29_[12-39-25].txt` |

**Table 4.24-txt: DJI Phantom 4 Android .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T11:39:28. 385000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648970847946 Latitude: 39.961199612799305 Height: 0m Distance: 0.0m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-06-29_[12-39-25].txt` |
| 2017-06-29T11:39:28. 489000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648948640839 Latitude: 39.96119960612798 Height: 0m Distance: 0.01922767609357834m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-06-29_[12-39-25].txt` |
| 2017-06-29T11:39:28. 591000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648922050795 Latitude: 39.96119957490419 Height: 1m Distance: 0.01922767609357834m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-06-29_[12-39-25].txt` |

**Table 4.22: DJI Phantom 4 iOS .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2025-05-29T05:55:31. 469785+00:00 | Content Modification Time | File stat | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/MC 02 DF005M(2)_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords Type: directory Owner identifier: 1000 Group identifier: 1000 Mode: 0o777 Number of links: 1` | filestat | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/MC 02 DF005M(2)_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords` |
| 2025-05-29T05:55:31. 469785+00:00 | Metadata Modification Time | File stat | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/MC 02 DF005M(2)_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords Type: directory Owner identifier: 1000 Group identifier: 1000 Mode: 0o777 Number of links: 1` | filestat | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/MC 02 DF005M(2)_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords` |
| 2025-05-29T05:55:31. 474780+00:00 | Content Modification Time | File stat | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/MC 02 DF005M(2)_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/2017-06-29_14-51-13_FLY005.DAT Type: file Owner identifier: 1000 Group identifier: 1000 Mode: 0o777 Number of links: 1` | filestat | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/MC 02 DF005M(2)_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/2017-06-29_14-51-13_FLY005.DAT` |

## iOS drone controller

The .DAT `DF005 flight.zip` iOS image processed using log2timeline and psort tools produced a total of 7,258 events, as detailed in Table 4.22. The investigation localized the flight records within the `AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/` directory, named `2017-06-29 14-51-13 FLY005.DAT`. Artifact testing on this file produced 3,466 events without any errors in parsing flight data, as shown in Table 4.23.

Additionally, developed parser successfully extracted 3,705 records from iOS .TXT forensic image, which can be seen in Table 4.23-txt. Table 4.25-txt confirms the parser successfully extracted the binary .TXT artifact `DJIFlightRecord_2017-06-29_[13-00-45].txt`. Overall, the parser demonstrated robust performance across both Android and iOS platforms for .TXT artifact extraction.

**Table 4.23: DJI Phantom 4 iOS .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T13:51:31. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2165133 Latitude: 39.9611989 Height: 2486.06 X_velocity: -0.01 Y_velocity: 0.0 Z_velocity: -0.03 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/2017-06-29_14-51-13_FLY005.DAT` |
| 2017-06-29T13:51:31. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2165136 Latitude: 39.9611992 Height: 2485.994 X_velocity: 0.0 Y_velocity: -0.01 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/2017-06-29_14-51-13_FLY005.DAT` |
| 2017-06-29T13:51:31. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.216514 Latitude: 39.9611993 Height: 2485.959 X_velocity: 0.02 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/iOS/2017-06-29_14-51-13_FLY005.DAT` |

**Table 4.23-txt: DJI Phantom 4 iOS .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T12:00:47. 631000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648689130849 Latitude: 39.96119817079554 Height: 0m Distance: 0.23276323080062866m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/6e40561236de1d331f89cda28a3297d869459984_extract_1749652436460/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2017-06-29_[13-00-45].txt` |
| 2017-06-29T12:00:47. 734000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648666351909 Latitude: 39.96119806900314 Height: 0m Distance: 0.2552697956562042m Speed: 1.0m/s | drone_binary | `OS:/mnt/d/6e40561236de1d331f89cda28a3297d869459984_extract_1749652436460/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2017-06-29_[13-00-45].txt` |
| 2017-06-29T12:00:47. 834000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2164864241324 Latitude: 39.96119794041998 Height: 0m Distance: 0.28021353483200073m Speed: 1.0m/s | drone_binary | `OS:/mnt/d/6e40561236de1d331f89cda28a3297d869459984_extract_1749652436460/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2017-06-29_[13-00-45].txt` |

**Table 4.25-txt: DJI Phantom 4 iOS .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-29T12:00:47. 631000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648689130849 Latitude: 39.96119817079554 Height: 0m Distance: 0.23276323080062866m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-06-29_[13-00-45].txt` |
| 2017-06-29T12:00:47. 734000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21648666351909 Latitude: 39.96119806900314 Height: 0m Distance: 0.2552697956562042m Speed: 1.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-06-29_[13-00-45].txt` |
| 2017-06-29T12:00:47. 834000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2164864241324 Latitude: 39.96119794041998 Height: 0m Distance: 0.28021353483200073m Speed: 1.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2017-06-29_[13-00-45].txt` |

## Drone internal memory

Drone's internal memory image `DF006_microsd_internal.001` was analyzed using log2timeline and psort tool yielding 24.246 metadata events. Table 4.24 shows no errors or warnings by the result of created parser and identified multiple .DAT logs in the root directory. Verification of the `FLY001.DAT` artifact extracted 7.176 records without errors or warnings. Results in Table 4.25 underlying binary structure of the flight records remains compatible with the developed parser.

**Table 4.24: DJI Phantom 4 Drone Internal Memory .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-05-28T19:01:32. 000000+00:00 | Creation Time | File stat | TSK:/FLY001.DAT Type: file Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/FLY001.DAT |
| 2017-05-28T19:01:32. 000000+00:00 | Creation Time | File stat | TSK:/FLY002.DAT Type: file Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/FLY002.DAT |
| 2017-05-28T19:01:32. 000000+00:00 | Creation Time | File stat | TSK:/PARM.LOG Type: file Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/PARM.LOG |

**Table 4.25: DJI Phantom 4 Drone Internal Memory .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-06-28T10:37:08. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -105.1106551 Latitude: 39.9207267 Height: 1462.484 X_velocity: 0.06 Y_velocity: 0.21 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/Drone/FLY001.DAT` |
| 2017-06-28T10:37:08. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -105.1107095 Latitude: 39.9207218 Height: 1468.631 X_velocity: -0.01 Y_velocity: 0.1 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/Drone/FLY001.DAT` |
| 2017-06-28T10:37:08. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -105.1107556 Latitude: 39.9207178 Height: 1473.943 X_velocity: 0.01 Y_velocity: 0.3 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Phantom_4/Drone/FLY001.DAT` |
