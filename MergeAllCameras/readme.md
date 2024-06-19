# JSON Data Merging Algorithm

This script combines two pieces of JSON data from various camera feeds based on how close they are to one other spatially. The objective is to locate and combine data points from the second set that correspond to items found in the first set and are closer than a predetermined threshold. After merging the data, a new JSON file is created and stored.

## Algorithm Overview

1.  **Calculate Distance Function**: Calculate the Euclidean distance between two 3D coordinates using the `calculate_distance()` method.

2.  **Merging Data Function**: Two pieces of JSON data (json_data1 and `json_data2`), a distance threshold, and an ID adjustment value (make sure to change the value every time when you merge 2 json files for getting unique id) are passed to the`merge_json_data()` method. In order to create a new dataset (`merged_data`), it analyses the data to find matching items.
    When comparing objects from `json_data1` and `json_data2` for potential merging, the function checks two conditions:

        - `j in unmatched_indices`: This condition ensures that an object from `json_data2` hasn't been matched with any object from `json_data1` yet. This prevents one object from `json_data2` being merged with multiple objects from `json_data1`.

        - `json_data1["type"][i] == json_data2["type"][j]`: This condition checks if the types of objects in `json_data1` and `json_data2` are the same. Only objects with matching types are considered for merging.

3.  **Merging and Saving Function**: Two input files (`json_file1` and `json_file2`) are read by the`merge_and_save_json()` method to read JSON data. The merged data is then saved to an output file after the program iterates through each pair of data entries and uses the `merge_json_data()` function to combine them.

## Usage

1. **Prerequisites**: Ensure you have Python and the `shapely` library installed. You can install it using `pip install shapely`.

2. **Data Preparation**: Place the input JSON files in the directory `input/`. Create an output directory with the name `output/` to save the merged data.

2. **How to run**:

Merge will works with multiple iterations.

- Iterations 1: run the Cam1 as input and Cam2 as output json using adjust_ID = 10000
- Iterations 2: run OutputCam12 as input and Cam3 as output json using adjust_ID = 20000
- Iterations 3: run OutputCam123 as input and Cam4 as output json using adjust_ID = 30000
- Iterations 4: run OutputCam1234 as input and Cam45 as output json using adjust_ID = 40000

   ```bash
    json_file1 = 'input/OnlyPerson/Camera_1234_cut_final_transformed.json'
    json_file2 = 'input/OnlyPerson/Camera_5_cut_final_transformed.json'
   ```

Here json_file1 considered as input like Cam1 data.
Here json_file2 considered as input like Cam2 data.
While run this script, you have to update every in every run. 

run command 

   ```bash
   python merge2Json.py
   ```


   **Sample input1 (`input/Cam1.json`):**

```json
[
  {
    "timestamp": "2023-07-29T22:30:22.801Z",
    "id": [1, 2, 3, 4, 5, 7, 8, 10, 14],
    "coordinates": [
      [967731.7601707891, 6468644.113205706, 1.0],
      [967739.2275438067, 6468721.65449088, 1.0],
      [967720.1503904081, 6468627.500482801, 1.0],
      [967734.8169872257, 6468726.701328755, 1.0],
      [967723.5031896648, 6468621.211255788, 1.0],
      [967740.4270098063, 6468634.506602504, 1.0],
      [967731.1382749235, 6468636.272375308, 1.0],
      [967732.962751747, 6468639.791774379, 1.0],
      [967737.9291890141, 6468631.463355769, 1.0]
    ],
    "type": [
      "CAR",
      "CAR",
      "PERSON",
      "CAR",
      "PERSON",
      "PERSON",
      "BICYCLE",
      "PERSON",
      "BICYCLE"
    ]
  }
]
```

**Sample input 2 (`input/Cam2.json`):**

```json
[
  {
    "timestamp": "2023-07-29T22:32:49.480Z",
    "id": [1, 2, 3, 7, 8, 11, 12, 13, 14, 15, 16, 17, 18, 20, 22, 23],
    "coordinates": [
      [967732.2187230347, 6468700.045567645, 1.0],
      [967735.8748946106, 6468697.161022393, 1.0],
      [967701.3874565677, 6468637.565815932, 1.0],
      [967691.798241687, 6468619.547083363, 1.0],
      [967687.750923086, 6468607.077350087, 1.0],
      [967698.4731273905, 6468617.5828329185, 1.0],
      [967708.6145481009, 6468689.479443268, 1.0],
      [967661.9193026959, 6468574.040422699, 1.0],
      [967709.2637418663, 6468692.551824262, 1.0],
      [967721.3278346001, 6468617.374842919, 1.0],
      [967685.0416459474, 6468596.160880767, 1.0],
      [967696.3903135777, 6468607.873360844, 1.0],
      [967717.1055760826, 6468695.5015411945, 1.0],
      [967709.6471594232, 6468613.314400236, 1.0],
      [967672.8750921944, 6468592.139398976, 1.0],
      [967707.6521973455, 6468692.449766348, 1.0]
    ],
    "type": [
      "CAR",
      "CAR",
      "CAR",
      "CAR",
      "CAR",
      "CAR",
      "PERSON",
      "CAR",
      "PERSON",
      "PERSON",
      "CAR",
      "CAR",
      "PERSON",
      "PERSON",
      "CAR",
      "PERSON"
    ]
  }
]
```

**Sample Output (`output/Cam12.json`):**

```json
[
  {
    "timestamp": "2023-07-29T22:30:22.801Z",
    "id": [
      1, 2, 3, 4, 5, 7, 8, 10, 14, 10003, 10007, 10008, 10011, 10012, 10013,
      10014, 10016, 10017, 10018, 10022, 10023
    ],
    "coordinates": [
      [967731.7601707891, 6468644.113205706, 1.0],
      [967739.2275438067, 6468721.65449088, 1.0],
      [967720.1503904081, 6468627.500482801, 1.0],
      [967734.8169872257, 6468726.701328755, 1.0],
      [967723.5031896648, 6468621.211255788, 1.0],
      [967740.4270098063, 6468634.506602504, 1.0],
      [967731.1382749235, 6468636.272375308, 1.0],
      [967732.962751747, 6468639.791774379, 1.0],
      [967737.9291890141, 6468631.463355769, 1.0],
      [967701.3874565677, 6468637.565815932, 1.0],
      [967691.798241687, 6468619.547083363, 1.0],
      [967687.750923086, 6468607.077350087, 1.0],
      [967698.4731273905, 6468617.5828329185, 1.0],
      [967708.6145481009, 6468689.479443268, 1.0],
      [967661.9193026959, 6468574.040422699, 1.0],
      [967709.2637418663, 6468692.551824262, 1.0],
      [967685.0416459474, 6468596.160880767, 1.0],
      [967696.3903135777, 6468607.873360844, 1.0],
      [967717.1055760826, 6468695.5015411945, 1.0],
      [967672.8750921944, 6468592.139398976, 1.0],
      [967707.6521973455, 6468692.449766348, 1.0]
    ],
    "type": [
      "CAR",
      "CAR",
      "PERSON",
      "CAR",
      "PERSON",
      "PERSON",
      "BICYCLE",
      "PERSON",
      "BICYCLE",
      "CAR",
      "CAR",
      "CAR",
      "CAR",
      "PERSON",
      "CAR",
      "PERSON",
      "CAR",
      "CAR",
      "PERSON",
      "CAR",
      "PERSON"
    ]
  }
]
```


 
