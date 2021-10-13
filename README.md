# kb1

kubebuilder init --domain tutorial.kubebuilder.io

kubebuilder create api --group batch --version v1 --kind CronJob
 
kubebuilder create webhook --group batch --version v1 --kind CronJob --defaulting --programmatic-validation

Go mod tidy; go mod vendor

Make install

kubectl create -f config/samples/batch_v1_cronjob.yaml

kubectl get cronjob.batch.tutorial.kubebuilder.io -o yaml

make docker-build docker-push IMG=<some-registry>/<project-name>:tag

make deploy IMG=<some-registry>/<project-name>:tag

kubectl config set-context --current --namespace=buildcron-system

kubectl get all
