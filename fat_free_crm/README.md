# openshift-ffcrm

[Fat Free CRM](https://github.com/fatfreecrm/fat_free_crm) on OpenShift

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

Once the app is running, log-into the pod and run the setup task:

```bash
rake ffcrm:setup
```

or 

```bash
rake db:migrate && rake ffcrm:setup:admin USERNAME=admin PASSWORD=password EMAIL=admin@example.com
```

## Version

* Ruby 2.5
* Postgres 10
* Fat Free CRM 0.18.x