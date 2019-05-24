# Test step for gosoft lunch and learn

## build docker

* gcloud builds submit --tag="gcr.io/store-controller/lunch-and-learn:$(git rev-parse --short=7 HEAD)" .
* gcloud builds submit --config .\cloudbuild.yaml .
* gcloud builds submit --config=cloudbuild.yaml . --substitutions=TAG_NAME="100.100.100.1"

<!--
gcloud container clusters create [CLUSTER_NAME]
gcloud container clusters get-credentials [CLUSTER_NAME]
-->
## Apply kubernetes.

* gcloud init
* gcloud container clusters create lunch-and-learn-1
* gcloud container clusters get-credentials lunch-and-learn-1

* gcloud container clusters create auto-scale-test	
* gcloud container clusters get-credentials auto-scale-test	
---

## kubectl manual

* kubectl get pod --all-namespaces -o wide
* kubectl describe pod [POD_NAME] --namespace=kube-system

* kubectl apply -f .
* kubectl delete -f .

link --> <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

## cleanup cluster
* gcloud container clusters delete [CLUSTER_NAME]
