# RancherOS

The smallest, easiest way to run Docker in production at scale.  Everything in RancherOS is a container managed by Docker.  This includes system services such as udev and rsyslog.  RancherOS includes only the bare minimum amount of software needed to run Docker.  This keeps the binary download of RancherOS very small.  Everything else can be pulled in dynamically through Docker.

## How this works

Everything in RancherOS is a Docker container.  We accomplish this by launching two instances of
Docker.  One is what we call the system Docker which runs as the first process.  System Docker then launches
a container that runs the user Docker.  The user Docker is then the instance that gets primarily
used to create containers.  We created this separation because it seemed logical and also
it would really be bad if somebody did `docker rm -f $(docker ps -qa)` and deleted the entire OS.

![How it works](docs/rancheros.png "How it works")

## Latest Release

**v0.6.0 - Docker 1.12.1 - Linux 4.4.16**

### ISO

https://releases.rancher.com/os/latest/rancheros.iso  
https://releases.rancher.com/os/v0.6.0/rancheros.iso  

### Additional Downloads

#### Latest

* https://releases.rancher.com/os/latest/initrd
* https://releases.rancher.com/os/latest/iso-checksums.txt
* https://releases.rancher.com/os/latest/rancheros-openstack.img
* https://releases.rancher.com/os/latest/rancheros-raspberry-pi.zip
* https://releases.rancher.com/os/latest/rancheros-v0.6.0.tar.gz
* https://releases.rancher.com/os/latest/rancheros.iso
* https://releases.rancher.com/os/latest/rootfs_arm.tar.gz
* https://releases.rancher.com/os/latest/rootfs_arm64.tar.gz
* https://releases.rancher.com/os/latest/rootfs.tar.gz
* https://releases.rancher.com/os/latest/vmlinuz



#### v0.6.0

* https://releases.rancher.com/os/v0.6.0/initrd
* https://releases.rancher.com/os/v0.6.0/iso-checksums.txt
* https://releases.rancher.com/os/v0.6.0/rancheros-openstack.img
* https://releases.rancher.com/os/v0.6.0/rancheros-raspberry-pi.zip
* https://releases.rancher.com/os/v0.6.0/rancheros-v0.6.0.tar.gz
* https://releases.rancher.com/os/v0.6.0/rancheros.iso
* https://releases.rancher.com/os/v0.6.0/rootfs_arm.tar.gz
* https://releases.rancher.com/os/v0.6.0/rootfs_arm64.tar.gz
* https://releases.rancher.com/os/v0.6.0/rootfs.tar.gz
* https://releases.rancher.com/os/v0.6.0/vmlinuz



**Note**: you can use `http` instead of `https` in the above URLs, e.g. for iPXE.  

### Amazon

SSH keys are added to the **`rancher`** user, so you must log in using the **rancher** user.

**HVM**

Region | Type | AMI |
-------|------|------
ap-northeast-1 | HVM |  [ami-1e34ff7f](https://console.aws.amazon.com/ec2/home?region=ap-northeast-1#launchInstanceWizard:ami=ami-1e34ff7f)
ap-northeast-2 | HVM |  [ami-a7f227c9](https://console.aws.amazon.com/ec2/home?region=ap-northeast-2#launchInstanceWizard:ami=ami-a7f227c9)
ap-southeast-1 | HVM |  [ami-c4d308a7](https://console.aws.amazon.com/ec2/home?region=ap-southeast-1#launchInstanceWizard:ami=ami-c4d308a7)
ap-southeast-2 | HVM |  [ami-60c5f303](https://console.aws.amazon.com/ec2/home?region=ap-southeast-2#launchInstanceWizard:ami=ami-60c5f303)
eu-central-1 | HVM |  [ami-caf704a5](https://console.aws.amazon.com/ec2/home?region=eu-central-1#launchInstanceWizard:ami=ami-caf704a5)
eu-west-1 | HVM |  [ami-90790be3](https://console.aws.amazon.com/ec2/home?region=eu-west-1#launchInstanceWizard:ami=ami-90790be3)
sa-east-1 | HVM |  [ami-000d9c6c](https://console.aws.amazon.com/ec2/home?region=sa-east-1#launchInstanceWizard:ami=ami-000d9c6c)
us-east-1 | HVM |  [ami-827b1395](https://console.aws.amazon.com/ec2/home?region=us-east-1#launchInstanceWizard:ami=ami-827b1395)
us-west-1 | HVM |  [ami-1affb27a](https://console.aws.amazon.com/ec2/home?region=us-west-1#launchInstanceWizard:ami=ami-1affb27a)
us-west-2 | HVM |  [ami-7adf0e1a](https://console.aws.amazon.com/ec2/home?region=us-west-2#launchInstanceWizard:ami=ami-7adf0e1a)
ap-south-1 | HVM |  [ami-4593e62a](https://console.aws.amazon.com/ec2/home?region=ap-south-1#launchInstanceWizard:ami=ami-4593e62a)

### Google Compute Engine

We are providing a disk image that users can download and import for use in Google Compute Engine. The image can be obtained from the release artifacts for RancherOS.

[Download Image](https://github.com/rancher/os/releases/download/v0.6.0/rancheros-v0.6.0.tar.gz)

Please follow the directions at our [docs to launch in GCE](http://docs.rancher.com/os/running-rancheros/cloud/gce/).

## Documentation for RancherOS

Please refer to our [RancherOS Documentation](http://docs.rancher.com/os/) website to read all about RancherOS. It has detailed information on how RancherOS works, getting-started and other details.

## Support, Discussion, and Community
If you need any help with RancherOS or Rancher, please join us at either our [Rancher forums](http://forums.rancher.com) or [#rancher IRC channel](http://webchat.freenode.net/?channels=rancher) where most of our team hangs out at.

Please submit any **RancherOS** bugs, issues, and feature requests to [rancher/os](//github.com/rancher/os/issues).

Please submit any **Rancher** bugs, issues, and feature requests to [rancher/rancher](//github.com/rancher/rancher/issues).

#License
Copyright (c) 2014-2016 [Rancher Labs, Inc.](http://rancher.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
