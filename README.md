# 12-kubernetes-01-intro.md

root@sergey-VirtualBox:~# kubectl get services
NAME         TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
hello-node   LoadBalancer   10.109.152.232   <pending>     8080:30426/TCP   8m57s
kubernetes   ClusterIP      10.96.0.1        <none>        443/TCP          19m
root@sergey-VirtualBox:~#  minikube addons list
|-----------------------------|----------|--------------|-----------------------|
|         ADDON NAME          | PROFILE  |    STATUS    |      MAINTAINER       |
|-----------------------------|----------|--------------|-----------------------|
| ambassador                  | minikube | disabled     | unknown (third-party) |
| auto-pause                  | minikube | disabled     | google                |
| csi-hostpath-driver         | minikube | disabled     | kubernetes            |
| dashboard                   | minikube | enabled ✅   | kubernetes            |
| default-storageclass        | minikube | enabled ✅   | kubernetes            |
| efk                         | minikube | disabled     | unknown (third-party) |
| freshpod                    | minikube | disabled     | google                |
| gcp-auth                    | minikube | disabled     | google                |
| gvisor                      | minikube | disabled     | google                |
| helm-tiller                 | minikube | disabled     | unknown (third-party) |
| ingress                     | minikube | enabled ✅   | unknown (third-party) |
| ingress-dns                 | minikube | disabled     | unknown (third-party) |
| istio                       | minikube | disabled     | unknown (third-party) |
| istio-provisioner           | minikube | disabled     | unknown (third-party) |
| kubevirt                    | minikube | disabled     | unknown (third-party) |
| logviewer                   | minikube | disabled     | google                |
| metallb                     | minikube | disabled     | unknown (third-party) |
| metrics-server              | minikube | disabled     | kubernetes            |
| nvidia-driver-installer     | minikube | disabled     | google                |
| nvidia-gpu-device-plugin    | minikube | disabled     | unknown (third-party) |
| olm                         | minikube | disabled     | unknown (third-party) |
| pod-security-policy         | minikube | disabled     | unknown (third-party) |
| portainer                   | minikube | disabled     | portainer.io          |
| registry                    | minikube | disabled     | google                |
| registry-aliases            | minikube | disabled     | unknown (third-party) |
| registry-creds              | minikube | disabled     | unknown (third-party) |
| storage-provisioner         | minikube | enabled ✅   | kubernetes            |
| storage-provisioner-gluster | minikube | disabled     | unknown (third-party) |
| volumesnapshots             | minikube | disabled     | kubernetes            |
|-----------------------------|----------|--------------|-----------------------|


  
netology>curl -X GET https://192.168.1.69:8443/api --header "Authorization: Bearer eyJhbGciOiJSUzI1NiIsImtpZCI6Ik13Mk9rY2JyTWlRZkJOZWJrVzc0Y3FJcHVoMEc1RDhmTFlrX01adnc5RU0ifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJkZWZhdWx0Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6ImRlZmF1bHQtdG9rZW4tNW00NzUiLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoiZGVmYXVsdCIsImt1YmVybmV0ZXMuaW8vc2VydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6IjM4YTNhNTdlLTVjNWMtNGU4Yy1hZmFmLTE1ZjIzMDg3YjUxMSIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDpkZWZhdWx0OmRlZmF1bHQifQ.vGav9pfZMDWgMxJefjbDzf4qPlRB3E-xKLiocjNlQHO4yFa-mZOMHSqqPeBULJfI-y5YPMWis1pwEjdnco7NldTZ-rztLXHzSSMe3sCV3j3yKVRx3Ck7Zf-tIw5c4sT32ZPnuRX_CaZ3J0Acq-cs9_wd0CNmj9I4svFHGvxl0us_U5Q2aM4gBmMIHD77ucIYKnOZuR4O6-MMMLHOgP5rocCAk1zAkUK8iabveKSV-vTl3S6qsUr-7HYv_chVNIVn-dS_ly6UC38fOnei7gDofCn-9r4zgVC9xfThgSFG4vCuMhNOTnyUz9aTS527kaeFc2IV-_GvdhXZ_KE3CVpc8A" --insecure
{
  "kind": "APIVersions",
  "versions": [
    "v1"
  ],
  "serverAddressByClientCIDRs": [
    {
      "clientCIDR": "0.0.0.0/0",
      "serverAddress": "192.168.1.69:8443"
    }
  ]
}
netology>kubectl get po
Unable to connect to the server: x509: cannot validate certificate for 192.168.1.69 because it doesn't contain any IP SANs

  
  по пункту 4, смог настроить доступ к кластеру через curl, но не через kubectl. что-то там не там с авторизацией, но эта тема в уроке совсем не освещалась
