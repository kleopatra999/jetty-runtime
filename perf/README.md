## Perf app

### Test webapp
The submodule `jetty-load-generator-app` contains a simple webapp which can be deploy to gcloud using with activating the `gcloud-deploy` profile `-Pgcloud-deploy`:

`mvn install -Pgcloud-deploy -Dgcloud.sdk.path=<path to your gcloud sdk directory>`  

This contains a very simple webapp with static resources and a basic servlet.

### Load testing
Load testing can be performed using the following command:

`mvn clean install -Pperf -Prun-perf -DskipTests -Drunning.time.unit=s -Dwarmup.number=5 -Drunning.time=30 -Dusers=20`

You can define a number of parameters for the testing including the numbers of users (`-Dusers`) and running time (`-Drunning.time`).

To deploy new version add the profile `-Pgcloud-deploy`