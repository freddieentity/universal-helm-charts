# Publish helm charts
cd packages
helm package ../charts/microservices-standard

#Update index.yml searching all first level subfolders for possible packaged charts
cd ..   
helm repo index . --url https://<github_username>.github.io/<repo_name>

helm repo add my-repo https://<github_username>.github.io/<repo_name>

helm repo update

helm search repo microservices-standard