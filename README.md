# log_analyzer_python_pandas

This project is a Jupyter notebook that analyzes web server access log files (in Apache Common Log Format) to extract valuable information and detect potential anomalies, such as brute force attempts and vulnerability scans.
Description

The notebook performs the following tasks:

    Log Reading and Parsing: Reads a log file line by line using a regular expression and converts it into a Pandas DataFrame for easier analysis.
    Data Cleaning and Conversion: Cleans the data and converts relevant columns to the correct data types (dates, integers, etc.).
    Exploratory Analysis: Conducts an exploratory analysis of the data to obtain general insights, including:
        Most frequent IPs.
        HTTP status codes.
        Most visited URLs.
        Traffic over time (requests per hour).
        Most common User-Agents.
        Most common Referrers.
    Anomaly Detection: Implements algorithms to detect:
        Traffic Spikes: Based on the mean plus a multiple of the standard deviation of             requests per hour.
        Brute Force Attempts: Based on the number of failed access attempts (HTTP 4xx and          5xx status codes) from a single IP within a specific time window.
        Vulnerability Scans: Based on detecting suspicious patterns in requested URLs and          a high proportion of 404 status codes.
    Investigation of Suspicious IPs: Provides functions to retrieve additional information     about detected suspicious IPs, including:
        WHOIS Information: Uses the system whois command.
