[![Autonomiccs Platform](tools/project-logo/autonomiccs.png)](http://autonomiccs.com.br)

###Project status: [![Build Status](http://jenkinsbadge.autonomiccs.com.br/buildStatus/icon?job=Autonomiccs-platform)](http://jenkins.autonomiccs.com.br/job/Autonomiccs-platform/) <a href="https://scan.coverity.com/projects/autonomiccs-platform"><img alt="Coverity Scan Build Status" src="https://scan.coverity.com/projects/8610/badge.svg"/></a><a style="padding-right: 2px; padding-left: 1px;" href="https://sonar.autonomiccs.com.br/"><img alt="Sonar quality gate" src="http://sonarbadges.autonomiccs.com.br/api/badges/gate?key=autonomic-platform"/></a><a href="https://sonar.autonomiccs.com.br/" style="padding-right: 2px;" ><img alt="Code coverage" src="http://sonarbadges.autonomiccs.com.br/api/badges/measure?key=autonomic-platform&metric=overall_coverage"/></a><a href="https://sonar.autonomiccs.com.br/" style="padding-right: 2px;" ><img alt="duplicated lines density" src="http://sonarbadges.autonomiccs.com.br/api/badges/measure?key=autonomic-platform&metric=duplicated_lines_density"/></a><a href="https://sonar.autonomiccs.com.br/" style="padding-right: 2px;" ><img alt="bugs" src="http://sonarbadges.autonomiccs.com.br/api/badges/measure?key=autonomic-platform&metric=bugs"/></a> 
 
In a nut shell, Autonomiccs is a distributed virtual machine scheduling (A.K.A distributed resource scheduling) for Apache CloudStack.

The Autonomiccs platform is an open source system that is capable of managing and optimizing an IaaS cloud computing environment autonomously. The system is developed as a plugin to <a href="https://github.com/apache/cloudstack">Apache CloudStack</a>. Our mission is to take the orchestration of cloud computing infrastructures to the next level. To achieve that, we have developed a distributed and autonomic plugin that can monitor a CC environment and take decisions in order to fulfill administrative goals. We do not wish to remove the need for human administrators, but to improve their work. Our mission involves optimizing and making CC environments more efficient and stable without the need to rely on human administrators.

The plugin is stable on CloudStack 4.6 and beyond, and was designed to have a smooth installation and upgrade process. Currently, all algorithms that do not shut down idle hosts are working with every type of hypervisor supported by ACS; however, the consolidation algorithms are available only for XenServer and XCP (it is a matter of time and resources to implement our platform for all hypervisors supported by ACS).

## Motivation

Over the past years, cloud computing (CC) usage has increased. To meet that demand the infrastructure required to create and maintain CC environments grows constantly, which impacts on management costs. Thus, the optimization of those environments has become infeasible to human administrators, requiring an autonomic approach.

Even so, we still do not see autonomic management solutions being used in current commercial orchestration tools such as Apache CloudStack and OpenStack. This project provides a solution capable of improving the management of virtual machines and physical servers orchestrated by Apache CloudStack. Our solution aims to optimize the cloud provider infrastructure, by ensuring the fulfillment of its goals.

## Solution

In summary, our agents can move workloads around, allowing idle servers to power off; those agents are also able to balance the load throughout the whole environment and manage the service level agreements between providers and clients. The plugin was designed to be flexible and strive to achieve different goals regarding the management of cloud computing environments.

We had already developed a set of algorithms that strive to achieve some specific goals; e.g. (i) reduce the energy consumption by migrating the workloads of VMs and powering off idle hosts; (ii) distribute VMs among hosts to balance resource usage. These algorithms and their usage are explained at the <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Heuristics">heuristics</a> page.

### Balancing workload

In this approach, the environment workload will constantly be balanced. It seeks to migrate virtual machines among hosts in order to keep the resource usage of each host close to a given average.

The following figure depicts the autonomic system balancing the workload of a given scenario:
<p align="center">
	<img src="tools/figures/balancing.jpg" width="280">
</p>

### Powering off idle hosts

This solution strives to power off as many hosts as possible. The goal of this approach is to reduce energy-related costs for running a CC environment  by powering off idle hosts.

By using this heuristic one should be able to cut their energy costs and the need for maintenance caused by unnecessary use of idle resources. Moreover, as the concerns with pollution caused by the use of unclean sources of energy have grown, governments and consumers are willing to prefer companies that invest in green solutions, in favor of companies that do not.

The following figure depicts the autonomic system consolidating a given scenario:
<p align="center">
	<img src="tools/figures/consolidation.jpg" width="280">
</p>


## Project evolution

This project is still in its infancy. To provide an idea of the big picture and our development plan, we have listed some of our goals here:

- user interface to the management plugin;
- autonomic monitoring platform;
- user interface to the monitoring platform;
- analysis and forecasting of virtual machines profile to enhance the virtual machine placement;
- projection of virtual machines workload, enabling the activation of hosts before the demand happens;
- prediction of service degradation that is caused by collocated VMs and migration before the service degradation takes place.

The aforementioned goals contribute toward an autonomic monitoring platform and a component to perform analysis on the monitored data; with that, our agents' decisions can be improved through the use of artificial intelligence techniques. Also, the user interface gives the environment administrator a greater understanding of the infrastructure and its workload behavior.

## Who is Autonomiccs for?

Our main focus is to get CloudStack to the next generation of cloud computing orchestration platforms. One who shares our enthusiasm may benefit from this project.
    
We foresee the following types of users for this platform:
- companies that use Apache CloudStack;
- companies that provide Apache CloudStack consulting and support services to other companies;
- Cloud Computing research labs;

The first user of this solution is the Network and Management Laboratory of the Federal University of Santa Catarina (<a href="https://wiki.lrg.ufsc.br/">LRG</a>).

## Getting Started

- Please, follow the installation instructions on the <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Installation">Installation</a> wiki page;
- once it is installed, please check our documentation to understand our plugin <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Usage">usage</a>.
 
## Getting source repository

The Autonomiccs Platform project uses Git and a mirror is hosted on GitHub. To access our master source code, click <a href="https://github.com/Autonomiccs/autonomiccs-platform">here</a>. The latest stable version of the Autonomiccs platform source code is: <a href="https://github.com/Autonomiccs/autonomiccs-platform/tree/1.0.2">1.0.2</a>.

The Github mirror allows users and developers to explore the code; contributions from the community may only be done via Github pull requests.

## Getting involved
The Autonomiccs project welcomes anybody interested in working towards the development of a Cloud Computing autonomic management solution.

You do not need to be a developer to contribute to this project, we are pleased to receive any contribution. We need people that can help with documentation, promotion, design, research and other tasks that are essential to the project life cycle.

### Mailing lists
If you have doubts, problems, suggestions, critics or anything else that can help us improve, you are more than welcome to join us in our mailing lists. We have two distinct mailing lists; one that focuses on users of the Autonomiccs platform; and the other that is directed to the developers of the platform.

We highlight that all participants on the mailing lists are expected to treat one another professionally and politely.
#### Subscribing
If you want to subscribe to a list, send an email to <listname>-subscribe@autonomiccs.com.br:
* To join the users mailing list you should send an email to: users-subscribe@autonomiccs.com.br
* To join the developers mailing list you should send an email to: devs-subscribe@autonomiccs.com.br

#### Unsubscribing
If you have decided that you are getting too much mail and want to cancel your subscription from one of the lists you should send an email to <listname>-unsubscribe@autonomiccs.com.br from the same email you subscribed with.
* To leave the users mailing list you should send an email to: users-unsubscribe@autonomiccs.com.br
* To leave the developers mailing list you should send an email to: devs-unsubscribe@autonomiccs.com.br

## More details
Please, go to our <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki">wiki</a> page for more details; there you can understand more about the <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Autonomiccs-platform">Autonomiccs platform</a>, some <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Basic-concepts">basic concepts</a>, what are <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Heuristics">heuristics</a> and how we use it, how to <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Installation">install</a> and <a href="https://github.com/Autonomiccs/autonomiccs-platform/wiki/Usage">use</a>.

You can find more about Autonomiccs visiting the [website](http://autonomiccs.com.br).

## Licence

This project is part of Autonomiccs, an open source autonomic cloud computing management platform. Copyright (C) 2016 Autonomiccs, Inc.

Licensed to the Autonomiccs, Inc under one or more contributor license agreements.  See the NOTICE file distributed with this work for additional information regarding copyright ownership.  The ASF licenses this file to you under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License.  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.  See the License for the specific language governing permissions and limitations under the License.

Please see the <a href="https://github.com/Autonomiccs/autonomiccs-platform/blob/master/LICENSE">LICENSE</a> file included in the root directory of the project for more details.

<p align="center">
	<img src="https://github.com/Autonomiccs/autonomiccs-platform/blob/master/tools/project-logo/autonomiccsWhite.png" width="150">
</p>
