# CICFlowMeter

# Install on Ubuntu 20.04

```bash
apt install maven gradle openjdk-8-jdk

git clone https://github.com/ahlashkari/CICFlowMeter.git

//linux :at the pathtoproject/jnetpcap/linux/jnetpcap-1.4.r1425
//windows: at the pathtoproject/jnetpcap/win/jnetpcap-1.4.r1425
cd CICFlowMeter/jnetpcap/linux/jnetpcap-1.4.r1425
mvn install:install-file -Dfile=jnetpcap.jar -DgroupId=org.jnetpcap -DartifactId=jnetpcap -Dversion=1.4.1 -Dpackaging=jar

# Make package
# cd to CICFlowMeter
cd ../../../
gradle clean
gradle build

# The .tar and .zip files will be in the pathtoproject/CICFlowMeter/build/distributions
```

## Fix for generate csv in linux 
https://github.com/ahlashkari/CICFlowMeter/pull/85  
```
### For Linux: (x64)
Install libpcap-dev using:
1. $ sudo apt-get install libpcap-dev
2. Go to the jnetpcap folder inside CICFlowMeter/jnetpcap/linux/jnetpcap-1.4.r1425
3. Copy libjnetpcap.so and libjnetpcap-pcap100.so in /usr/lib/ (as sudo).
```


# Using CICFlowMeter

Unpack zip package in CICFlowMeter/build/distributions.
```bash
cd CICFlowMeter-4.0/bin
# cfm : command line
# CICFlowMeter : graphical application
/cfm file.pcap <outdir>
# output file is file.pcap_Flow.csv
```