# openshift-snibox

[Self-hosted snippet manager](https://github.com/snibox/snibox) on OpenShift

## Quick Setup

Create a copy of `secrets.yaml.example` and rename it to `secrets.yaml`. Make the necessary changes.

Deploy the app:

```bash
oc new-project <your_project>
oc create -f openshift/secrets.yaml -n <your_project>
oc create -f openshift/pv.yaml -n <your_project>
oc create -f openshift/build-app.yaml -n <your_project>
oc create -f openshift/deploy-postgresql.yaml -n <your_project>
oc create -f openshift/deploy-app.yaml -n <your_project>
```
