{
    "title": "How to install Transfer CFT in a container",
    "linkTitle": "How to install Transfer CFT in a container",
    "weight": "140"
}There are two methods  for installing and operating a containerized Transfer CFT, use either Docker Compose or Kubernetes with Helm. This page describes prerequisites and installation instructions needed to help you install Transfer CFT in a container.

The information in this page may be supplemented, corrected, or even contradicted by the README.md file supplied with the product, in which case the README.md file takes precedence.

## Prerequisites

To get started, you require:

-   For Docker-Compose:
    -   Docker 17.11 and up
    -   Docker-Compose 1.17.0 and up
-   For Kubernetes using Helm:
    -   Kubernetes 1.14 and up
    -   Helm 2.16 and up, or Helm 3 and up

Beyond the prerequisites listed above, the installation instructions for each container option provide links to their own prerequisites.

## Installation procedures

Depending on which method you plan to use, follow the corresponding link to the appropriate installation instructions.

<table data-cellspacing="0">
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Instructions</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Docker Engine</td>
<td><a href="https://docs.docker.com/engine/install/">https://docs.docker.com/engine/install/</a></td>
</tr>
<tr class="even">
<td>Docker-Compose</td>
<td><a href="https://docs.docker.com/compose/install/">https://</a><a href="https://docs.docker.com/compose/install/">docs.docker.com/</a><a href="https://docs.docker.com/compose/install/">compose/install/</a></td>
</tr>
<tr class="odd">
<td>Kubernetes</td>
<td><a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/">https://kubernetes.io/docs/tasks/tools/install-kubectl/</a></td>
</tr>
<tr class="even">
<td>Helm</td>
<td><a href="https://helm.sh/docs/intro/install/">https://helm.sh/docs/intro/install/</a></td>
</tr>
<tr class="odd">
<td>Git</td>
<td><p><a href="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git">https://git-scm.com/book/en/v2/Getting-Started-Installing-Git</a></p></td>
</tr>
</tbody>
</table>

## Download the Transfer CFT repository

Begin by downloading or cloning the Transfer CFT repository. To download, navigate to <https://github.com/Axway/docker-cft> and click **Code** &gt; **Download Zip**. Alternatively, to clone using Git:<span id="gitcontainertest"></span>

<table data-cellspacing="0">
<tbody>
<tr class="odd">
<td><p>git clone <a href="https://github.com/Axway/docker-cft.git">https://github.com/Axway/docker-cft.git</a></p>
<p>cd docker-cft</p></td>
</tr>
</tbody>
</table>

The repository contains several README.md files that correspond to each sub-module, and a CHANGELOG.md file that describes all changes to the current version.

READMEs

Use the following links to find more information in the associated README:

-   Transfer CFT Docker changelog: <https://github.com/Axway/docker-cft/blob/master/CHANGELOG.md>
-   Organizational repository information: <https://github.com/Axway/docker-cft/blob/master/README.md>
-   How to build a Docker image: <https://github.com/Axway/docker-cft/blob/master/docker/README.md>
-   How to use Docker-Compose: <https://github.com/Axway/docker-cft/blob/master/compose/README.md>
-   How to use Kubernetes with Helm:<https://github.com/Axway/docker-cft/blob/master/helm/transfer-cft/README.md>

## Download the Transfer CFT Docker image

You can download the Transfer CFT Docker image from the [Axway support](http://support.axway.com/) site. From the **Downloads** page, search Transfer CFT and click to download the Transfer\_CFT\_&lt;version>\_DockerImage\_allOS\_&lt;BN>.zip.

 
