# DJI Mavic 2 Enterprise Testing

## Android drone controller

The parser successfully processed the .DAT `mobile_android_logical.zip` image, producing forensic timelines with 605 events containing combination of files in the Android image. However, detailed analysis of the exported CSV files in Table 4.17 revealed an absence of .DAT flight logs within the standard application directories. Despite the absence of .DAT logs, psort was successfully executed on the Android .TXT forensic image, generating 1,809 extractions as shown in Table 4.18-txt. Furthermore, Table 4.20-txt demonstrates that the developed parser successfully extracted 5,358 events from binary .TXT artifact `DJIFlightRecord_2018-11-20_[14-55-49].txt`.

**Table 4.18-txt: DJI Mavic 2 Enterprise Android .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-11-20T14:55:54. 333000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26224365300385 Latitude: 39.8919448310861 Height: 0m Distance: 0.35588911175727844m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/mobile_android-20250507T074940Z-001/mobile_android/mobile_android_logical/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/FlightRecord/DJIFlightRecord_2018-11-20_[14-55-49].txt` |
| 2018-11-20T14:55:54. 434000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26224365300385 Latitude: 39.8919448310861 Height: 0m Distance: 0.35588911175727844m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/mobile_android-20250507T074940Z-001/mobile_android/mobile_android_logical/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/FlightRecord/DJIFlightRecord_2018-11-20_[14-55-49].txt` |
| 2018-11-20T14:55:54. 535000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26224343122725 Latitude: 39.89194497887398 Height: 0m Distance: 0.3819965422153473m Speed: 0.1414213627576828m/s | drone_binary | `OS:/mnt/d/mobile_android-20250507T074940Z-001/mobile_android/mobile_android_logical/mobile_android_logical/Media01/sdcard/DJI/com.dji.industry.pilot/FlightRecord/DJIFlightRecord_2018-11-20_[14-55-49].txt` |

**Table 4.20-txt: DJI Mavic 2 Enterprise Android .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-11-20T14:55:54. 333000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26224365300385 Latitude: 39.8919448310861 Height: 0m Distance: 0.35588911175727844m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-11-20_[14-55-49].txt` |
| 2018-11-20T14:55:54. 434000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26224365300385 Latitude: 39.8919448310861 Height: 0m Distance: 0.35588911175727844m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-11-20_[14-55-49].txt` |
| 2018-11-20T14:55:54. 535000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26224343122725 Latitude: 39.89194497887398 Height: 0m Distance: 0.3819965422153473m Speed: 0.1414213627576828m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-11-20_[14-55-49].txt` |

## iOS drone controller

The iOS .DAT image `mobile_ios_backup.zip` was tested using Plaso via the log2timeline and psort tools yielding 5,358 events. The results in Table 4.18 shows the storage was successfully extracted without any errors and revealed an absence of .DAT flight logs in the directory. Further analysis of iOS .TXT forensic image produced 6,124 records, as presented in Table 4.19-txt. Table 4.21-txt also confirms the parser successfully extracted binary .TXT artifact `DJIFlightRecord_2018-11-20_[15-11-25].txt` from the iOS DJI Mavic 2 Enterprise drone controller.

**Table 4.18: DJI Mavic 2 Enterprise iOS .DAT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2025-05-14T02:28:30. 631966+00:00 | Content Modification Time | File stat | `OS:/mnt/d/artifact/DJI_Mavic_2_Enterprise/iOS/mobile_ios_backup_decrypted/AppDomain-com.apple.Maps/Library/Preferences Type: directory Owner identifier: 1000 Group identifier: 1000 Mode: 0o777 Number of links: 1` | filestat | `OS:/mnt/d/artifact/DJI_Mavic_2_Enterprise/iOS/mobile_ios_backup_decrypted/AppDomain-com.apple.Maps/Library/Preferences` |
| 2025-05-14T02:28:30. 631966+00:00 | Metadata Modification Time | File stat | `OS:/mnt/d/artifact/DJI_Mavic_2_Enterprise/iOS/mobile_ios_backup_decrypted/AppDomain-com.apple.Maps/Library/Preferences Type: directory Owner identifier: 1000 Group identifier: 1000 Mode: 0o777 Number of links: 1` | filestat | `OS:/mnt/d/artifact/DJI_Mavic_2_Enterprise/iOS/mobile_ios_backup_decrypted/AppDomain-com.apple.Maps/Library/Preferences` |
| 2025-05-14T02:28:30. 631966+00:00 | Content Modification Time | File stat | `OS:/mnt/d/artifact/DJI_Mavic_2_Enterprise/iOS/mobile_ios_backup_decrypted/AppDomain-com.apple.Maps/Library/Preferences/com.apple.Maps.plist Type: file Owner identifier: 1000 Group identifier: 1000 Mode: 0o777 Number of links: 1` | filestat | `OS:/mnt/d/artifact/DJI_Mavic_2_Enterprise/iOS/mobile_ios_backup_decrypted/AppDomain-com.apple.Maps/Library/Preferences/com.apple.Maps.plist` |

**Table 4.19-txt: DJI Mavic 2 Enterprise iOS .TXT Image Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-11-20T15:11:30. 368000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26223617931116 Latitude: 39.891948408499644 Height: 0m Distance: 0.2893962264060974m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/d4c192fdf9361ba93427178a45c16eefa4b4e2f5_extract_1747647027854/AppDomain-com.dji.Pilot-Enterprise-iOS/Documents/FlightRecords/DJIFlightRecord_2018-11-20_[15-11-25].txt` |
| 2018-11-20T15:11:30. 475000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.2622362822645 Latitude: 39.89194846286569 Height: 0m Distance: 0.3000589609146118m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/d4c192fdf9361ba93427178a45c16eefa4b4e2f5_extract_1747647027854/AppDomain-com.dji.Pilot-Enterprise-iOS/Documents/FlightRecords/DJIFlightRecord_2018-11-20_[15-11-25].txt` |
| 2018-11-20T15:11:30. 587000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26223626842301 Latitude: 39.89194863379295 Height: 1m Distance: 0.31910184025764465m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/d4c192fdf9361ba93427178a45c16eefa4b4e2f5_extract_1747647027854/AppDomain-com.dji.Pilot-Enterprise-iOS/Documents/FlightRecords/DJIFlightRecord_2018-11-20_[15-11-25].txt` |

**Table 4.21-txt: DJI Mavic 2 Enterprise iOS .TXT Artifact Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-11-20T15:11:30. 368000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26223617931116 Latitude: 39.891948408499644 Height: 0m Distance: 0.2893962264060974m Speed: 0.0m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-11-20_[15-11-25].txt` |
| 2018-11-20T15:11:30. 475000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.2622362822645 Latitude: 39.89194846286569 Height: 0m Distance: 0.3000589609146118m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-11-20_[15-11-25].txt` |
| 2018-11-20T15:11:30. 587000+00:00 | Creation Time | DJI Flight Log | Longitude: -105.26223626842301 Latitude: 39.89194863379295 Height: 1m Distance: 0.31910184025764465m Speed: 0.10000000149011612m/s | drone_binary | `OS:/mnt/d/DJIFlightRecord_2018-11-20_[15-11-25].txt` |

**Table 4.19: DJI Mavic 2 Enterprise Android Internal Memory .DAT Extraction**

| datetime | timestamp_desc | source_long | message | parser | display_name |
| --- | --- | --- | --- | --- | --- |
| 2018-11-29T04:09:54. 000000+00:00 | Content Modification Time | File stat | `ZIP:/aircraft_logical/blackbox/system/perf_data/8/mpstat.log Type: file` | filestat | `ZIP:/aircraft_logical/blackbox/system/perf_data/8/mpstat.log` |
| 2018-11-29T04:09:54. 000000+00:00 | Content Modification Time | File stat | `ZIP:/aircraft_logical/blackbox/system/perf_data/8/procmem.log Type: file` | filestat | `ZIP:/aircraft_logical/blackbox/system/perf_data/8/procmem.log` |
| 2018-11-29T04:09:56. 000000+00:00 | Content Modification Time | File stat | `ZIP:/aircraft_logical/blackbox/system/perf_data/1/mpstat.log Type: file` | filestat | `ZIP:/aircraft_logical/blackbox/system/perf_data/1/mpstat.log` |

## Drone internal memory

Analysis was performed on the `aircraft_logical.001` drone's internal memory image. The `log2timeline` and `psort` operations yielded 498 events, identifying the presence of a proprietary .DAT file. As presented in Table 4.19, the process completed without errors or warnings.
