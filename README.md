# Various Pipeline demos

Gradually accumulating more over time - one on each branch!

### System Requirements

* [Jenkins v2.32](https://jenkins.io/) or greater with the following installed plugins:
  - [Blue Ocean Plugin v1.0.0-b23](https://wiki.jenkins-ci.org/display/JENKINS/Blue+Ocean+Plugin)
  - [Pipeline Multibranch Plugin v2.12](https://wiki.jenkins-ci.org/display/JENKINS/Pipeline+Multibranch+Plugin)
  - **NOTE**: You may use [easy-jenkins](https://github.com/gmacario/easy-jenkins) to install all the prerequisites
* Lot of time, network bandwidth and disk space...

### Installing in a Jenkins MultiBranch pipeline

Jenkins: Manage Jenkins > Manage Nodes > master > Configure

* Labels: `docker`

then click **Save**.

Jenkins: New Item

* Name: `my-jenkins-pipelines`
* Type: **Multibranch Pipeline**

then click **OK** and configure job:

* Branch Sources: Add source > Git
  - Project Repository: `https://github.com/gmacario/my-jenkins-pipelines`

then click **Save**.

### See also

* [Declarative Pipeline Quick Reference](https://www.cloudbees.com/sites/default/files/declarative-pipeline-refcard.pdf) (PDF, 2 pages)

<!-- EOF -->
