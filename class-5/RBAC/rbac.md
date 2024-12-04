
1. execute this configuration

```bash
k apply -f admin-sa.yml
k apply -f general-sa.yml
k apply -f others-sa.yml

```

```bash
k get sa
kubectl get clusterroles

```


2. Generate Token for ServiceAccounts: 

# For admin service account:

```bash
kubectl -n default create token admin
kubectl -n default create token general
kubectl -n default create token others

```
3. Create Kubeconfig Files:
 
Use the tokens generated in the previous step to create kubeconfig files for each serviceAccount.

Example: `admin-kubeconfig.yaml`
save this content to `admin-kubeconfig.yaml`
 
# now, we need to create service account for three user, like `admin, ogeneral, others`

```bash
sudo apt update
sudo snap install kubectl --classic
```
# 4. Use the kubeconfig files
```bash
export KUBECONFIG=~/admin-kubeconfig.yaml
kubectl config get-contexts
kubectl get nodes
```

eyJhbGciOiJSUzI1NiIsImtpZCI6InNRVmFfMGxnX3FmZ1puNkVlcVZ1UUtTSU9oZER6TTNma2hSX0Z2VThXSjgifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzI0OTY3NTU1LCJpYXQiOjE3MjQ5NjM5NTUsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0Iiwic2VydmljZWFjY291bnQiOnsibmFtZSI6ImFkbWluIiwidWlkIjoiYmJjMzM5MzMtNWFhYS00NTZmLWE0MzYtZGI4Mjc3ZjFkYmQwIn19LCJuYmYiOjE3MjQ5NjM5NTUsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDpkZWZhdWx0OmFkbWluIn0.oR6HGB9cg6KT1ys-3fd7WzsXXbuN_mot_IyOWVkbF91NiOL6XaxTzBwnWKdaE8bqRZEwepX9D1qZa49nYTiA7Zp5002uCkUk-X_bqfBJd8TzEVR7X3LWDqTUEOAv-DROH0aTVDrW5iAbzrOEXxpifn0JFWq9Ee9eXH5QIaSPv91HslO6E6aekBSBflb0H8akdV1KDLfvHhNFarlUpoJFajacpe9C2SMvDfPXoikKnIhUwVjABE9blyxzRzDz6SUSZtp6z469MqTbqxmYpLnUiTTYDFTqWnA1LpQQPbzr8zIbK97FzJ0OXmVBu7wZQC2zez39FHxGkrZkZQugOEVOXA


eyJhbGciOiJSUzI1NiIsImtpZCI6InNRVmFfMGxnX3FmZ1puNkVlcVZ1UUtTSU9oZER6TTNma2hSX0Z2VThXSjgifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzI0OTY3NTY2LCJpYXQiOjE3MjQ5NjM5NjYsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0Iiwic2VydmljZWFjY291bnQiOnsibmFtZSI6ImdlbmVyYWwiLCJ1aWQiOiI3YjliNmNhMC1jN2FkLTQ0MTQtOGVlZC01NDMzYzU5YWFiZGUifX0sIm5iZiI6MTcyNDk2Mzk2Niwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50OmRlZmF1bHQ6Z2VuZXJhbCJ9.XfZ79HE1goRHOX5CGwcH7j4ydNEbGDElyIqDbR9mhh8LjRewP6sb_Q5uTgGYvwQ-nZVmeC5sbA-oT2nqYXIfH7v3mK4kX8SJRtwombfP3Vv9tQ3BYji6BFjiFEERnKLUj5i76pDJ9h9R1McVsQDDjE5s3awKeZY8uNXKxZ5o6cdw9LhfMMjrBo2lFfZSldsdlrtLhlmy1Ol2zrd0gGtlK0-laoIM9xhuv9RG4NMpzS_uizGDPWl3lXcarXwiKXEOaql9uxckDUyNkzvQOooQA1WI7I1sgqo8xyYS_496iKJqSZQ_l65PztF1sK_orgtnckA-9GayaC_0UVsvMKQiqg


eyJhbGciOiJSUzI1NiIsImtpZCI6InNRVmFfMGxnX3FmZ1puNkVlcVZ1UUtTSU9oZER6TTNma2hSX0Z2VThXSjgifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzI0OTY3NTcyLCJpYXQiOjE3MjQ5NjM5NzIsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0Iiwic2VydmljZWFjY291bnQiOnsibmFtZSI6Im90aGVycyIsInVpZCI6IjE4ZjU2MDliLTY3NmQtNDA1ZC1iZTAwLTk3NjJjZWM2NjI2ZCJ9fSwibmJmIjoxNzI0OTYzOTcyLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6ZGVmYXVsdDpvdGhlcnMifQ.kTzeGQsenyOZ4ddPeKqDFxfWjflRJJneRbv448at537ZZluOI4jHiNpNHxRyr6mwswNmOuC7aVG2JNZBjqqvJHrEALL217zvhi7lo0h8RO6oK6mhljT46ToECzoo3TTsB4zuJzzPEY7HLZt4BX_KvxyhTLk76zADFqWU2XL1Psqsu4b1B7sj4rkTg1qpU12qqDSWJd84IJoMku9y3FF7CuzigKe-IRKe7uEovlltPOjqAnlTJ-d543PKk3YXwgCHzq4l1k6dQxacEdru6tmI_I_Sv1iAwGJg3ZdU7OL_4ShDbg96SYr6vfXWsLNw3xM7VFFfLC6YbZ1AgixaHN6CZQ


```bash
k get role
k describe role <role-name>
```


# master node commands histoy
```bash
   13  cd .kube/
   14  ls
   15  cat config
   16  cd ..
   17  ls
   18  vim admin.yaml
   19  ls
   20  cat admin.yaml
   21  kubectl apply -f admin.yaml
   22  vim admin.yaml
   23  kubectl apply -f admin.yaml
   24  cat admin.yaml
   25
   31  vim general.yaml
   32  kubectl apply -f general.yaml
   33  cat general.yaml
   37  vi others.yaml
   38  kubectl apply -f others.yaml
   39  cat others.yaml
   40  kubectl create namespace ns1
   41  kubectl create namespace ns2
   42  kubectl create namespace ns3
   44  vim deployment.yaml
   45  kubectl apply -f deployment.yaml -n ns2
   46  kubectl get pods
   47  kubectl get pods -n ns2
   48  kubectl get deploy -n ns2
   49  kubectl get svc -n ns2
   50  kubectl get deploy -n ns2
   51  kubectl get svc -n ns2
   54  kubectl -n default create token admin
   55  kubectl -n default create token general
   56  kubectl -n default create token others
   57  cd .kube/
   58  cat config

```
# admin-user
```bash

       sudo apt update
       sudo snap install kubectl --classic
       vim admin-kubeconfig.yaml
   32  kubectl apply -f admin-kubeconfig.yaml
   33  cat admin-kubeconfig.yaml
   34  export KUBECONFIG=~/admin-kubeconfig.yaml
   35  kubectl config get-contexts
   36  kubectl get nodes
   37  cat admin-kubeconfig.yaml
   38  kubectl get nodes
   39  kubectl get all -n ns2
   40  kubectl get deploy -n ns2
   kubectl delete pod <pod-name> -n ns2
   
```

# general user 
```bash
    1  sudo apt update
    2  sudo snap install kubectl --classic
    3  vi general-kubeconfig.yaml
    4  export KUBECONFIG=~/general-kubeconfig.yaml
    5  kubectl config get-contexts
    6  kubectl get nodes
    7  kubectl get ns
    8  kubectl get all -n ns2
    9  kubectl delete pod full-stack-app-deployment-59954787bf-qpfg9
   10  kubectl delete pod full-stack-app-deployment-59954787bf-qpfg9 -n ns2
```
# others users
```bash
    1  sudo apt update
    2  sudo snap install kubectl --classic
    3  vim others-kubeconfig.yaml
    4  export KUBECONFIG=~/others-kubeconfig.yaml
    5  kubectl config get-contexts
    6  kubectl get nodes
    7  kubectl get ns
    8  kubectl get pods -n ns2
```



# Step by step process


```bash
#step-1

#step-2
ubuntu@ip-172-31-16-69:~$ k get sa
NAME      SECRETS   AGE
admin     0         5s
default   0         78m
general   0         5s
others    0         5s
ubuntu@ip-172-31-16-69:~$ ^C
ubuntu@ip-172-31-16-69:~$ kubectl get clusterroles
NAME                                                                   CREATED AT
admin                                                                  2024-12-04T15:54:55Z
admin-role                                                             2024-12-04T17:13:00Z
calico-cni-plugin                                                      2024-12-04T15:55:11Z
calico-kube-controllers                                                2024-12-04T15:55:10Z
calico-node                                                            2024-12-04T15:55:10Z
cluster-admin                                                          2024-12-04T15:54:55Z
edit                                                                   2024-12-04T15:54:55Z
general-role                                                           2024-12-04T17:13:00Z
kubeadm:get-nodes                                                      2024-12-04T15:54:56Z
others-role                                                            2024-12-04T17:13:00Z

#step-3
ubuntu@ip-172-31-16-69:~$ k create namespace ns1
namespace/ns1 created
ubuntu@ip-172-31-16-69:~$ k create namespace ns2
namespace/ns2 created
ubuntu@ip-172-31-16-69:~$ k create namespace ns3
namespace/ns3 created
ubuntu@ip-172-31-16-69:~$ k get ns
NAME              STATUS   AGE
default           Active   89m
kube-node-lease   Active   89m
kube-public       Active   89m
kube-system       Active   89m
ns1               Active   11s
ns2               Active   6s
ns3               Active   4s
ubuntu@ip-172-31-16-69:~$

#step-4
ubuntu@ip-172-31-16-69:~$ vi deployment.yml
ubuntu@ip-172-31-16-69:~$ k apply -f deployment.yml -n ns2
deployment.apps/full-stack-app-deployment created
service/full-stack-app-svc created
ubuntu@ip-172-31-16-69:~$ k get po
No resources found in default namespace.
ubuntu@ip-172-31-16-69:~$ k get po -n ns2
NAME                                         READY   STATUS    RESTARTS   AGE
full-stack-app-deployment-79fd6bdd95-p7zgb   1/1     Running   0          11s
ubuntu@ip-172-31-16-69:~$ k get svc -n ns2
NAME                 TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)          AGE
full-stack-app-svc   NodePort   10.104.35.168   <none>        4000:32041/TCP   26s
ubuntu@ip-172-31-16-69:~$ k get deploy -n ns2
NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
full-stack-app-deployment   1/1     1            1           36s
ubuntu@ip-172-31-16-69:~$

#step-5

ubuntu@ip-172-31-16-69:~$ k -n default create token admin
eyJhbGciOiJSUzI1NiIsImtpZCI6Il9XdWlmWjQzSjNWNHEyb2t6UTJWVmdBeWN0cjRXSTYwcXFNN0k2ZDVYZW8ifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzMzMzM2NTE2LCJpYXQiOjE3MzMzMzI5MTYsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwianRpIjoiODI4N2YyNWUtMjQ1Mi00YzAzLThiNWYtODdjOWZmZDc4NjVlIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0Iiwic2VydmljZWFjY291bnQiOnsibmFtZSI6ImFkbWluIiwidWlkIjoiNmM4M2VhNDctZWU3OC00YTNmLWJmZWItNDhjOTAyN2M1YmVhIn19LCJuYmYiOjE3MzMzMzI5MTYsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudDpkZWZhdWx0OmFkbWluIn0.t_Wz5E_aPvPhOLvTdEU8cb49Njj5wAIP2jEBw93YTrQfPQnigvG7uOaq9tzKYIlrY5aZ5iOt6ob1y9xJspPz71-LU57RTZXGHm3qvAk_epqhGlLYxIzb3qHqYSP98fzpDDLRYrLnMOkVq1qbyXcOn_o6zSz097yrrApveEr82t3kLQQEQVksW-XWrj8cpbnntxGs_BV-Jnku6gRkWxgG4nEwCdv3ycuDK5RUQGLIIstlM_b5kyomA0IfX50Mz_ghp69Bw42scZzzDcu0-xYRUCPtCkC16ehzBTiGI-5RGrUbNqY81Iysy1NWMAt35KxLozGNXYIbZOPeCywvCvovDQ
ubuntu@ip-172-31-16-69:~$ k -n default create token general
eyJhbGciOiJSUzI1NiIsImtpZCI6Il9XdWlmWjQzSjNWNHEyb2t6UTJWVmdBeWN0cjRXSTYwcXFNN0k2ZDVYZW8ifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzMzMzM2NTM2LCJpYXQiOjE3MzMzMzI5MzYsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwianRpIjoiZjRiYTJlZjgtOTQ5ZS00OWJjLWEzM2EtYmJlMzQ1YmEzZTQwIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0Iiwic2VydmljZWFjY291bnQiOnsibmFtZSI6ImdlbmVyYWwiLCJ1aWQiOiIxNjE3MzNhMy05ZTI0LTRmOGYtYjNmMy02MWJiODcwOTU1ZjgifX0sIm5iZiI6MTczMzMzMjkzNiwic3ViIjoic3lzdGVtOnNlcnZpY2VhY2NvdW50OmRlZmF1bHQ6Z2VuZXJhbCJ9.baSqUVQhkhFlPbKnI-LpOtqzehF7I5xmPau6H0AKiDI2g_rtvRv2LuJpAGtl0gbckYjsssBHxh3Idpe9k2kUMiHrRTc1MXcMVL4hpq0Hj2qw2q5QnHzusB4UwAynl9XabIF5gVjKuIx2t7_DIztYz1_jYlw3p882pgQ7qwuo93ID8QkA758tRsfRmyj-fsBfdeikoJ_WUSddvIkwIXLA6eqcx_bkeZNLX-FS_zf9ymMIPkxzvNH7oq_v29OYsQXMha6IIG9WoBxZS2oPu0DDTOh8NLYOTDEC9yKlk2UGnQ3slmcs2u4I6VbzTR8ucB7HGhBV0mDdnwcAKzq05CJ91g
ubuntu@ip-172-31-16-69:~$ k -n default create token others
eyJhbGciOiJSUzI1NiIsImtpZCI6Il9XdWlmWjQzSjNWNHEyb2t6UTJWVmdBeWN0cjRXSTYwcXFNN0k2ZDVYZW8ifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNzMzMzM2NTQzLCJpYXQiOjE3MzMzMzI5NDMsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwianRpIjoiM2FkYTViODgtYjBhZi00ZGYxLTlmYmQtMDkwMzc0OWVmZjZlIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0Iiwic2VydmljZWFjY291bnQiOnsibmFtZSI6Im90aGVycyIsInVpZCI6ImM4Y2I3ODRkLTJmNmYtNDEwOC04ZTA4LTZlOTRkZWFkMzUwMyJ9fSwibmJmIjoxNzMzMzMyOTQzLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6ZGVmYXVsdDpvdGhlcnMifQ.dyiCyZRTG100-JPntHwSTUI7rFLIxO_GvZ5x8TRIWCGk2EIwiYFJFeaJjmOrZp3BzjmtEVKFLhuXllwHvRgdQ6h37C00kqbbnpjdVJZ6Y-zuSLFatirLdbtgcZMKsEVKjPWF35dlAmAmWJ4HW0j56o9laYMjpNB3nMtUldWeGAtSChGG326ClwwfKEzPtqG7O0Uunza2s4M0I-YOIUQtBSW-gt9hc3q7fU2tCouUQdpFPUTaqgIceOmUti4pSFedbuirabaSPQ8gnQNDcnk7ZyWmTHYuBxle7478I3JnLUAk2srmKknucqGsvMXBtsA8xBpaWSYICyFqsvmkw9vx6w
ubuntu@ip-172-31-16-69:~$ ^C

#step-6
# get config file template

ubuntu@ip-172-31-16-69:~$ ls
ubuntu@ip-172-31-16-69:~$ cd .kube/
ubuntu@ip-172-31-16-69:~/.kube$ ls
cache  config
ubuntu@ip-172-31-16-69:~/.kube$ cat config
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURCVENDQWUyZ0F3SUJBZ0lJRFVPTG9PdFd5aGd3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TkRFeU1EUXhOVFE1TkRkYUZ3MHpOREV5TURJeE5UVTBORGRhTUJVeApFekFSQmdOVkJBTVRDbXQxWW1WeWJtVjBaWE13Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBQTRJQkR3QXdnZ0VLCkFvSUJBUURGSVd1VDEyblVnaTJaTm9hYStXU1pCTmNSOW01QVFvaVoxcUx1aWZ4ODhEUDIzMHZ1c0xtZW1Cd0gKTUIybTltOVBWVDZyaEtCOXVkRUxOSWlaU1ZYYUJNY3Bzc3lLNzNXVkZSRFE1cE51dU5teVdNM3N3TytLaW5odgo5TW9nRjVGaTkwWEpDUzJPYnFMYXphL0JmdHI3eXViQVRDNHNMRHMwK3AwVUJtZitpcXA2LzVzTlBsakJOYVVyCnB5dnJ3RWl2anBReXhSSTlLRjhlaWwxaVFNbkVNc0JkSGFsQ0lRUVdZeVozZWVSZjdKU1E3bHBzaU1RZSt5ejAKMTFQUXRxeHhaZS9hMUZxNGVKbnVLNGlSNnE5ZFZhSzJxVGFkdXJSZENVUWRXNFJvS3VvL1VEVVRDTjVzNU9ERwpYVm5tb0VydFJZSzU2K0VTQ3VUSUNYelBpUWJkQWdNQkFBR2pXVEJYTUE0R0ExVWREd0VCL3dRRUF3SUNwREFQCkJnTlZIUk1CQWY4RUJUQURBUUgvTUIwR0ExVWREZ1FXQkJRVmVTZlpkREkvMFlobGpUL1g2RzgzbmJ3MlNqQVYKQmdOVkhSRUVEakFNZ2dwcmRXSmxjbTVsZEdWek1BMEdDU3FHU0liM0RRRUJDd1VBQTRJQkFRQitSWlY3QmRyYQowckpGZlJieGdBN1VKSHM2ZlBBaHgxc2RqNnZGVU9jc1U5UGZtOUlmdGgxekFaeFV3blJEaCtLbnROL3hwcUhqCjJVRDBENmpib1dISlhXYTJ1KzlEMHhoQk5LOVZaVnAwM1UxTTVsY2pzNGNRcHFxaWpIMVV4Nm5YVi9aQW9haXkKNTFaN3ByaG1xVVZRMHhWa3pkSG02MXhoMFFGRTUrUWwzNS9yVWFZd0xPSzhxbUQ5MWJtMTNuVmkwTWRUK2QxVwpybmFHTTNwYzZjb2hQeWZuWlEwRFJFbnN5M3BNMWxPTStFUUowTGxOaHpSdkFESGpPNWJKNTBmVStCNVhpNzc5ClZ6bzQ4ME9UUkJaaVQxUjR5ZzJzR1NYZE8zNVRVSkN6SHl2eVhaMU8yOXZXazg2bDlLeGV3MjRGTTJzWTN3dkUKSlhEZDgrMklzdlVQCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K
    server: https://172.31.16.69:6443
  name: kubernetes
contexts:
- context:
    cluster: kubernetes
    user: kubernetes-admin
  name: kubernetes-admin@kubernetes
current-context: kubernetes-admin@kubernetes
kind: Config
preferences: {}
users:
- name: kubernetes-admin
  user:
    client-certificate-data: LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURLVENDQWhHZ0F3SUJBZ0lJRDNKWENkbW52eEF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TkRFeU1EUXhOVFE1TkRkYUZ3MHlOVEV5TURReE5UVTBORGRhTUR3eApIekFkQmdOVkJBb1RGbXQxWW1WaFpHMDZZMngxYzNSbGNpMWhaRzFwYm5NeEdUQVhCZ05WQkFNVEVHdDFZbVZ5CmJtVjBaWE10WVdSdGFXNHdnZ0VpTUEwR0NTcUdTSWIzRFFFQkFRVUFBNElCRHdBd2dnRUtBb0lCQVFDei9aN2UKVjF2VzBNYU8zVC9UQU8vN3RxUnRsZ1dJa0tRa1lzaVZMaVJpZldOT3hJUkFBNmpmZXhsME1Kak93REtteFNvTwpzMDVxd0YrMENVZjFNem5FczBJV0tBeWQrSEpYdDFlZzhuYittR2Z6cUd4NEFvdFhBcUNEZDV6VUMraGM1ZVZUCnRzTGFVS0FnRElITzF4Vk0wRHV2WE5hTHJ2dkduN0pManEyckthWXUvbmRzL3hyZmV3RjBSNWZqUlhCT1cwWWgKUGd6UVNtRS9BMUR1WkMvK0VOV09IZ0M5SVJSNEMzaENHd3hYZ2NHQ0NkWWozQXd5OGk4RVBXTHRMNmxhc3h4TwphNTcxKzYyWlFJV2w2QXN0cy9HUmpRelJsU0hJRE1iWE5yZUx3bG4rRi9YM2VnbHEreEk4KzY5U01sZGM3V3o3CmpXam9FeUlLSUQ4VXZTMzNBZ01CQUFHalZqQlVNQTRHQTFVZER3RUIvd1FFQXdJRm9EQVRCZ05WSFNVRUREQUsKQmdnckJnRUZCUWNEQWpBTUJnTlZIUk1CQWY4RUFqQUFNQjhHQTFVZEl3UVlNQmFBRkJWNUo5bDBNai9SaUdXTgpQOWZvYnplZHZEWktNQTBHQ1NxR1NJYjNEUUVCQ3dVQUE0SUJBUUNqNDArV3BoNmNoMmx3cnBLOWM3QXdBM2hwCjg1U0FWQVdDWTlENysxaTlLVkV5UHMxZGZ1bjkyclRsTTZxdmtQZWF4Z2JpdDcvOVFxNU9sd1JzQXRRM1FobGgKNWs2ZUhSaEU0aHpEeGkrK2JEeC8xeFExV0JlMUhBRXB0cW13VzN0V2FVbGduekJsZWJvT2hHcE5aVHFZS21uaAo5VEhaSEl3Sk5KVTNlYXEwK2VqKzN1NXoyemR3Q2g2c29NalZ4Y1hCYi9LRmVzVThVb1YrNW8yL01hMnI4OThKCnhxelVBNkJZQnhiNGhSZFdERWJIeTMrUUNCV0E1RUhqVWMwaFhlWGNydU0yeHhINTcxOWZDdTRWdmgzbFZiY3IKK1FFb2E5a1RGbXVSTEU1a1dQNENXeVhNL0JvdGxuRW9WUlBXUEp1Tk9nZ0ZQZjNBWDBNSkh0czJkbUduCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K
    client-key-data: LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVktLS0tLQpNSUlFcEFJQkFBS0NBUUVBcy8yZTNsZGIxdERHanQwLzB3RHYrN2FrYlpZRmlKQ2tKR0xJbFM0a1luMWpUc1NFClFBT28zM3NaZERDWXpzQXlwc1VxRHJOT2FzQmZ0QWxIOVRNNXhMTkNGaWdNbmZoeVY3ZFhvUEoyL3Bobjg2aHMKZUFLTFZ3S2dnM2VjMUF2b1hPWGxVN2JDMmxDZ0lBeUJ6dGNWVE5BN3IxeldpNjc3eHAreVM0NnRxeW1tTHY1MwpiUDhhMzNzQmRFZVg0MFZ3VGx0R0lUNE0wRXBoUHdOUTdtUXYvaERWamg0QXZTRVVlQXQ0UWhzTVY0SEJnZ25XCkk5d01Ndkl2QkQxaTdTK3BXck1jVG11ZTlmdXRtVUNGcGVnTExiUHhrWTBNMFpVaHlBekcxemEzaThKWi9oZjEKOTNvSmF2c1NQUHV2VWpKWFhPMXMrNDFvNkJNaUNpQS9GTDB0OXdJREFRQUJBb0lCQVFDTXpXYXVnS0J6bDdiOApvOC85L01tL204MWRmUEt2TnBkeGIyV0NiaXBBY2Q1eURBRjVJbVBGRDhPRnhVNkV6bzNSTUlRS0kvTEFSK1dXCkxYeUJNS1dNWHI3Z0hreGdkNjdiTjYzeFZqd0lScWxyVHVJcnI3SFpTMURPQjVCRHdWenc3MWRLK2JuTWx5M3MKWkZ4WHRxSVBDUWJuMURSeDZWMUVzRUVHSW9OeFZUM2xNa29QTndEcDh6WmdURHhIOUJYRE4rQlgxR0NiMFZGOQpBMXFPUkNESXRPa2t0THVoOWR1aDFNbzZ3SC8zWmZkRGpSZ3VGU1M0OFZqN3huY05CWUdTZE5GSkdyZ2w5blAxCkNEOC84NkFxQWxiMFJFS1VsM3pFbGdDUC9iTGVqMTNaT3dtMHd0dHFadmpzZmc1NXZWRWdGREg0ZE5wREJmNWEKMi91S3Z1V0JBb0dCQU1GektRbkhhVXlIc2s2Qmx5RUdZZGN3RXJhRVJVSm44Q1pKZXdDZUtlb2cwZWl2WXQvaQorOVJwWGwxSTUrY015N2hKS1pKN2FLNHFFRURVRUswSHZsNGNFaWl0Y24vZCtNS1RnMFFCS0xrYm16U0NHcXJwCjZuR3g3djZWNFlHNjBsdTNTbEoyd0ZCNmE3NXkyU3gwQmdqcUZibHRieTNNOGlUZHp2cEdIQkNSQW9HQkFPNHcKWU1SWUdrODAvVlBXTnMyUkZvQitsbHdmZnJETStCMDArK2NCVWFxbGJuUHhUQU9qTU9naXVqcEdMeFBWNVlVSAp1RExuaFRDTGNGVG4rU28wVUtUeUdURjZIK3gxSjVtSWdTekFFNkRIS2VRVFUxbHpzTUREalZrc09zVmlXbWp1CmszWVZpNFhjZVgvcDVkRWxHWk8xcXMrT0FRNVlsZ0d6N1BoUXFob0hBb0dBUU16VHBWdnY4TnZQcGE2Uk1sWFIKOW1RN0VIcDBQTTlXU1d6NXovWXJNaXMyUlV4aXdYNW1QdnZneVR5L3VjeTJmUSs4NWoyQ2pqeTIzeEJxV1p1cgpjQmpWR0YwcGFwMnZVM1pZVlRKU010ZUZnT3hJQkpLQW52OHNnSWt5VmVOL3pZc3pVVFpJSzIwbXBGQVNZV3FvCkR0cGkxbzlLMjd1NExSTkQzdUFYVEpFQ2dZRUFoT1IvQ08weStLQlMrdlNZclFiWExDZjBraitNT3U2UlBCSjAKdlVVeUlHaWVnSmZQVm5RMWREN3o4bEY0TUxQMWs4eGp6QnI2WjhSVWp6ckIvUGNsUzNJNzlpdnlKY2FUcW9qTApzWUVWTW00TWhGRDMvdithVFdLTnVZUUE0bUhtbVljS3hTWnVLdWlBN1lvOWkvd01FaXFZdTZhNkZodjh6Y1JxCllYejMrdjhDZ1lCZlU1SCtHN0pKN0VpQ0xIcVpEbnFTdGlyaFdYaTUxZjBvTk0velFESDA0Tm1nbFZMUFgzUWwKZkt4aXJiS3BRRUkvS3poc1RXSm1tSmFDYmJqeGtaRzN5M3QzYm1RNWZCWGxuV3d5c0xpblhJMHI1OEVHa3F6bwoyUTVna0YrRUtVQW9RRGR0UGN4RzJ4ZnA2RkFEYndQN0VwYkZhQVRjdkJ3TW83c2dRR01FcUE9PQotLS0tLUVORCBSU0EgUFJJVkFURSBLRVktLS0tLQo=
ubuntu@ip-172-31-16-69:~/.kube$ cd ..
ubuntu@ip-172-31-16-69:~$ 


```