# Submission Reminder Application

This is a simple Bash script that helps track assignment submissions by students and sends reminders to those who haven't submitted.

## Features
- Reads assignment details from a configuration file.
- Checks student submissions from a CSV file.
- Displays reminders for students who haven't submitted their assignments.
- Uses modular scripts for flexibility.

## Prerequisites
Ensure you have:
- A Linux/macOS system with Bash installed.
- Execution permissions for shell scripts.

## Installation and Setup

### Step 1: Clone or Create the Script
If you haven't already, create a directory and save the script file.

Alternatively, clone the project (if hosted on GitHub):
```bash
# Example if hosted on GitHub
git clone https://github.com/your-repo/submission-reminder.git
cd submission-reminder
```

### Step 2: Run the Setup Script
The provided script sets up the necessary files and directories. Run:
```bash
chmod +x setup.sh
./setup.sh
```

This will:
- Create necessary directories (`app`, `modules`, `assets`, `config`).
- Create required files (`reminder.sh`, `functions.sh`, `config.env`, `submissions.txt`).
- Assign execute permissions where necessary.

### Step 3: Run the Application
Once setup is complete, execute:
```bash
./startup.sh
```

This will:
- Load assignment details from `config/config.env`.
- Check student submissions in `assets/submissions.txt`.
- Display reminders for students who haven't submitted their assignments.

## Customization

### Modify the Assignment Name and Due Date
Edit `config/config.env` to change the assignment details:
```bash
ASSIGNMENT="New Assignment Name"
DAYS_REMAINING=5
```

### Update Student Submission Data
Modify `assets/submissions.txt` to reflect real-time student submissions:
```bash
student, assignment, submission status
John Doe, Shell Scripting, not submitted
Jane Smith, Git, submitted
```

## Troubleshooting
- **Permission Denied Error:** Run
  ```bash
  chmod +x startup.sh app/reminder.sh modules/functions.sh
  ```
- **Function Not Found Error:** Ensure `functions.sh` is correctly sourced by modifying `app/reminder.sh`:
  ```bash
  source modules/functions.sh
  ```
  Then rerun the script.

## Expected Output
If successful, the script outputs:
```
Assignment: Shell Navigation
Days remaining to submit: 2 days
--------------------------------------------
Checking submissions in ./assets/submissions.txt
Reminder: Chinemerem has not submitted the Shell Navigation assignment!
Reminder: Divine has not submitted the Shell Navigation assignment!
```

## Next Steps
- Automate execution using a cron job for periodic reminders.
- Enhance functionality to send email or SMS reminders.
