# B1.2 – Log Analysis

## Aim

To analyse web-server access logs and identify request counts, HTTP status codes and client activity.

## Introduction

Log analysis helps administrators understand website activity and identify errors. It is useful for monitoring the university result portal during normal usage and result-day traffic.

## Script Description

The `log_analysis.sh` script reads a web-server access log and displays:

- Total number of requests.
- Number of successful requests.
- Number of client errors.
- Number of server errors.
- Most frequent client IP address.

## Procedure

1. Create the `log_analysis.sh` file.
2. Give the script execution permission.
3. Run the script with a web-server access log as input.
4. Observe the output.
5. Save the actual output in `log_analysis_output.txt`.

## Result

The log-analysis script processes the access log and displays request and client information. The output file should contain the actual result obtained after execution.
