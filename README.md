# presto-HDFS-read-data

Within Uber during the past 2 years, we have extracted logs from Presto and HDFS to track the detailed operations, including file open and read calls. We used these logs to understand our data lake traffic patterns, and provided insights for multiple projects. We see common use cases and high demand of similar logs across the industry and academia, and the opportunity to open source the logs, with anonymizing sensitive information such as the file paths.

## Log format
The logs are formatted as **<timestamp, path, thread id, latency, (read position, read length)>**, which were collected over **17 days** from September 8 to September 25, 2023, from 3 nodes of **Presto cluster**.

For example, `server.log-2023-09-08.0.log.gz:2023-09-08T02:56:07.191Z	INFO stdout	PARQUETOPEN:9030208118269938,8695,58,44474752` means:
- Time: 2023-09-08T02:56:07.191Z
- Request Type: PARQUETOPEN
- Timestamp: 9030208118269938
- File ID: 8695
- Thread ID: 58
- Latency Duration: 44474752

## License
All data is copyright 2024, Uber Techologies, Inc.  Licensed under the [Community Data License Agreement - Permissive - v 2.0](LICENSE.md).
