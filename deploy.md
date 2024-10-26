```markdown
Create a deployment named my-deploy with the image nginx.
Scale my-deploy to 3 replicas.
Replace the image in my-deploy from nginx to nginx:alpine.
Scale down the replicas of my-deploy to 2.
Rollback to the previous version of my-deploy.
Delete the deployment, replicaset, and pod created by my-deploy.
```

```bash
k create deployment my-deploy --image=nginx
k scale deployment my-deploy --replicas=3
k set image deployment/my-deploy nginx=nginx:alpine
k scale deployment my-deploy --replicas=2 
k rollout undo deployment my-deploy
k delete deploy my-deploy
```


```bash

k create deployment my-deploy --image=nginx
  576  k get deploy
  577  k get pods
  578  k scale deployment my-deploy --replicas=3
  579  k get deploy
  580  k get rs
  581  k get po
  582  clear
  583  k set image deployment/my-deploy nginx=nginx:alpine 
  584  k get pods
  585  k describe pod my-deploy-bf798779c-gp5qr
  586  k describe pods my-deploy-bf798779c-gp5qr
  587  k describe pods my-deploy-d84dc5bf8-ntgqf
  588  clear
  589  k scale deployment my-deploy --replicas=2
  590  k get deploy
  591  k get rs
  592  k get pods
  593  k rollout undo deployment my-deploy
  594  k get pods
  595  clear
  596  k get pods
  597  k describe my-deploy-bf798779c-s9xz9
  598  k get pods
  599  k describe pod my-deploy-bf798779c-s9xz9
  600  clear
  601  k get deploy
  602  k delete deploy my-deploy
  603  k get deploy

```