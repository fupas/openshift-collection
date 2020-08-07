# snibox/snibox

Snibox is a self-hosted snippet manager. Developed to collect and organize code snippets. Supports various programming languages, markdown, plain text.

## Repository

[https://github.com/snibox/snibox](https://github.com/snibox/snibox)

## Quick Setup

Create a copy of `secrets.yaml.example` and rename it to `secrets.yaml`. Make the necessary changes.

Deploy the app:

```bash
oc new-project <your_project>

oc create -f secrets.yaml -n <your_project>
oc create -f pv.yaml -n <your_project>
oc create -f build-app.yaml -n <your_project>
oc create -f deploy-postgresql.yaml -n <your_project>
oc create -f deploy-app.yaml -n <your_project>
```

## Versions

* Ruby 2.6
* RAILS 5.2.x
* Postgres 10