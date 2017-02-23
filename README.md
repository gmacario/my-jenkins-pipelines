# Various Pipeline demos

Gradually accumulating more over time - one on each branch!

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
