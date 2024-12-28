# Web Log Analyzer and Anomaly Detector

This project is a Jupyter notebook that analyzes web server access logs (in Apache Common Log Format) to extract valuable information and detect potential anomalies, such as brute-force attacks and vulnerability scans.

## Description

The notebook performs the following tasks:

1. **Log Reading and Parsing:** Reads a log file line by line using a regular expression and converts it into a Pandas DataFrame for easy analysis.
2. **Data Cleaning and Conversion:** Cleans the data and converts relevant columns to the correct data types (dates, integers, etc.).
3. **Exploratory Analysis:** Performs an exploratory analysis of the data to obtain general information, including:
    *   Most frequent IPs.
    *   HTTP status codes.
    *   Most visited URLs.
    *   Traffic over time (requests per hour).
    *   Most common User-Agents.
    *   Most common Referers.
4. **Anomaly Detection:** Implements algorithms to detect:
    *   **Traffic Spikes:** Based on the mean plus a multiple of the standard deviation of the number of requests per hour.
    *   **Brute-Force Attacks:** Based on the number of failed login attempts (HTTP status codes 4xx and 5xx) from the same IP within a given time window.
    *   **Vulnerability Scans:** Based on the detection of suspicious patterns in the requested URLs and a high proportion of 404 status codes.
5. **Suspicious IP Investigation:** Provides functions to obtain additional information about IPs detected as suspicious, including:
    *   **WHOIS Information:** Uses the system's `whois` command.
