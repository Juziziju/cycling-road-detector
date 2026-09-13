# Cycling Road Detector

git See [STRUCTURE.md](STRUCTURE.md) for the project plan. Only for internal communication, will elimate when submit final project.

## Requirements

Not set yet, will normalize it during processing part.

## Recording names

Use `P01_R01_T01` for each recording folder. `P` identifies the participant, `R` identifies the physical road segment, and `T` is the recording index in chronological order for that participant on that segment. Start indices at `01`. `T` is an index, not a timestamp or a sensor sample number.

Keep participant IDs fixed and use the same road ID across all participants for the same physical segment. Different segments have different road IDs, even if their surface type is the same.

## Data format

Store self-collected recordings under `data/smooth/P01_R01_T01/` or `data/bumpy/P01_R02_T01/`, according to the observed surface type. Each folder contains the original Sensor Logger CSV exports, including `Accelerometer.csv`, `Gyroscope.csv`, and `Gravity.csv`. Keep exported filenames and raw values unchanged.

The existing deployment CSV files use `time,seconds_elapsed,z,y,x`: an absolute timestamp, elapsed recording time in seconds, and three sensor axes. Check the headers of new exports and read axes by column name. Surface labels come from the enclosing `smooth` or `bumpy` folder, not from the sensor columns.

Keep the external files in `data/DeploymentData/` separate from self-collected data. They are reserved for deployment after model selection, not training or testing.
