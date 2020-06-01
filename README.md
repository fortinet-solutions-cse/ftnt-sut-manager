# Fortinet System under test manager 

Goal have a low cost (license) and fast way to build Fortinet system for testing api based test.

Allow to test several versions and several configuration in a reproduceable manner.

Mainly used by the tests part of fortiosapi.

# Usage
You must be in libvirt group

define variables for flavor and version.
```
export flavor=myvdom
export fgtversion=FGT-6.4.0
```

Optionally define 
```
export FTNT_SUT_FGT_HOME=/home/test/ftnt-sut-manager/fortigate
export JENKINS_HOME=/home/test/temp
export BRIDGE=mybridge
```

Those will be set by default, if you are in fortigate subfolder:
```
export FTNT_SUT_FGT_HOME=$PWD/fortigate/
export JENKINS_HOME=$PWD
export BRIDGE=docker0
```

flavor correspond to examples in flavors folder, fortigate/versions-build.json match the FGT version to its build number.
You must download from https://support.fortinet.com
the KVM .zip file of the Fortigate under test and place it zipped in the version folder.

Under flavors you create check the examples for building the config, add a license file and can link in 
flavors/ folder to <flavor>.lic.
Example
```
cd flavors
ln -f FGVM0XXXXX.lic vdom.lic
```
The license file per flavor will be taken from there.

# Build


