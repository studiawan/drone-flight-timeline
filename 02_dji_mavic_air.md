# DJI Mavic Air Testing

## Android drone controller

The parser was applied to the `Android_Logical.zip` .DAT image, successfully generating a Plaso storage file without warnings. Extraction using psort in Table 4.7 yielded 4,871 events, identifying .DAT artifacts within the `/sdcard/DJI/dji.go.v4/FlightRecord/MCDatFlightRecords/` directory. Targeted testing on the extracted artifact `18-06-19_02-47-38_FLY057.DAT` produced 3,231 event data records. Timeline results in Table 4.8 demonstrated full data recovery, including longitude, latitude, height, and acceleration levels (x, y, z).

**Table 4.7: DJI Mavic Air Android .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T06:09:54. 000000+00:00 | Content Modification Time | File stat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/DebugNotConnect/log-2018-06-19.log Type: file` | filestat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/DebugNotConnect/log-2018-06-19.log` |
| 2018-06-19T06:09:54. 000000+00:00 | Content Modification Time | File stat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/FLAG_NO_VIDEO_SIGNAL/log-2018-06-19.log Type: file` | filestat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/FLAG_NO_VIDEO_SIGNAL/log-2018-06-19.log` |
| 2018-06-19T06:09:54. 000000+00:00 | Content Modification Time | File stat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/LiveStreaming/log-2018-06-19.log Type: file` | filestat | `ZIP:/Android_Logical/sdcard/DJI/dji.go.v4/LOG/CACHE/LiveStreaming/log-2018-06-19.log` |

**Table 4.8: DJI Mavic Air Android .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T11:47:37. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2166723 Latitude: 39.9613782 Height: 2488.198 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Air/Android/18-06-19-02-47-38_FLY057.DAT` |
| 2018-06-19T11:47:38. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2166723 Latitude: 39.9613782 Height: 2488.198 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Air/Android/18-06-19-02-47-38_FLY057.DAT` |
| 2018-06-19T11:47:39. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2166723 Latitude: 39.9613782 Height: 2488.198 X_velocity: 0.0 Y_velocity: 0.0 Z_velocity: 0.0 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Air/Android/18-06-19-02-47-38_FLY057.DAT` |

Additionally, the parser successfully extracted 713 events of Android .TXT forensic image in Table 4.14-txt. The developed parser also successfully extracted and read 1845 flight data records from targeted binary TXT artifact files `DJIFlightRecord_2018-06-19_[14-50-34].txt`. The results in Table 4.16-txt demonstrating parsers ability to read drone flight records from the DJI Mavic Air.

**Table 4.14-txt: DJI Mavic Air Android.TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2017-10-10T09:02:25. 766000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21631313134716 Latitude: 39.96126314419996 Height: 0m Distance: 0.03837350755929947m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/mobile_android_logical-20250507T063657Z-001/mobile_android_logical/Android_Logical/Android_Logical/sdcard/DJI/dji.pilot/FlightRecord/DJIFlightRecord_2017-10-10_[10-02-22].txt` |
| 2017-10-10T09:02:25. 868000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21631309160018 Latitude: 39.961263316217384 Height: 0m Distance: 0.05776325985789299m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/mobile_android_logical-20250507T063657Z-001/mobile_android_logical/Android_Logical/Android_Logical/sdcard/DJI/dji.pilot/FlightRecord/DJIFlightRecord_2017-10-10_[10-02-22].txt` |
| 2017-10-10T09:02:25. 972000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21631323542528 Latitude: 39.96126345955628 Height: 1m Distance: 0.07311757653951645m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/mobile_android_logical-20250507T063657Z-001/mobile_android_logical/Android_Logical/Android_Logical/sdcard/DJI/dji.pilot/FlightRecord/DJIFlightRecord_2017-10-10_[10-02-22].txt` |

**Table 4.16-txt: DJI Mavic Air Android .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T11:50:37. 385000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646750129996 Latitude: 39.961197091132334 Height: 0m Distance: 0.1591688096523285m Speed: 0.1414213627576828m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[14-50-34].txt` |
| 2018-06-19T11:50:37. 489000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646736003898 Latitude: 39.961196969210874 Height: 1m Distance: 0.17730006575584412m Speed: 0.1414213627576828m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[14-50-34].txt` |
| 2018-06-19T11:50:37. 593000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21646722906246 Latitude: 39.96119679674023 Height: 1m Distance: 0.19949018955230713m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[14-50-34].txt` |

## iOS drone controller

Analysis of the `MC 04 iOS.zip` image successfully recovered 23,131 events, with flight logs located in the `/AppDomain-com.dji.go/Documents/FlightRecords/MCDatFlightRecords/` directory. Details of the iOS image parsing results using the psort tool can be seen in Table 4.9. Artifact testing on `2018-04-19_11-24-49_FLY029.DAT` produced 1,024 events. Table 4.10 shows the storage successfully extracted all forensic columns without any errors, confirming that encryption and structural logic are consistent with the DJI Mavic Pro extraction on iOS. Concurrently, Table 4.15-txt and Table 4.17-txt confirm the parser's capability to effectively extract flight records from iOS .TXT image and artifacts `DJIFlightRecord_2018-06-19_[12-25-59].txt`.

**Table 4.9: DJI Mavic Air iOS .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-04-19T09:04:03. 633144+00:00 | Content Modification Time | Plist file | `/ParsecFirstUse OfTheDay_news` | plist/plist _default | `OS:/mnt/d/artifact/DJI_Mavic_Air/iOS/MC04iOS_decrypted/HomeDomain/Library/Preferences/com.apple.parsecd.plist` |
| 2018-04-19T09:42:41. 645029+00:00 | Content Modification Time | Plist file | `/ActivityBase Dates/com.apple. dataaccess. dataaccessd.fetch. 65C5F5A5-664A-4D9B-AB75- 1DDF8A991C5E` | plist/plist _default | `OS:/mnt/d/artifact/DJI_Mavic_Air/iOS/MC04iOS_decrypted/RootDomain/Library/Preferences/com.apple.xpc.activity2.plist` |
| 2018-04-19T10:22:52. 249970+00:00 | Content Modification Time | Plist file | `/ActivityBase Dates/com.apple. GeoServices.Update Experiment.Execute` | plist/plist _default | `OS:/mnt/d/artifact/DJI_Mavic_Air/iOS/MC04iOS_decrypted/RootDomain/Library/Preferences/com.apple.xpc.activity2.plist` |

**Table 4.10: DJI Mavic Air iOS .DAT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-04-19T10:24:49. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2165154 Latitude: 39.9612828 Height: 2481.916 X_velocity: 0.01 Y_velocity: 0.01 Z_velocity: -0.04 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Air/iOS/2018-04-19_11-24-49_FLY029.DAT` |
| 2018-04-19T10:24:49. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2165154 Latitude: 39.9612829 Height: 2481.919 X_velocity: 0.0 Y_velocity: -0.01 Z_velocity: -0.04 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Air/iOS/2018-04-19_11-24-49_FLY029.DAT` |
| 2018-04-19T10:24:49. 000000+00:00 | Recorded Time | DJI Mavic DAT Log | Longitude: -106.2165154 Latitude: 39.9612829 Height: 2481.92 X_velocity: -0.01 Y_velocity: 0.0 Z_velocity: -0.04 | dji_logfile | `OS:/mnt/d/artifact/DJI_Mavic_Air/iOS/2018-04-19_11-24-49_FLY029.DAT` |

**Table 4.15-txt: DJI Mavic Air iOS .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T11:26:01. 557000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.2164526012044 Latitude: 39.96119286744786 Height: 0m Distance: 0.11589385569095612m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/7f05ad1235cea98920b1112ef14ddd9fdded744a_extract_1747648204343/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2018-06-19_[12-25-59].txt` |
| 2018-06-19T11:26:01. 658000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21645253445851 Latitude: 39.96119289019725 Height: 0m Distance: 0.12211959809064865m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/7f05ad1235cea98920b1112ef14ddd9fdded744a_extract_1747648204343/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2018-06-19_[12-25-59].txt` |
| 2018-06-19T11:26:01. 761000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21645249461656 Latitude: 39.961192949588416 Height: 0m Distance: 0.1295454502105713m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/7f05ad1235cea98920b1112ef14ddd9fdded744a_extract_1747648204343/AppDomain-com.dji.go/Documents/FlightRecords/DJIFlightRecord_2018-06-19_[12-25-59].txt` |

**Table 4.17-txt: DJI Mavic Air iOS .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-06-19T11:29:41. 685000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21645434933404 Latitude: 39.96119298253288 Height: 0m Distance: 0.3377384841442108m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[12-29-38].txt` |
| 2018-06-19T11:29:41. 788000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21645448931716 Latitude: 39.96119319641253 Height: 0m Distance: 0.36434558033943176m Speed: 0.20000000298023224m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[12-29-38].txt` |
| 2018-06-19T11:29:41. 889000+00:00 | Creation Time | DJI Flight Log | Longitude: -106.21645452590784 Latitude: 39.961193356004976 Height: 1m Distance: 0.38236337900161743m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-06-19_[12-29-38].txt` |

**Table 4.11: DJI Mavic Air Internal Memory .DAT Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-01-13T10:00:00. 000000+00:00 | Last Access Time | File stat | TSK:/LOST.DIR Type: directory Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/LOST.DIR |
| 2018-01-13T10:00:00. 000000+00:00 | Last Access Time | File stat | TSK:/MISC Type: directory Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/MISC |
| 2018-01-13T10:00:00. 000000+00:00 | Last Access Time | File stat | TSK:/MISC/GIS Type: directory Owner identifier: 0 Group identifier: 0 Mode: 0o777 Number of links: 1 | filestat | TSK:/MISC/GIS |

## Drone internal memory

The drone's internal memory image `df048_Mavic_Air_Internal_Memory.E01` was processed to identify flights record data. `Log2timeline` and `psort` operations generated timeline of 104.576 events. The results in Table 4.11 revealed an absence of .DAT flight logs containing actual recording data. This suggests for DJI Mavic Air dataset flight records were either not retained on the internal storage or were stored in a non-standardized location not captured during the logical acquisition.
