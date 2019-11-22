## Making a secret for the duffy api key

$ oc create secret generic duffy.key --from-file=duffy.key=duffy.key

## Making a secret for the duffy ssh key

$ oc create secret generic duffy-ssh-key --from-file=ssh-privatekey=id_rsa --type=kubernetes.io/ssh-auth
