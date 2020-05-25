# ECS with ALB example
Terraform v0.11.10

This example shows how to launch an ECS service fronted with Application Load Balancer.

The example uses latest CoreOS Stable AMIs.

To run, configure your AWS provider as described in https://www.terraform.io/docs/providers/aws/index.html

## Get up and running

Planning phase

```
terraform plan -auto-approve
```

Apply phase

```
terraform apply -auto-approve
Outputs:
asg_name = tf-test-asg
elb_hostname = tf-example-alb-ecs-190742905.us-west-2.elb.amazonaws.com
instance_security_group = sg-09273bfeb4b104e79
launch_configuration = terraform-20200525170551584400000001
```

Verify
```
brawser http://tf-example-alb-ecs-190742905.us-west-2.elb.amazonaws.com/
get Ghost UI

```

Once the stack is created, wait for a few minutes and test the stack by launching a browser with the ALB url.

## Destroy :boom:

```
terraform destroy -auto-approve

```
