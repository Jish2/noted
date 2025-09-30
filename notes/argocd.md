---
updated: 2025-08-19T10:26
created: 2025-08-11T11:41
---
#infra/k8s 
gitops approach to ci/cd for kubernetes environments

- declarative, it respects a git repo as the source of truth
    - when the k8s environment is out of sync, it will self repair
- doesn't replace ci, just replaces cd
    - you still need to deploy your application code and push to a registry
    - has history & status



### without argocd
1. test
2. build image
3. push to registry
4. update k8s manifest
5. kubectl apply

### with argocd
1. test
2. build image
3. push to registry
4. update k8s manifest
5. argocd tracks k8s manifests, triggers deploy


[^1]: [ArgoCD Tutorial for Beginners \| GitOps CD for Kubernetes - YouTube](https://www.youtube.com/watch?v=MeU5_k9ssrs)