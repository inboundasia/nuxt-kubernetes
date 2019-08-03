# Deploy Flow

`docker build . -t asia.gcr.io/inboundmarketing/nuxt-demo`

`docker push asia.gcr.io/inboundmarketing/nuxt-demo`

`kubectl apply -f kubernetes/deployment.yaml`

`gcloud compute addresses create nuxt-demo-ip --global`

`gcloud compute addresses describe nuxt-demo-ip --global`

`kubectl apply -f kubernetes/ingress.yaml`

# Clean up

kubectl delete ingress,service -l app=nuxt-demo

gcloud compute addresses delete nuxt-demo-ip --global

kubectl delete -f kubernetes/deployment.yaml
