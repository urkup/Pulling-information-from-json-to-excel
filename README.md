# Pulling-information-from-json-to-excel

import json
import csv
with open("./users10.json") as file:
    data = json.load(file)

fname = "output3.csv"

with open(fname, "w") as file:
    csv_file = csv.writer(file)
    csv_file.writerow(["first_name","custom_email","username"])
    for item in data["results"]:
        csv_file.writerow([item["first_name"],item["custom_email"],item["username"]])
