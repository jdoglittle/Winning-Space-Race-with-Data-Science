Data Collection – SpaceX API​
import requests
import pandas as pd
!pip install pandas
url = "https://api.spacexdata.com/v4/launches/past"
response = requests.get(url)
launch_data = response.json()
df = pd.json_normalize(launch_data)
rocket_ids = df['rocket'].unique()
rocket_info = {}

# Loop through unique rocket IDs and fetch details
for rid in rocket_ids:
    r = requests.get(f"https://api.spacexdata.com/v4/rockets/{rid}").json()
    rocket_info[rid] = r['name']

# Map rocket names into the main dataframe
df['rocket_name'] = df['rocket'].map(rocket_info)




