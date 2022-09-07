## Some Glitches
#### On values.yaml at ingress-nginx chart admissionWebhooks: failurePolicy set to Ignore
#### ArgoCD runs only with https. You need to change it at argocd.yaml on argocd Deployment containers:- command: - argocd-server - --insecure
#### To test argo-events webhook use: curl -X POST -H "Content-Type: application/json" -d '{"message": "Hello Webook!"}' http://eventsource.cluster.local/testing-webhook (Modify it in respect of post request url and endpoint name)

## General info
#### Before you start you need to have a kubernetes cluster that has some deployments already created. It needs cert-manager + clusterissuer (lets encrypt) for any cluster on the cloud and for everyone using baremetal it needs metallb and local-path-provisioner.
#### First you install argocd and then you can proceed with the apps.

#### You need to create docker config json. Use:
#### kubectl -n argo create secret docker-registry regcred --docker-server=$REGISTRY_SERVER --docker-username=$REGISTRY_USER --docker-password=$REGISTRY_PASSSOWRD --docker-email=$REGISTRY_EMAIL
