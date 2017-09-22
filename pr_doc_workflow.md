# Documentation Pull Request Acceptance Workflow

## <a name="pre"></a>Prerequisite
To contribute to the documentation, you first need to sign the
[Oracle Contributor Agreement](http://www.oracle.com/technetwork/community/oca-486395.html).
When filling the OCA make sure to include your GitHub username. If you signed the OCA previously and your GitHub
username wasn't included, just ping [David Delabassee](mailto:david.delabassee(@)oracle.com) to fix this.
Once your OCA has been approved, you'll be able to work directly with the respective project/module owners or
reviewers to get your Pull Request reviewed and approved. The OCA process doesn't apply to Oracle employees.

## One Time Setup
* [Fork](https://help.github.com/articles/fork-a-repo/) the [tutorial](https://github.com/javaee/tutorial/) repository.
* [Clone](https://help.github.com/articles/cloning-a-repository/) your forked repository.
```
$ git clone https://github.com/javaee/tutorial.git
```
* [Configure](https://help.github.com/articles/configuring-a-remote-for-a-fork/) the remote for your fork.
```
$ git remote add upstream https://github.com/javaee/tutorial.git
$ git remote -v
origin    https://github.com/your-githubid/tutorial.git (fetch)
origin    https://github.com/your-githubid/tutorial.git (push)
upstream    https://github.com/javaee/tutorial.git (fetch)
upstream    https://github.com/javaee/tutorial.git (push)
```
## Raising a Pull Request
* Sync the master of your fork with upstream master.
```
$ git fetch upstream
$ git checkout master
$ git merge upstream/master
$ git push origin master #push local master to github fork.
```
* Create a local topic branch in your fork from your master.
```
$ git checkout -b doc_update
```
* Do the development in your branch.
* Commit all the changes.
```
$ git add src/main/jbake/content/my.adoc
$ git commit -m "my commit message"
 ```
 * Push your changes in a remote branch of your fork.
 ```
 $ git push origin doc_update
 ```
* Before raising a Pull Request, please raise an [issue](https://github.com/javaee/tutorial/issues) if it doesn't
exist. We would like every Pull Request to be associated with an issue. Submit the Pull Request referring to the issue
number.
* Raise a [Pull Request](https://github.com/javaee/tutorial/pulls).
* Make sure you put a proper 'title' for the Pull Request. The title of the Pull Request would become the commit
message. Instead of giving 'title' like "Iss xxxx" or "Fixes #xxxxx", consider giving a proper one line 'title' for
the Pull Request like "Fixes xxx : <brief description about the issue/fix>"
* In the Pull Request description (body), please mention "Fixes #xxxxx" in order to link the Pull Request with the
Issue you are fixing.
* If you have signed the OCA, one of the GlassFish team members will review your Pull Request. If you have not signed
an OCA, see [Prerequisite](#pre).
