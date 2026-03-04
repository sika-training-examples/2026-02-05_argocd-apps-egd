> [!TIP]
> <a href="https://ondrej-sika.cz/skoleni/argocd"><img src="https://img.shields.io/badge/Školení%20ArgoCD-by%20Ondřej%20Šika-orange?style=for-the-badge&logo=argo&logoColor=white" style="width: 100%; height: auto;" alt="Školení ArgoCD by Ondřej Šika" /></a>
>
> 🚀 Naučte se, jak efektivně spravovat deploymenty pomocí **ArgoCD**! Praktické školení vedené [Ondřejem Šikou](https://ondrej-sika.cz).
>
> 👉 [Více informací a registrace zde](https://ondrej-sika.cz/skoleni/argocd)

# argocd-apps-egd

## Install ArgoCD & Setup App-of-Apps for EGD Cluster

```
oc apply -f clusters/egd/_system/argocd/manifests/01_ns.yaml
oc apply -f clusters/egd/_system/argocd/manifests/02_operatorgroup.yaml
oc apply -f clusters/egd/_system/argocd/manifests/03_subscription.yaml
oc apply -f clusters/egd/_system/argocd/manifests/04_rbac.yaml
sleep 60
oc apply -f clusters/egd/_system/argocd/manifests/05_argocd_config.yaml
sleep 60
oc apply -f clusters/egd/app_of_apps.acdproj.yaml
oc apply -f clusters/egd/app_of_apps.acdapp.yaml
```

## Install ArgoCD & Setup App-of-Apps for Training Cluster

```
oc apply -f clusters/training/_system/argocd/manifests/01_ns.yaml
oc apply -f clusters/training/_system/argocd/manifests/02_operatorgroup.yaml
oc apply -f clusters/training/_system/argocd/manifests/03_subscription.yaml
oc apply -f clusters/training/_system/argocd/manifests/04_rbac.yaml
sleep 60
oc apply -f clusters/training/_system/argocd/manifests/05_argocd_config.yaml
sleep 60
oc apply -f clusters/training/app_of_apps.acdproj.yaml
oc apply -f clusters/training/app_of_apps.acdapp.yaml
```
