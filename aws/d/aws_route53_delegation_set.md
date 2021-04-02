# aws_route53_delegation_set

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_route53_delegation_set" {
  source = "./modules/aws/d/aws_route53_delegation_set"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "aws_route53_delegation_set" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "caller_reference" {
  description = "returns a string"
  value       = data.aws_route53_delegation_set.this.caller_reference
}

output "id" {
  description = "returns a string"
  value       = data.aws_route53_delegation_set.this.id
}

output "name_servers" {
  description = "returns a list of string"
  value       = data.aws_route53_delegation_set.this.name_servers
}

output "this" {
  value = aws_route53_delegation_set.this
}
```

[top](#index)