# Fat Free CRM

An open source, Ruby on Rails customer relationship management platform (CRM).

## Repository

[https://github.com/fatfreecrm/fat_free_crm](https://github.com/fatfreecrm/fat_free_crm)

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
bundle exec rake ffcrm:setup
```

or 

```bash
bundle exec rake db:migrate
bundle exec rake ffcrm:setup:admin USERNAME=admin PASSWORD=password EMAIL=admin@example.com
```

### Versions

* Ruby 2.6
* RAILS 5.2.x
* Postgres 10
* Fat Free CRM 0.18.1