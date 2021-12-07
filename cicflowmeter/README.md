# CICFlowMeter
CICFlowMeter is a network traffic flow generator and analyser.  
https://www.unb.ca/cic/research/applications.html  
https://github.com/ahlashkari/CICFlowMeter  

:warning: Needs coding to get timestamp in microseconds. See https://github.com/lbfiorino/CICFlowMeter.

# Install on Ubuntu 20.04

## Requirements
- JDK 8 (`sourceCompatibility = 1.8` in `build.gradle`)
- Maven
- Gradle

```bash
# Install requirements
apt install openjdk-8-jdk maven gradle
```

## Build CICFlowMeter

### Install jnetpcap
```bash
//linux: at the pathtoproject/jnetpcap/linux/jnetpcap-1.4.r1425
//windows: at the pathtoproject/jnetpcap/win/jnetpcap-1.4.r1425

# Linux
# at root directory of this repository
cd CICFlowMeter/jnetpcap/linux/jnetpcap-1.4.r1425
sudo mvn install:install-file -Dfile=./jnetpcap/linux/jnetpcap-1.4.r1425/jnetpcap.jar -DgroupId=org.jnetpcap -DartifactId=jnetpcap -Dversion=1.4.1 -Dpackaging=jar

# Windows (use quotation marks)
# at root directory of this repository
mvn install:install-file -Dfile=".\jnetpcap\win\jnetpcap-1.4.r1425\jnetpcap.jar" -DgroupId="org.jnetpcap" -DartifactId=jnetpcap -Dversion="1.4.1" -Dpackaging=jar
```

### Build

#### From IntelliJ IDEA
1. Open folder project in IntelliJ IDEA;
2. Choose 'Gradle Project';
3. Open terminal in the IDE (Alt+F12)
4. In project root directory type: 
   linux: ./gradlew execute
   windows: gradlew execute


#### From console 
```bash
git clone https://github.com/ahlashkari/CICFlowMeter.git

# Make package
# cd to CICFlowMeter
cd ../../../
gradle clean
gradle build

# The .tar and .zip files will be in the pathtoproject/CICFlowMeter/build/distributions
```

### Fix for generate csv in linux 
https://github.com/ahlashkari/CICFlowMeter/pull/85  
:warning: It was not necessary. 

```
### For Linux: (x64)
Install libpcap-dev using:
1. $ sudo apt-get install libpcap-dev
2. Go to the jnetpcap folder inside CICFlowMeter/jnetpcap/linux/jnetpcap-1.4.r1425
3. Copy libjnetpcap.so and libjnetpcap-pcap100.so in /usr/lib/ (as sudo).
```


# Using CICFlowMeter

Unpack tar/zip package in CICFlowMeter/build/distributions.
```bash
cd CICFlowMeter-4.0/bin
# cfm : command line
# CICFlowMeter : graphical application
/cfm file.pcap <outdir>
# output file is file.pcap_Flow.csv
```
