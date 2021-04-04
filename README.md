<!---
.. ===============LICENSE_START=======================================================
.. Acumos CC-BY-4.0
.. ===================================================================================
.. Copyright (C) 2018 AT&T Intellectual Property & Tech Mahindra. All rights reserved.
.. ===================================================================================
.. This Acumos documentation file is distributed by AT&T and Tech Mahindra
.. under the Creative Commons Attribution 4.0 International License (the "License");
.. you may not use this file except in compliance with the License.
.. You may obtain a copy of the License at
..
..      http://creativecommons.org/licenses/by/4.0
..
.. This file is distributed on an "AS IS" BASIS,
.. WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
.. See the License for the specific language governing permissions and
.. limitations under the License.
.. ===============LICENSE_END=========================================================
-->

# AI4EU Acumos System Integration

This repository holds installation and deployment scripts for the AI4EU Acumos system.

Preconditions:
* Ubuntu 20.04
* Docker installed and docker service enabled and started 
* Installation user created that belongs to groups docker and sudo, in this example the user is ai4eu
* /etc/hosts has exactly one entry for the FQHN pointing to the externel ipv4 interface
* /etc/hosts must not contain a 127.0.1.1 entry with hostname
* optionally letsencrypt certificates installed

Become user ai4eu (installation user)

clone this repo and the correct branch

    cd system-integration/tools
    bash setup_k8s.sh 
    bash setup_helm.sh
    cd $HOME
    # replace FGHN appropriately
    bash system-integration/AIO/setup_prereqs.sh k8s FQHN $USER generic | tee log_prereqs.txt
    cd system-integration/AIO/
    bash oneclick_deploy.sh | tee log_oneclick.txt



