# aws_redshift_security_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_redshift_security_group" {
  source = "./modules/aws/r/aws_redshift_security_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  ingress = [{
    cidr                    = null
    security_group_name     = null
    security_group_owner_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ingress" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      cidr                    = string
      security_group_name     = string
      security_group_owner_id = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_redshift_security_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name

  dynamic "ingress" {
    for_each = var.ingress
    content {
      # cidr - (optional) is a type of string
      cidr = ingress.value["cidr"]
      # security_group_name - (optional) is a type of string
      security_group_name = ingress.value["security_group_name"]
      # security_group_owner_id - (optional) is a type of string
      security_group_owner_id = ingress.value["security_group_owner_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_redshift_security_group.this.id
}

output "this" {
  value = aws_redshift_security_group.this
}
```

[top](#index)