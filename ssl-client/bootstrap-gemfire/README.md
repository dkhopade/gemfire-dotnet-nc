# Bootstrap GemFire Cluster
## _Follow these instructions to start local GemFire Cluster_

This step assumes you have downloaded standalone GemFire distribution from https://network.pivotal.io/products/pivotal-gemfire/
To download it you need to login to your account and if you dont have one, then go ahead and create one.
To learn more on how to install and configure local GemFire, please refer to this link: https://gemfire.docs.pivotal.io/910/gemfire/getting_started/installation/install_standalone.html
## Steps

- Open GFSH from the working directory where you want to start your cluster
- Before running below script, make sure you have valid SSL keystore & truststore at the location specified in your security.properties file
- Then run the script start-configure-small-ssl.gfsh
- It might ask you certain properties like keystore type, etc. You can choose to with default. GemFire uses default JKS format (java)
- Verify with list members, list regions commands
- Your cluster is ready to accept SSL client connections

```sh
cd C:\local-gemfire
C:\local-gemfire\gfsh
gfsh>run --file=start-configure-small-ssl.gfsh
```

NOTE: you can refer this KB for more details on how to run an SSL enabled cluster on Windows. https://community.pivotal.io/s/article/How-to-start-SSL-enabled-VMware-GemFire-cluster-on-Windows?language=en_US