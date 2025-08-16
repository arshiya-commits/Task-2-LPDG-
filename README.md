Traffic Velocity Anomaly Detection

This project analyzes a traffic dataset (CSV file with timestamps and velocities) to detect anomalies in vehicle speed patterns.

📌 Objective:
Compare each row’s velocity to the previous timestamp’s velocity.

Define Normal vs Anomaly:

Normal: velocity changes smoothly (small differences between rows).

Anomaly: velocity jumps too fast (e.g., +10 m/s in <0.5 seconds) or goes negative unexpectedly.

🛠️ Steps Performed

Load the dataset

Used pandas.read_csv() to load the CSV file into a pandas DataFrame.

Convert timestamps

Converted the time_stamp column (Unix time in seconds) into a human-readable datetime column.

Sort the dataset

Sorted the DataFrame by the datetime column to ensure rows are in correct time order.

Compare with previous row

Created prev_velocity and prev_time using .shift(1).

Calculated:

delta_v = difference in velocity

delta_t = difference in time (in seconds, using .dt.total_seconds())

Apply anomaly rules

Rule 1: Mark as anomaly if velocity < 0.

Rule 2: Mark as anomaly if |delta_v| >= 10 and delta_t <= 0.5.

Otherwise, mark as Normal.

Saved result in a new status column.

Results

Counted anomalies vs normals using .value_counts().

📊 Future Model Note

These anomaly flags can be used in a semi-supervised model.

Train the model only on Normal rows (to learn usual velocity patterns).

Use the Anomaly rows to validate whether the model is catching outliers.

Over time, this approach helps detect unusual driving events in new data without needing a fully labeled dataset.

⚡ Tech Stack

   Python 

   Pandas (data handling)

Install requirements:
   pip install pandas
