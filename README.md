# sync-test
this is a repositry for testing devop sync pipeline

Last login: Fri Jan 27 14:41:43 on ttys006

The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.
(base) Marshmallow-ProMax:~ mkhael$ docker run -u 0 -it --entrypoint /bin/sh docker.io/alpine/git:latest
/git # mkdir testfield
/git # cd testfield
/git/testfield # GITSRCREPO='github.com/aquasecurity/trivy-db.git'
/git/testfield # GITSRCREPONAME='trivy-db.git'
/git/testfield # AZUREREPOPAT='###Something'
/git/testfield # AZUREPO='dev.azure.com/#some/#where/_git/trivy-db.git'
/git/testfield # sourceURL="https://$GITSRCREPO"
/git/testfield # destURL="https://$AZUREREPOPAT@$AZUREPO"
/git/testfield # git clone --mirror $sourceURL
Cloning into bare repository 'trivy-db.git'...
remote: Enumerating objects: 8141, done.
remote: Counting objects: 100% (245/245), done.
remote: Compressing objects: 100% (127/127), done.
remote: Total 8141 (delta 141), reused 196 (delta 108), pack-reused 7896
Receiving objects: 100% (8141/8141), 11.27 MiB | 6.87 MiB/s, done.
Resolving deltas: 100% (4501/4501), done.
/git/testfield # /testfield # cd trivy-db.git/
/bin/sh: /testfield: not found
/git/testfield # cd $GITSRCREPONAME
/git/testfield/trivy-db.git # git remote rm origin
Note: Some branches outside the refs/remotes/ hierarchy were not removed;
to delete them, use:
  git branch -d feat/get-ids-from-refs
  git branch -d feat/vendor-status
  git branch -d feat/wolfi-advisories
  git branch -d fix/remove-rejected-for-rhsa
  git branch -d github-releases
  git branch -d main
  git branch -d override-vulns
/git/testfield/trivy-db.git # git remote add --mirror=fetch origin $destURL
/git/testfield/trivy-db.git # git fetch $sourceURL
From https://github.com/aquasecurity/trivy-db
 * branch            HEAD       -> FETCH_HEAD
/git/testfield/trivy-db.git # git push origin --all -f
Everything up-to-date
/git/testfield/trivy-db.git #

use edit mode to read clearly
