To install karpenter edit the configmap **aws-auth** present in the namespace **kube-system**.

![image](https://github.com/user-attachments/assets/f951d3ad-dfbd-41e4-a1e9-29f4ab1e42c2)
![image](https://github.com/user-attachments/assets/ff1cfc81-48c2-47ef-aee8-06cd2a713a84)

I had installed Karpenter Controller using the helm with the help of the command as shown in the scrrenshot attcahed below.

```
helm upgrade --install karpenter oci://public.ecr.aws/karpenter/karpenter --version "1.3.2" --namespace "karpenter" --create-namespace --set "settings.clusterName=eks-demo-cluster-dev" --set "serviceAccount.annotations.eks\.amazonaws\.com/role-arn=arn:aws:iam::02XXXXXXXXX6:role/karpenter-controller-role" --set controller.resources.requests.cpu=1 --set controller.resources.requests.memory=1Gi --set controller.resources.limits.cpu=1 --set controller.resources.limits.memory=1Gi
```
![image](https://github.com/user-attachments/assets/07b52851-4d2c-4782-8968-416ead24d483)

