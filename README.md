# efk-with-xpack

Generate Password for the Elasticsearch users

kubectl exec -it $(kubectl get pods -n logging | grep elasticsearch-client | sed -n 1p | awk '{print $1}') -n logging -- bin/elasticsearch-setup-passwords interactive

Run the following command to create a secret in Kubernetes

kubectl create secret generic elasticsearch-pw-elastic -n logging --from-literal password=admin@123
