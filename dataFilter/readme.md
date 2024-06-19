# JSON Data Filter Code

This script designed to filter out specific entries from a JSON file containing camera data. It specifically focuses on extracting data related to specified type from the input file. The code reads the input JSON file, filters the entries, and writes the filtered data to a new JSON file.

## Requirements

To run this code, you need Python installed on your system. Additionally, make sure that the json module is available in your Python environment. The code should work with Python versions 3.x.

### Sample Input

The input data is expected to be a JSON file in the following format and the code will look for the input JSON file named `cam1.json` in the input directory. Make sure to place the input file in the appropriate location.

```json
{
    "frame1": {
        "timestamp": "2023-07-29T22:30:22.801Z",
        "1": {
            "type": "car",
            "class": "2",
            "x1": "484",
            "y1": "325",
            "x2": "667",
            "y2": "439"
        },
        "2": {
            "type": "person",
            "class": "0",
            "x1": "200",
            "y1": "145",
            "x2": "294",
            "y2": "194"
        },
    },
    "frame2": {
        "timestamp": "2023-07-29T22:30:21.841Z",
        "1": {
            "type": "bicycle",
            "class": "2",
            "x1": "497",
            "y1": "320",
            "x2": "673",
            "y2": "433"
        },
        "2": {
            "type": "car",
            "class": "2",
            "x1": "200",
            "y1": "144",
            "x2": "293",
            "y2": "193"
        },
    },
}
```

### Sample Output

The code will create a new JSON file with the filtered data, containing only entries with `type` equal to `bicycle` and `car` for each frame. The output JSON file will have the following format and The output JSON file will be named `cam1_final.json` and will be located in the output directory.

```json
{
    "frame1": {
        "timestamp": "2023-07-29T22:30:22.801Z",
        "1": {
            "type": "car",
            "class": "2",
            "x1": "484",
            "y1": "325",
            "x2": "667",
            "y2": "439"
        },
    },
    "frame2": {
        "timestamp": "2023-07-29T22:30:21.841Z",
        "1": {
            "type": "bicycle",
            "class": "2",
            "x1": "497",
            "y1": "320",
            "x2": "673",
            "y2": "433"
        },
        "2": {
            "type": "car",
            "class": "2",
            "x1": "200",
            "y1": "144",
            "x2": "293",
            "y2": "193"
        },
    },
}
```
## To Run the Code

To run the code, execute it using Python:

```
    python data_filter.py
```