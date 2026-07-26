# Machine Condition Monitoring Unit (SIH 2026)

## Problem Statement
Small production units suffer from unexpected machinery breakdowns and delivery penalties because maintenance is based on fixed calendars rather than actual machine vibration and temperature conditions.

## How to Run Step-by-Step
1. Clone this repository:
   `git clone https://github.com/your-username/sih-machine-monitoring.git`
2. Open terminal inside the project directory.
3. Run the Python signal simulation script (Optional):
   `python simulate.py`
4. Start a local HTTP server to avoid CORS issues:
   `python -m http.server 8000`
5. Open your browser and navigate to:
   `http://localhost:8000`

## Data Field Descriptions
- `reading_id`: Unique integer identification for the sensor log entry.
- `machine_id`: String identifier representing the target equipment (e.g., MCH-101).
- `vibration`: Decimal representing vibration speed in mm/s (Range: 0 to 10.0; Outliers > 50).
- `temperature`: Decimal representing housing surface temperature in °C (Range: 0 to 100.0).
- `alert_flag`: Enum status string (`NORMAL`, `WARNING`, `CRITICAL`, `UNKNOWN`, `ERROR`).
- `recorded_at`: ISO 8601 UTC timestamp format.

## Derived Calculations Explanation
- **Average Temperature/Vibration**: Sum of all valid readings divided by total non-null count (excluding values out of valid ranges >200°C or >50 mm/s).
- **Total Machine Logs**: Running sum of all historical logs registered under a selected `machine_id`.

## Status of Completion
All tasks (Task 1 to Task 6) are 100% completed according to specifications.# monitoringproject1
