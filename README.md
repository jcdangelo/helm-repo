# helm-repo

These are helm charts developed by Jeff D'Angelo.

* cloudacademy-webapp-0.1.0.tgz
    * A simple webserver to report a string for requesting / with `--set nginx.conf.message='String goes here'`
        * e.g. `helm install ca-demo2 cloudacademy-gh-repo-demo/cloudacademy-webapp --set nginx.conf.message='served from github pages'`
    * See personal notes palazzo:~/notes/otd/2025/0208.intro_to_helm
    * Based on [Cloud Academy](https://platform.qa.com/l)'s [Kubernetes Tools](https://platform.qa.com/learning-paths/kubernetes-tools-2065/) > [Performing a Kubernetes Deployment using ConfigMaps and Helm [lab]](https://platform.qa.com/lab/performing-kubernetes-deployment-using-configmaps-and-helm/)
* flux-tick-migration-tag-0.1.0.tgz
    * A simple webserver based on cloudacademy-webapp that can be used to verify current state of a flux config that is managing a given namespace; assist the migration of tick from flux v1 to flux v2.
