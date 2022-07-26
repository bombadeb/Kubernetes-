### Create EKS cluster using EKSCTL
``` bash
eksctl create cluster --name=eksdemo1 \
                      --region=us-east-1 \
                      --zones=us-east-1a,us-east-1b \
                      --without-nodegroup 
                  
```                  

### Get List of clusters
```
eksctl get
