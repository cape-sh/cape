<p align="center" style="background-color:#23327c">
  <img src="https://biqmind.com/wp-content/uploads/2020/07/CAPE-4CLogo-Hor.png"/>
</p>
<p align="center">
  <a href="#features">Features</a> •
  <a href="#install">Install</a> •
  <a href="#Learn">Learn</a> •
  <a href="#license">License</a> •
  <a href="#support">Support</a> 

</p>

# Advanced Kubernetes Multi-cluster Application & Data Management

CAPE provides advanced Kubernetes features for Disaster Recovery, Data Migration & Mobility, Multi-cluster Application Deployment and CI/CD within a single, intuitive interface.

Deploy advanced K8s functionalities without the learning curve. This repo is for tracking community issues and feedback. Try CAPE today and let us know what you think!

<hr/>

<p align="center" style="background-color:#23327c">
  <img src="https://biqmind.com/wp-content/uploads/2020/07/cape-dashboard-clusters.png" />
</p>

[![CAPE](assets/youtube-cape.png)](https://youtu.be/4KJt8NXTO8E "CAPE INTRO")


## Features

1. <b>Disaster Recovery</b>
- Single & scheduled backup & restore 
- Multi-cluster & multi-cloud backup & restore 
 
2. <b>Data Migration & Mobility</b>
- Secure, encrypted application & data at rest and in transit
- Support for on-prem, private cloud, major public clouds and edge

3. <b>Multi-cluster Application Deployment</b>
- End-to-end deployment, from application definition to application release
- Support for multiple types of application environments

4. <b>Drag & Drop CI/CD Workflow Manager (In development)</b>
- Build, Test & Deploy across multiple cloud providers or on-premises systems
- Standardize CI/CD tooling & processes across vendors & deployment environments

<hr /> 

## Install

### Start k3d local instance
Prerequisites:
- [docker](https://docs.docker.com/get-docker/)
- [k3d](https://github.com/rancher/k3d) (install latest version > 3)

```sh
k3d cluster create dev -p 443:443@loadbalancer -p 80:80@loadbalancer --agents=0 --wait
export KUBECONFIG="$(k3d kubeconfig write dev)"
kubectl cluster-info
````
Note: The Kubernetes cluster "dev" has been created locally

### Install CAPE
> By running the following command, I have read and agree to CAPE [privacy policy](https://biqmind.com/privacy-policy/), [terms of service](https://biqmind.com/terms-of-service/) and [end user license agreement](https://biqmind.com/end-user-license-agreement/)
```
kubectl apply -f https://cape.sh/install/simple.yaml

kubectl set env deploy/web CAPE_ACCEPT_TOS=true -n cape
```

### Access CAPE UI
> Enter the following command:
```
kubectl -n cape wait --for=condition=available --timeout=600s deployment/web
#wait for completion of CAPE deployment
open http://127.0.0.1.nip.io
```
Please wait for CAPE deployment to complete and open a new tab with the following URL: http://127.0.0.1.nip.io

<hr />

After accessing the CAPE UI, we recommend you to go through our videos for a walkthrough of the various use cases. 

## Learn

- [Recent Webinar](https://www.youtube.com/watch?v=JHP9zgv75ls)
- [CAPE Tutorials](https://www.youtube.com/watch?v=S551qxe9vCg&list=PLByzHLEsOQEB01EIybmgfcrBMO6WNFYZL)
- [Katacoda](https://katacoda.com/cape/courses/trycape/) 

## Use CAPE on Your Favorite Platforms
CAPE is also avaliable for the following deployment platforms:
- [Ansible](https://github.com/cape-sh/cape-ansible)
- [Azure](https://github.com/cape-sh/cape-azure)
- [Docker Hub](https://hub.docker.com/u/capesh)
- [Github](https://github.com/cape-sh/cape-docker)
- [Helm Charts](https://hub.helm.sh/charts/cape/cape)
- [OperaterHub]-> Coming soon


## Environments Supported

For CAPE Version V1.0.0
- Alibaba Cloud
- AWS
- Azure
- DigitalOcean
- GCE
- Huawei Cloud
- Tencent Cloud

## License
CAPE is available as an always FREE Community Edition or as an Enterprise Plan with dedicated support.


## Support

### Videos

#### CAPE UI Features Walkthrough
- [Key Menus](https://www.youtube.com/watch?v=S551qxe9vCg)

#### Clusters Walkthrough
- [Create Organization](https://www.youtube.com/watch?v=rjfZ_Av-Mxg)
- [Connect Biqmind CAPE to a K8s cluster using Kubectl](https://www.youtube.com/watch?v=CSW4IrjyGro)
- [Connect Biqmind CAPE to a K8s cluster using Kubeconfig](https://www.youtube.com/watch?v=pvfDTnu-HLI)
- [Install a disaster recovery component](https://www.youtube.com/watch?v=74t6jKB9G3E)

#### Backups Walkthrough
- [Backup K8s on-demand](https://www.youtube.com/watch?v=MOPtRTeG8sw)
- [Schedule a K8s Backup](https://www.youtube.com/watch?v=CkIVZdmWXiQ)
- [Share backup with other clusters](https://www.youtube.com/watch?v=tnyNPynPLJI)

#### Restores Walkthrough
- [Restoring a Kubernetes cluster](https://www.youtube.com/watch?v=Xf0TkzudUF0)
- [Restoring a Kubernetes cluster to another cluster](https://www.youtube.com/watch?v=dhBnUgfTsh4)

### Documentation
- Get started with CAPE [Docs](https://docs.cape.sh/docs/).

### Contribute
We welcome contributions from the community:
- Bug reports and feature requests through [Github issues](https://github.com/cape-sh/cape/issues/new)

### Contact
Connect with us on our mailing list or Slack:
- [<img src="https://img.shields.io/badge/Slack-CAPE-brightgreen">](https://capesh.slack.com)

Our Youtube channel:
- [<img src="https://img.shields.io/badge/Youtube-Biqmind-blue">](https://www.youtube.com/channel/UCSXtrXokSgbZuSz7qgu3VHw)

If you like our project,
![Twitter Follow](https://img.shields.io/twitter/follow/CapeSuperhero?style=social) and 
![GitHub stars](https://img.shields.io/github/stars/cape-sh/cape?style=social)  

