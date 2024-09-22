# Application explanation


1. **metadata**
   - `name: springboot-argocd-application` : name of the application in ArgoCD
   - `namespace: argocd` : this namespace is where ArgoCD running 
2. **spec**
   - `project: default` : name of ArgoCD project
3. **source**
   - `repoURL` : URL of manifest Git repository
   - `targetRevision: argocd` : refer to branch `argocd` that we are working on.
   - `path: manifests` : path of Kubernetes manifest (deploy, service...)
4. **destination**
   - `server` : K8s API server
   - `namespace: springboot-agrocd` : namespace where app will be deployed
5. **syncPolicy**
   - automated
     - `prune: true` : remove resources that define outside Git automatically. 
     - `selfHeal: true` : sync if the state in Git change 
   - syncOptions:
    - CreateNmespace=true
   - `revisionHistoryLimit: 5` : the amount of keeping history the deployed version


