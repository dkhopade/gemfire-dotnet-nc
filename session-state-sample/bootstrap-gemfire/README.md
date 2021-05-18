# Bootstrap GemFire Cluster
## _Follow these instructions to start local GemFire Cluster_

This step assumes you have downloaded standalone GemFire distribution from https://network.pivotal.io/products/pivotal-gemfire/
To download it you need to login to your account and if you dont have one, then go ahead and create one.
To learn more on how to install and configure local GemFire, please refer to this link: https://gemfire.docs.pivotal.io/910/gemfire/getting_started/installation/install_standalone.html
## Steps

- Open GFSH from the working directory where you want to start your cluster
- Then run the script startcluster.gfsh
- This script uses the JAR file to be deployed on cache servers. Make sure the file is in place that gets added on native client's install directory.
- Verify with list members, list regions commands
- Your cluster is ready to accept client connections

```sh
cd C:\local-gemfire
C:\local-gemfire\gfsh
gfsh>run --file=startcluster.gfsh
```