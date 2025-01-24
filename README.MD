# Rest-Configuration

## Overview
Developing the REST API connector will furnish Fusion with a versatile tool capable of seamlessly integrating diverse data sources. Additionally, this initiative will afford us the strategic advantage of replacing several of our classic connectors reliant on REST API data ingestion.

## Setup
To configure the REST connector with a configuration, you will need to:

1. Download the configuration from this repository.
2. Use the curl command to provision the REST connector with any configuration from this repository. Before executing the curl command, please add the Fusion instance, JSON config, and within the JSON, please include the collection name and pipeline. Then execute the curl command:

```
curl -u username:password --location 'https://**fusion domain!**/api/apps/**fusion app name**/connectors/datasources' \
--header 'Content-Type: application/json' \
--data-raw 'add json here'
```
3. Log in to the Fusion admin and configure the relevant information, such as credentials, URL for the instance, etc.

4. Now you're ready to go! Happy crawling!

## Contributing

All are welcome to contribute to this repository. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidance on how to contribute.