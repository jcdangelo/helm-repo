# helm-repo

These are helm charts developed by Jeff D'Angelo.

Served to helm via [index.yaml](index.yaml).

## Helm cheat

* `cd ~/working-dir`
* `helm create project-foo`
* `tree project-foo`
* `vi project-foo/*` ...
* `helm template project-foo | less`
* `helm lint project-foo`
* `helm package project-foo`
* `cd ~/this-helm-repo-checkout`
* `git branch -v ; git status ; git pull` ... clean up; use branch gh-pages
* `cp ~/working-dir/project-foo-0.1.0.tgz ~/this-helm-repo-checkout`
* `git add project-foo-0.1.0.tgz ; git commit project-foo-0.1.0.tgz -m 'a note here'`
* `helm repo index . ; git commit index.yaml -m 'a note here'``
* `vi README.md ; git commit README.md -m 'a note here'` (optional)
* `git push`
* `ktx your-target-kubernetes-context`
* `kns your-target-kubernetes-namespace`
* `helm repo add jcdangelo https://jcdangelo.github.io/helm-repo/` # if you didn't do this yet; do once
* `helm repo update`
* `helm install deploy-name jcdangelo/project-foo --set nginx.conf.message='current tag'`

etc.

## Charts

* cloudacademy-webapp-0.1.0.tgz
    * A simple webserver to report a string for requesting / with `--set nginx.conf.message='String goes here'`
        * e.g. `helm install ca-demo2 cloudacademy-gh-repo-demo/cloudacademy-webapp --set nginx.conf.message='served from github pages'`
    * See personal notes palazzo:~/notes/otd/2025/0208.intro_to_helm
    * Based on [Cloud Academy](https://platform.qa.com/l)'s [Kubernetes Tools](https://platform.qa.com/learning-paths/kubernetes-tools-2065/) > [Performing a Kubernetes Deployment using ConfigMaps and Helm [lab]](https://platform.qa.com/lab/performing-kubernetes-deployment-using-configmaps-and-helm/)
* flux-tick-migration-tag-0.1.0.tgz
    * A simple webserver based on cloudacademy-webapp that can be used to verify current state of a flux config that is managing a given namespace; assist the migration of tick from flux v1 to flux v2.
    * Configs tracked via https://github.com/jcdangelo/flux-tick-migration-tag
