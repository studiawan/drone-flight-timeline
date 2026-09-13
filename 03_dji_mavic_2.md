# DJI Mavic 2 Testing

## Android drone controller

.DAT execution against the `Android_Logical.zip` forensic image successfully generated a Plaso storage file with zero warnings. Subsequent processing via psort yielded 6,511 events as shown in Table 4.12. The .DAT file was located at `/DJI/dji.go.v4/FlightRecord/MCDatFlightRecords/`. Targeted analysis of the extracted artifact `18-09-26-02-06-00_FLY012.DAT` in Table 4.13 produced 4,194 records, confirming successful extraction of all flight record data.

**Table 4.12: DJI mavic 2 android .DAT image extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-09-26T05:24:24. 000000+00:00 | Content Modification Time | File stat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/UP_WIFI_PR/log-2018-09-26.log Type: file` | filestat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/UP_WIFI_PR/log-2018-09-26.log` |
| 2018-09-26T05:24:26. 000000+00:00 | Content Modification Time | File stat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/MultiNetworkLog/log-2018-09-26.log Type: file` | filestat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/MultiNetworkLog/log-2018-09-26.log` |
| 2018-09-26T05:24:26. 000000+00:00 | Content Modification Time | File stat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/NFZ/log-2018-09-26.log Type: file` | filestat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/NFZ/log-2018-09-26.log` |

**Table 4.13: DJI Mavic 2 Android .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-09-26T11:05:58. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9513891 Latitude: 40.0121667 Height: 1562.715 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/Android/18-09-26-02-06-00_FLY012.DAT` |
| 2018-09-26T11:05:58. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9513891 Latitude: 40.0121667 Height: 1562.719 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/Android/18-09-26-02-06-00_FLY012.DAT` |
| 2018-09-26T11:05:58. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9513891 Latitude: 40.0121667 Height: 1562.724 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/Android/18-09-26-02-06-00_FLY012.DAT` |

The developed parser also successfully extracted .TXT artifacts from the Android forensic image which can be shown in Table 4.10-txt. Furthermore, Table 4.12-txt demonstrates the extracted specific Android artifact `DJIFlightRecord_2018-06-19_[14-50-34].txt`, validating the parser's capability to correctly extract binary .TXT artifacts from the DJI Mavic 2 drone.

**Table 4.10-txt: DJI Mavic 2 Android .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T11:50:36. 960000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646783122232 Latitude: 39.96119769686116 Height: 0m Distance: 0.08493509143590927m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/mobile_android_logical-20250507T061610Z-001/mobile_android_logical/Android_Logical/Android_Logical/sdcard/DJI/dji.pilot/FlightRecord/DJIFlightRecord_2018-06-19_[14-50-34].txt` |
| 2018-06-19T11:50:37. 165000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646777301935 Latitude: 39.96119749396617 Height: 0m Distance: 0.1087360680103302m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/mobile_android_logical-20250507T061610Z-001/mobile_android_logical/Android_Logical/Android_Logical/sdcard/DJI/dji.pilot/FlightRecord/DJIFlightRecord_2018-06-19_[14-50-34].txt` |
| 2018-06-19T11:50:37. 580000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2164678427009 Latitude: 39.96119762280709 Height: 0m Distance: 0.09322743862867355m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/mobile_android_logical-20250507T061610Z-001/mobile_android_logical/Android_Logical/Android_Logical/sdcard/DJI/dji.pilot/FlightRecord/DJIFlightRecord_2018-06-19_[14-50-34].txt` |

**Table 4.12-txt: DJI Mavic 2 Android .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T11:50:36. 960000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646783122232 Latitude: 39.96119769686116 Height: 0m Distance: 0.08493509143590927m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[14-50-34].txt` |
| 2018-06-19T11:50:37. 165000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646777301935 Latitude: 39.96119749396617 Height: 0m Distance: 0.1087360680103302m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[14-50-34].txt` |
| 2018-06-19T11:50:37. 580000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2164678427009 Latitude: 39.96119762280709 Height: 0m Distance: 0.09322743862867355m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[14-50-34].txt` |

## iOS drone controller

Testing on the .DAT `iOS_Backup.zip` image resulted in 8,441 processed data events. The results in Table 4.14 show the storage was successfully extracted flight logs in the `/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/` path. For granular verification, the individual artifact `2018-09-26_11-52-50_FLY012.DAT` was analyzed, generating 2,936 events. The results in Table 4.15 confirmed consistent parsing performance on the iOS platform with no warnings.

**Table 4.14: DJI Mavic 2 iOS .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-09-26T11:03:44. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9513867 Latitude: 40.0121631 Height: 1563.119 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/iOS/iOS_Backup_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/2018-09-26_11-52-50_FLY012.DAT` |
| 2018-09-26T11:03:44. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9513867 Latitude: 40.0121632 Height: 1563.124 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/iOS/iOS_Backup_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/2018-09-26_11-52-50_FLY012.DAT` |
| 2018-09-26T11:03:44. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9513867 Latitude: 40.0121632 Height: 1563.127 X_velocity: 0.0 Y_velocity: 0.01 Z_velocity: 0.01 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/iOS/iOS_Backup_decrypted/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/2018-09-26_11-52-50_FLY012.DAT` |

**Table 4.15: DJI Mavic 2 iOS .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-09-26T10:53:09. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9592185 Latitude: 40.0119094 Height: 1810.899 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/iOS/2018-09-26_11-52-50_FLY012.DAT` |
| 2018-09-26T10:53:10. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.951225 Latitude: 40.0122727 Height: 1619.662 X_velocity: 0.02 Y_velocity: 0.03 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/iOS/2018-09-26_11-52-50_FLY012.DAT` |
| 2018-09-26T10:53:10. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -104.9512263 Latitude: 40.0122722 Height: 1618.876 X_velocity: -0.01 Y_velocity: 0.01 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_2/iOS/2018-09-26_11-52-50_FLY012.DAT` |

**Table 4.11-txt: DJI Mavic 2 iOS .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-09-26T10:57:41. 740000+00:00 | Creation Time | DJI Flight Log | Longitude: -104.95136077377947 Latitude: 39.961? Wait, this seems incorrect. Please check. | drone_binary | `OS:/mnt/d/910c76c14ed64ee886ffdd2611665d842aec939b_extract_1747642580086/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2018-09-26_[11-57-33].txt` |
| 2018-09-26T10:57:41. 280000+00:00 | Creation Time | DJI Flight Log | Longitude: -104.95136058514116 Latitude: 40.01222680578811 Height: 0m Distance: 0.386337548494339m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/910c76c14ed64ee886ffdd2611665d842aec939b_extract_1747642580086/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2018-09-26_[11-57-33].txt` |
| 2018-09-26T10:57:41. 388000+00:00 | Creation Time | DJI Flight Log | Longitude: -104.95136049053144 Latitude: 40.01222670133592 Height: 1m Distance: 0.40047332644462585m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/910c76c14ed64ee886ffdd2611665d842aec939b_extract_1747642580086/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2018-09-26_[11-57-33].txt` |

## Drone internal memory

The drone's internal memory `SDCard_Internal_Aircraft_Intact.001` was analyzed to determine the presence of flight logs. Table 4.16 shows no error and proprietary .DAT flight records were detected. While the `log2timeline` and `psort` operations resulting timeline of 63 events consisted entirely of system-level metadata. This funding suggesting flight record for this session was stored on the mobile controller.

As presented in Table 4.11-txt, the parser successfully extracted 8,677 flight records of the DJI Mavic 2 drone from the .TXT iOS forensic image. Table 4.13-txt shows the results for the iOS artifact `DJIFlightRecord_2018-09-26_[11-57-33].txt`. This further confirms that the developed parser can accurately extract DJI Mavic 2 binary .TXT flight artifact files across both platforms.

**Table 4.13-txt: DJI Mavic 2 iOS .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-09-26T10:57:41. 740000+00:00 | Creation Time | DJI Flight Log | Longitude: -104.95136077377947 Latitude: 40.01222686710559 Height: 0m Distance: 0.36810302734375m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-09-26_[11-57-33].txt` |
| 2018-09-26T10:57:41. 280000+00:00 | Creation Time | DJI Flight Log | Longitude: -104.95136058514116 Latitude: 40.01222680578811 Height: 0m Distance: 0.386337548494339m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-09-26_[11-57-33].txt` |
| 2018-09-26T10:57:41. 388000+00:00 | Creation Time | DJI Flight Log | Longitude: -104.95136049053144 Latitude: 40.01222670133592 Height: 1m Distance: 0.40047332644462585m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-09-26_[11-57-33].txt` |

**Table 4.16: DJI Mavic 2 Internal Memory .DAT Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-08-15T10:00:00. 000000+00:00 | Last Access Time | File stat | TSK:/LOST.DIR Type: directory Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/LOST.DIR |
| 2018-08-15T10:00:00. 000000+00:00 | Last Access Time | File stat | TSK:/MISC Type: directory Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/MISC |
| 2018-08-15T10:00:00. 000000+00:00 | Last Access Time | File stat | TSK:/MISC/GIS Type: directory Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/MISC/GIS |

**Table 4.17: DJI Mavic 2 Enterprise Android .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-11-20T08:05:36. 000000+00:00 | Content Modification Time | File stat | `ZIP:/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/LOG/CACHE/LeftActionBar/log-2018-11-20.log Type: file` | filestat | `ZIP:/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/LOG/CACHE/LeftActionBar/log-2018-11-20.log` |
| 2018-11-20T08:05:36. 000000+00:00 | Content Modification Time | File stat | `ZIP:/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/deviceCfg.xml Type: file` | filestat | `ZIP:/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/deviceCfg.xml` |
| 2018-11-20T08:05:36. 000000+00:00 | Content Modification Time | File stat | `ZIP:/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/deviceCfg_verify.xml Type: file` | filestat | `ZIP:/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/deviceCfg_verify.xml` |
