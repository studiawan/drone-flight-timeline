# Drone Flight Timeline

This repository provides experimental results for custom parsers and supporting scripts for integrating DJI drone flight logs into the **log2timeline/Plaso forensic timeline framework**.

The repository supports the parsing and forensic timeline reconstruction of proprietary DJI **`.DAT`** and binary **`.TXT`** flight logs obtained from Android, iOS, and drone storage. The developed parsers extract key flight information, including:

- Timestamps
- GPS coordinates
- Altitude
- Velocity
- Speed
- Flight distance

The extracted artifacts are incorporated into a structured forensic timeline, enabling drone flight evidence to be analysed together with other digital forensic artifacts within a unified Plaso-based workflow.

## Related Research

This repository accompanies the research paper:

**Forensic Timeline Reconstruction from Encrypted Drone Flight Logs**

The study addresses the lack of native support in log2timeline/Plaso for proprietary DJI `.DAT` and binary `.TXT` flight logs. Custom parsers were developed to decode these formats and integrate the extracted flight telemetry directly into the forensic timeline.

## Supported DJI Drone Models

The proposed method was evaluated on five DJI drone models:

- DJI Mavic Pro
- DJI Mavic Air
- DJI Mavic 2
- DJI Mavic 2 Enterprise
- DJI Phantom 4

Due to space limitations, the paper presents detailed experimental results for only two representative models:

- DJI Mavic Pro
- DJI Phantom 4

The **complete experimental results for all five evaluated drone models are available in this repository**.

## Main Features

The repository includes functionality for:

- Parsing DJI `.DAT` flight logs
- Parsing binary DJI `.TXT` flight logs
- Decrypting and decoding DJI flight telemetry
- Extracting GPS coordinates and timestamps
- Extracting altitude and velocity information
- Extracting flight speed and distance
- Integrating drone artifacts into log2timeline/Plaso
- Generating structured forensic timelines
- Post-processing Plaso CSV output
- Supporting forensic analysis across Android, iOS, and drone storage

## DJI `.DAT` Log Processing

DJI `.DAT` files contain encrypted flight records. The implemented parser:

1. Identifies valid DJI `.DAT` records.
2. Verifies record integrity.
3. Extracts the ticket number and record type.
4. Decrypts the payload using a bitwise XOR operation.
5. Extracts flight telemetry such as:
   - Longitude
   - Latitude
   - Altitude
   - X velocity
   - Y velocity
   - Z velocity
6. Converts the extracted data into Plaso event objects.

## DJI `.TXT` Log Processing

Binary DJI `.TXT` files require a different decoding procedure. The parser:

1. Identifies individual flight records.
2. Determines the record type and payload.
3. Generates the required scramble bytes using CRC64-based processing.
4. Performs XOR-based payload decoding.
5. Extracts:
   - Longitude
   - Latitude
   - Height
   - Flight speed
   - Flight distance
   - Timestamp
6. Integrates the resulting data into the Plaso forensic timeline.

## Forensic Timeline Integration

The extracted drone flight data are converted into Plaso event data so that drone activity can be correlated with other forensic artifacts.

The resulting timeline may contain information such as:

```text
Timestamp
Longitude
Latitude
Height
Speed
Distance
X Velocity
Y Velocity
Z Velocity
Source
Artifact Path
