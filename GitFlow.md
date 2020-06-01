# Explanation of GitFlow

* Gitflow is a branching model for Git and was created by Vincent Driessen. It has become very popular because it is very beneficial for collaboration and scaling the development team. 

* One of the key benefits with GitFlow is that it makes parallel development easy, by isolating new development from finished work. A “feature branch” is considered a new development (features and non-emergency bug fixes). This is only moved back into the main body of code when the developers are satisfied with the finished product. 

* Another benefit with GitFlow is the collaboration. Feature branches make collaboration easier for two, or more developers who are working on the same feature. Each feature branch can be thought of as a sandbox where the only changes are the changes necessary to get the new feature working. 

* The release staging area is another benefit. As new developments are completed, it will be merged back into the “develop branch”. This is considered a “staging” area for all completed features that haven’t been released yet. As the next release is branched off of “develop”, it will automatically contain the new developments.

* The last mentioned feature is the support for emergency fixes, or “hotfix branches”. This feature allows for an emergency change, or hotfix where this change will only contain the hotfix and not be merged into the new development at this time. 

* The GitFlow is designed to work in this order:

1. New development (new features, non-emergency bug fixes) are built in feature branches
![Image of New Feature](/Images/GitFlowNewFeature1.png)

2. Feature branches are branched off of the develop branch, and finished features and fixes are merged back into the develop branch when they’re ready for release
![Image of Develop Branch](/Images/GitFlowDevelopBranch2.png)

3. When it is time to make a release, a release branch is created off of develop:
![Image of Release Branch](/Images/GitFlowReleaseBranch3.png)

4. The code in the release branch is deployed onto a suitable test environment, tested, and any problems are fixed directly in the release branch. This deploy -> test -> fix -> redeploy -> retest cycle continues until you’re happy that the release is good enough to release to customers. When the release is finished, the release branch is merged into master and into develop too, to make sure that any changes made in the release branch aren’t accidentally lost by new development.
![Image of Release Branch](/Images/GitFlowReleaseBranch4.png)

5. The master branch tracks released code only. The only commits to master are merges from release branches and hotfix branches. Hotfix branches are used to create emergency fixes. 
![Image of Master Branch](/Images/GitFlowMasterBranch5)

6. They are branched directly from a tagged release in the master branch, and when finished are merged back into both master and develop to make sure that the hotfix isn’t accidentally lost when the next regular release occurs.
