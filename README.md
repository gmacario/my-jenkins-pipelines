# Various Jenkins Pipeline demos

Gradually accumulating more over time - one on each branch!

### System Requirements

* [Jenkins 2.46](https://jenkins.io/) or greater with the following installed plugins:
  - [Blue Ocean Plugin 1.0.0](https://wiki.jenkins-ci.org/display/JENKINS/Blue+Ocean+Plugin)
  - [Pipeline Multibranch Plugin 2.14](https://wiki.jenkins-ci.org/display/JENKINS/Pipeline+Multibranch+Plugin)
  - **NOTE**: You may use [easy-jenkins](https://github.com/gmacario/easy-jenkins) to install all the prerequisites
* Lot of time, network bandwidth and disk space...


### Installing using Blue Ocean (NEW)

Jenkins: Manage Jenkins > Manage Nodes > master > Configure

* Labels: `docker`

then click **Save**.

Jenkins: Open Blue Ocean

Click **Create a new Pipeline**

* Where do you store your code? **Github**

* Connect to Github
  > Jenkins needs an access key to authorize itself with Github.
  > Create an access key here.
  
* Click on link **Create an access key here**
  
* New personal access token
  - Token description: `easy-jenkins on ies-genbld01-ub16`
  - Select scopes: "repo, read:user, user:email", then click **Generate token**
  
* Copy your personal access token

* Paste access token to blueocean "Create Pipeline" page, then click **Connect**

* Which organization does the repository belong to? **gmacario**

* Create a signle Pipeline or discover all Pipelines: **New Pipeline**

* Choose a repository: **my-jenkins-pipelines**, then click **Create Pipeline**

* Wait until the pipeline becomes green


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


### Documentation on Declarative Pipeline

* [Pipeline as code](https://jenkins.io/doc/book/pipeline-as-code/)
* [Pipeline Syntax Reference](https://jenkins.io/doc/book/pipeline/syntax/)
* [Pipeline Steps Reference](https://jenkins.io/doc/pipeline/steps/)
* [Declarative Pipeline Quick Reference](https://www.cloudbees.com/sites/default/files/declarative-pipeline-refcard.pdf) (PDF, 2 pages)

#### Blog posts on jenkins.io

* [Declarative Pipeline: Notifications and Shared Libraries](https://jenkins.io/blog/2017/02/15/declarative-notifications/) - jenkins.io blog, 2017-02-15
* [Declarative Pipeline: Publishing HTML Reports](https://jenkins.io/blog/2017/02/10/declarative-html-publisher/) - jenkins.io blog, 2017-02-10
* [Declarative Pipeline for Maven Projects](https://jenkins.io/blog/2017/02/07/declarative-maven-project/) - jenkins.io blog, 2017-02-07
* [Declarative Pipeline Syntax 1.0 is now available](https://jenkins.io/blog/2017/02/03/declarative-pipeline-ga/) - jenkins.io blog, 2017-02-03

#### Repositories with Jenkins Pipeline examples

* <https://github.com/jenkinsci/pipeline-examples>
* <https://github.com/abayer/misc-pipeline-demos>

#### Other links

* [Continuous Delivery With Jenkins Workflow](https://dzone.com/refcardz/continuous-delivery-with-jenkins-workflow) - DZone Refcard #218

<!-- EOF -->
