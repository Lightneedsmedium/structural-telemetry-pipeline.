# Structural Telemetry Assessment Pipeline

This repository contains a Python-based data pipeline designed to ingest raw modal sensor telemetry from structural health monitoring systems (e.g., accelerometers on bridges/buildings) and automatically generate readable, formatted structural condition assessments.

## Architecture
The pipeline utilizes **Claude 3.5 Sonnet** as the core reasoning engine. 
1. **Data Ingestion:** Reads raw JSON telemetry containing natural frequencies, damping ratios, and environmental conditions.
2. **Prompt Construction:** Transforms the raw numerical telemetry into a structured prompt designed for expert engineering analysis.
3. **LLM Assessment:** Passes the data to Claude 3.5 Sonnet to interpret frequency shifts (e.g., comparing current Hz to baseline Hz to detect loss of stiffness).
4. **Summary Generation:** Outputs a formatted Markdown report containing the overall status, localized sensor analysis, and maintenance recommendations.

## Files
- `telemetry_pipeline.py`: The main pipeline execution script.
- `raw_sensor_data.json`: A sample file containing mock modal telemetry from a bridge span.

## How to Run
Ensure Python is installed. The script runs using standard libraries.

```bash
python telemetry_pipeline.py
```
*(Note: The provided script uses a mock API response for demonstration purposes so it can be run out-of-the-box without requiring an active Anthropic API key).*
