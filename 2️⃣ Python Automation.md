🎯 Goal
Request reports, poll for readiness, download results, and transform them into analytics‑ready files.


📤 Report Request
```python
response = requests.post(
    "/reports",
    json={
        "reportType": "...",
        "dataStartTime": start_date,
        "dataEndTime": end_date
    }
)
report_id = response.json()["reportId"]
```
* Asynchronous report handling
* Scalable approach (API may take minutes)
* Robust orchestration logic


⏳ Status Polling
```python
while True:
    status = response.json()["processingStatus"]
    if status == "DONE":
        return document_id
    time.sleep(30)
```
* Controlled polling (no API abuse)
* Explicit failure handling
* Operational robustness


📦 File Processing
```python
with gzip.open(compressed_stream, mode='rt') as gz_file:
    raw_json = json.load(gz_file)

df = pd.json_normalize(raw_json["salesByAsin"])
```
* Handles compressed API outputs
* Flattens nested JSON structures
* Converts raw data into tabular format
