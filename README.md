# Py_projects
Python Projects

## File Operations Server Config

This folder contains utilities for managing server configuration files.

### server.conf
A sample server configuration file in key-value format, containing settings for network, security, logging, and other server parameters.

Example contents:
```
# Server config file

#Network Settings
PORT=8080
MAX_CONNECTIONS=1000
TIMEOUT = 30

#Security Settings
SSL_ENABLED=true
SSL_CERT_PATH=/path/to/cert.pem

#Logging Services
LOG_LEVEL=INFO
LOG_FILE=/var/log/server.log

#Other Settings
MAX_THREADS=10
ENABLE_FEATURE_X=true
```

### update_server.py
A Python script that provides a function to update specific configuration values in a config file. It reads the file, replaces lines containing a specified key with the new key-value pair, and writes back the updated content.

Key function:
```python
def update_server_config(file_path, key, value):
    with open(file_path, "r") as file:
        lines = file.readlines()
    
    with open(file_path, "w") as file:
        for line in lines:
            if key in line:
                file.write(key + "=" + value + "\n")
            else:
                file.write(line)
```

Example usage:
```python
update_server_config("server.conf", "MAX_CONNECTIONS", "1000")
```
This updates the `MAX_CONNECTIONS` setting to 1000 in server.conf.
