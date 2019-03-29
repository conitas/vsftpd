# Simple Preconfigured for FTPS Single User VSFTPD

This is a simple FTPS server preconfigured for simple user mode and secured by default with TLS > 1.0.

Inspired by [fauria/docker-vsftpd](https://github.com/fauria/docker-vsftpd)
and [onjin/docker-alpine-vsftpd](https://github.com/onjin/docker-alpine-vsftpd)

This image contains vsftpd server configured with only one user files with volume `/home/${FTP_USER}`. Password is set from `${FTP_PASSWORD}` env variable or generated if not provided.

# Passive Mode
Passive Mode is enabled by default. Internally the port range  10090-10100 is predefined for this purpose.

# SSL Keys
The SSL configuration needs pre generated valid ssl keys. Private key should be put into `/etc/vsftpd/vsftpd.key`, and the public certificate `/etc/vsftpd/vsftpd.crt` . If no keys provided, one temporary key will be generated at startup. Server is configured to be rejecting SSL and TLS1.0 protocols (versions).  

# Logs
Logs are redirected from file configured within the `/etc/vsftpd/vsftpd.conf` (parameter `xferlog_file`) to STDOUT of the container.

# Build
```
  docker-compose build
```

# Run
```
  docker-compose up
```    
