## Required libraries
- numpy                     1.26.4
- pandas                    2.2.3      
- python                    3.9.20 
- scikit-learn              1.5.1
- scipy                     1.13.1

## Important path to load data
## Data Pre-processing
### Data from T-brain
```{python}
TrainData_path = "./TrainData" (replace the path if needed)
```
### Data from HDARES
```{python}
Datapath = os.path.join(os.getcwd(), 'TrainData', 'additional', f'72T250_item_hour_20241127181859.csv') (replace the path if needed)
```

## Algorithm & Modeling
### Step 1
```{python}
test_data_path = os.path.join(os.getcwd(), 'ExampleTestData', 'upload(no answer).csv')
...
Datapath = os.path.join(os.getcwd(), 'TrainData', 'processed', f'L{location}_Train_processed.csv')
```
Since Step will run a while, we provide pickle file containing result of Step 1.
```{python}
import pickle

# Load variables from the local file
with open('saved_data.pkl', 'rb') as f:
    data = pickle.load(f)

# Extract the variables
dic_for_each_ex = data['dic_for_each_ex']

print("Data loaded successfully!")
----------------------------------
Data loaded successfully!
```
dic_for_each_ex is a dictionary that (key: 題目; value: a dic containing found corresponding location (key) and its Power (value))
like below:
```{python}
{20240117090001: {8: 24.886000000000003, 17: 51.354},
 20240117091001: {8: 26.511000000000003, 17: 97.969},
 20240117092001: {8: 31.68, 17: 141.77100000000002},
 20240117093001: {8: 37.409, 17: 49.427},
...}
```



