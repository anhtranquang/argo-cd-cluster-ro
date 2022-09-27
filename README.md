# EKS ARGOCD Bootstrap and Configuration Repository

## Step by step installation
Require following cli tools installed: helm, kubectl ( kubectx and kubens ).

1. Create local kubernetes cluster using kind. Follow this instruction https://kind.sigs.k8s.io/docs/user/quick-start/
2. Create namespace for ArgoCD : kubectl create ns argocd && kubens argocd
3. Install the ArgoCD via helm: helm dep update _argocd/templates/argocd && helm install argocd _argocd/templates/argocd
4. After the installation finish, we can access the ArgoCD UI via browser http://localhost:8080 after doing port-forward: kubectl port-forward svc/argocd-server 8080:80
5. Login to the ArgoCD using user *admin* and password printed from secret: kubectl get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

Good luck and have fun!

© CCT Technology 2022
