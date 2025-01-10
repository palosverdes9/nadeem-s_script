**Title:**
Log Archival System
Overview:
This document describes the technologies and architecture used to implement the log archival system, which automates the movement of logs from /var/log/audit/ to an S3 bucket.
Technology and purpose
Linux (Cron):
Schedule the monthly execution of the log archival script.
Bash Script:
Automates the log selection, copying, and synchronization process.
AWS S3:
Provides scalable object storage for storing logs securely and durably.
AWS CLI:
Facilitates interaction with AWS S3 for uploading and managing logs.
Logrotate:
Manages log file rotation, compression, and retention to avoid disk space overflows.
System Temporary Directory:
Temporary storage for intermediate log processing (/tmp or a custom path).

Description
The architecture for the log archival system includes the following components:
Log Source: Logs are generated and stored in /var/log/audit/.
Script Execution: A bash script, triggered by corn.monthly, identifies logs from the month before, processes them, and uploads them to the S3 bucket.
S3 Bucket: Logs are stored in an S3 bucket, organized by date-based folders for easy retrieval.
Log Cleanup: Optionally, local logs are removed after successful upload to free up disk space.
