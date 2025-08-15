Ransomware Behavior Detection Lab (Python + Watchdog)

2️⃣ Project Objective

The purpose of this project is to simulate ransomware activity in a controlled environment and detect it using Python.

Monitors a folder for rapid file modifications (a behavior common to ransomware).

Logs alerts in real-time when suspicious activity exceeds a threshold.

Provides a safe environment for beginners to learn ransomware detection techniques.

3️⃣ How It Works (Theory)

Monitored Folder

A folder (monitored_folder) is created to act as the target for ransomware activity.

The simulator creates/modifies files inside this folder to mimic ransomware behavior.

Detector Script (ransomware_detector.py)

Uses Python’s watchdog library to monitor filesystem changes.

Every file creation/modification triggers an event that is recorded in a temporary CHANGE_LOG.

If the number of changes exceeds a predefined threshold (e.g., 20 changes in 10 seconds), it raises an alert.

Alerts are printed in the terminal and saved in logs/alert.log.

Simulator Script (ransomware_simulator.py)

Randomly creates multiple files in the monitored folder.

This simulates the rapid file changes typical of ransomware attacks.

Log System

Alerts are saved in logs/alert.log.

Each line includes a timestamp for when the potential ransomware activity was detected.

4️⃣ Key Components
Component	Purpose
monitored_folder	Target folder for ransomware simulation
logs/alert.log	Stores all detection alerts
ransomware_detector.py	Python script monitoring the folder
ransomware_simulator.py	Python script generating simulated ransomware behavior
Watchdog library	Python library for monitoring file changes
5️⃣ Beginner-Level Commands
Step 1 — Setup Folders
cd ~/Desktop
mkdir -p ransomware_lab/monitored_folder
mkdir -p ransomware_lab/logs
touch ransomware_lab/logs/alert.log

Step 2 — Navigate to Lab
cd ~/Desktop/ransomware_lab

Step 3 — Run Detector (keep this terminal running)
python3 ransomware_detector.py


You should see:

Monitoring 'monitored_folder' for ransomware behavior... Press Ctrl+C to stop.

Step 4 — Run Simulator (in a second terminal)
cd ~/Desktop/ransomware_lab
python3 ransomware_simulator.py

Step 5 — Check Logs
cat logs/alert.log


You should see multiple alert entries like:

[ALERT] Possible ransomware activity detected at Thu Aug 15 12:34:56 2025

6️⃣ Safety Note

This lab is completely safe; no actual ransomware is used.

All file modifications occur in a controlled folder (monitored_folder).

Always keep backups of your important data.

7️⃣ Suggested GitHub README Structure
# Ransomware Behavior Detection Lab

## Objective
Detect simulated ransomware activity using Python and Watchdog library.

## How It Works
- Monitors folder for rapid file changes.
- Alerts printed in terminal and logged to logs/alert.log.
- Simulator creates multiple files to mimic ransomware.

## Components
- monitored_folder
- logs/alert.log
- ransomware_detector.py
- ransomware_simulator.py

## Commands to Run
1. Setup folders:
   mkdir -p ransomware_lab/monitored_folder
   mkdir -p ransomware_lab/logs
   touch ransomware_lab/logs/alert.log

2. Run detector:
   python3 ransomware_detector.py

3. Run simulator (in a second terminal):
   python3 ransomware_simulator.py

4. Check logs:
   cat logs/alert.log
