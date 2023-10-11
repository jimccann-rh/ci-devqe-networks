
```
terraform init
terraform plan -var-file=./secrets/terraform.tfvars -var-file=./terraform.tfvars
terraform apply -var-file=./secrets/terraform.tfvars -var-file=./terraform.tfvars
```


```
terraform state list | grep vlan | xargs -I {} terraform state show {} | grep vlan_number | awk -F\= '{print $2}' | tr -d '[:blank:]'
```



ibmcloud sl vlan list|grep ci_vlan | cut -d ' ' -f 1| xargs -I {} ibmcloud sl vlan detail {}
ibmcloud sl vlan list|grep ci_vlan | cut -d ' ' -f 1| xargs -I {} ibmcloud sl vlan detail --no-vs --no-hardware --output json {}
