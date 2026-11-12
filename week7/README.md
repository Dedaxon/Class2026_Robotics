# Dedaxon — Week 7, digits 35

- `Dedaxon_trajectory.qrs`: open in TRIK Studio and run the graphical program.
- `Dedaxon_trajectory.py`: alternative Python implementation for TRIK.
- `Dedaxon_analysis.ipynb`: Colab/local analysis for your recorded runs.

Use either program for both simulator and hardware with the same settings. M3/E3 is left, M4/E4 right. Start at (0,0), facing +x; +y is left. Each digit is 40 cm wide and 60 cm high, with a 25 cm gap. The pen lifts when moving to the top-right of 5. Final target: (65,-60) cm.

Both programs write `Dedaxon_odometry_data.txt`: x,y in centimetres, elapsed time in milliseconds, no header. Save each run before starting another: `Dedaxon_odometry_data_sim.txt` and `Dedaxon_odometry_data_real.txt`. These correspond to the task's unprefixed odometry filenames. One QRS is used for both environments; duplicate it under the task's sim/real submission names only if required.

Controller: the existing week7 turn-first proportional go-to-goal controller, with wrapped heading error. Radius 0.028 m, track 0.154 m, threshold 0.012 m; steering gain 70, distance gain 160, drive power limited to 20–60, steering correction to ±50, heading gate 0.15 rad. Measure geometry on your robot and adjust consistently in both sources if needed. Keep the floor clear over the full drawing and transfer path.

After both runs, upload the logs to the notebook. It plots the planned and recorded trajectories, reports waypoint misses and run times, and compares the tape-measured final position to the final target and odometry. Unequal sample counts are supported. Complete the discussion using your observations. The supplied `Dedaxon_odometry_data.txt` is saved here (570 rows, 73.271 s). Its simulator/real identity is unspecified; the notebook labels it Uploaded run and contains its executed analysis. A second labelled run and tape measurement are still needed for simulator-versus-real and physical endpoint comparisons.
