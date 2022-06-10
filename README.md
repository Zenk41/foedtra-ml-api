# Machine Learning API

- Flask
- Python
- PIP
- Cloud Run
- Dockerfile
- Cloud SDK

# Deploy
## Build Docker image Cloud shell
- Docker build -t gcr.io/$MY_PROJECT_ID/foedtra-ml:v1 -f Dockerfile .
- docker push gcr.io/$MY_PROJECT_ID/foedtra-ml:v1

## Deploy in Cloud Run

### Via Cloud Console
- Container image URL -> Select Docker Image 
- Container port = 8080
- Memory = 4 GiB
- CPU = 2
- Execution environment = Second generation
- Auto Scalling = 
  - Minimum instances = 1
  - Maximum instances = 5

### Via Cloud Shell or Terminal/CMD VsCode with Cloud SDK

- Open Cloud Shell/Terminal
- gcloud init -> Select account and Project
```
gcloud run deploy foedtra-ml \
 --image gcr.io/$MY_PROJECT_ID/foedtra-ml:v1 \
 --region asia-southeast2 \
 --platform managed \
 --port 8080 \
 --memory 4GiB \
 --cpu 2 \
 --max-instances 5 \
 --min-instances 1 \
 --execution-environment gen2 \
 ```
 
 
