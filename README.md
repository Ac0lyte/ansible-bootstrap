### ansible-bootstrap

This bootstraps an AWS account for use by Terraform.

# Why?

I prefer to use Terraform to manage my AWS resources, BUT it needs valid credentials, a place to store the state file (I like S3), yada, yada.

# How?

The following will create a 'builders' group and a 'terraform' user in that group. It will give god level permissions to that group.

You may wish to change what your terraform user has access to (I would recommend it). To do this edit *policies/builders_god_policy.json* file.


```
export AWS_ACCESS_KEY_ID=*your-aws-access-key*
export AWS_SECRET_ACCESS_KEY=*your-aws-secret-key*

ansible-playbook bootstrap.yaml --extra-vars "account_id=123456789012"
```

The playbook should spit out an access key id and secret.  *KEEP THESE SAFE*. 

Save these, you will not see them again.

*DO NOT*
- Send then via email to anyone
- Check them into a git repo
- Post them in a chat room
- Anythn else really stupid

