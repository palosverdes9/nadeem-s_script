**Log Archival System**

**Overview**

This repository outlines the architecture and technologies used to implement a log archival system designed to automate the transfer of logs from /var/log/audit/ to an AWS S3 bucket.

**Technology and Purpose**

**Linux (Cron):**

Utilized to schedule the monthly execution of the log archival script.

**Bash Script:**

Automates the process of selecting, copying, and synchronizing logs.

**AWS S3:**

Provides scalable object storage, ensuring logs are securely and durably stored.

**AWS CLI:**

Facilitates the interaction with AWS S3 for log uploads and management.

**Logrotate:**

Handles the rotation, compression, and retention of log files to prevent disk space overflow.

**System Temporary Directory:**

Used as a temporary storage location for intermediate log processing, typically /tmp or a custom path.

**Description**

The log archival system is composed of the following components:

**Log Source:**

Logs are generated and stored in /var/log/audit/.

**Script Execution:**

A bash script is executed monthly via cron.monthly. This script is responsible for identifying logs from the previous month, processing them, and uploading to the S3 bucket.

**S3 Bucket:**

Logs are organized into date-based folders within an S3 bucket, making retrieval straightforward and efficient.

**Log Cleanup:**

After a successful upload, local logs can be optionally removed to free up disk space.
This system ensures your logs are systematically archived to the cloud, leveraging AWS services to maintain a robust and efficient log management process.
