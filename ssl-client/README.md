## Overview

This is a sample code that connects to an SSL enabled GemFire cluster using SSL enabled client. It's a simple command line simple program that connects to a region using cache factory object and does not involve any depenency on Java.
Since JKS format is not supported with .NET, you will need to export your certs (keystore, truststore) in .pem or other supported types. JKS is not supported.
Please refer to this KB for more details <a href="https://community.pivotal.io/s/article/How-to-connect-SSL-Enabled-VMware-GemFire-NET-Client-to-SSL-Enabled-VMware-GemFire-Cluster-on-Windows?language=en_US" target="_blank">https://community.pivotal.io/s/article/How-to-connect-SSL-Enabled-VMware-GemFire-NET-Client-to-SSL-Enabled-VMware-GemFire-Cluster-on-Windows?language=en_US</a>

This sample was created, built and tested with Microsoft Visual Studio 2017 Community Edition.
