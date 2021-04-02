# aws_identitystore_user

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
module "aws_identitystore_user" {
  source = "./modules/aws/d/aws_identitystore_user"

  # identity_store_id - (required) is a type of string
  identity_store_id = null
  # user_id - (optional) is a type of string
  user_id = null

  filter = [{
    attribute_path  = null
    attribute_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "identity_store_id" {
  description = "(required)"
  type        = string
}

variable "user_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      attribute_path  = string
      attribute_value = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "aws_identitystore_user" "this" {
  identity_store_id = var.identity_store_id
  user_id           = var.user_id

  dynamic "filter" {
    for_each = var.filter
    content {
      attribute_path  = filter.value["attribute_path"]
      attribute_value = filter.value["attribute_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_identitystore_user.this.id
}

output "user_id" {
  description = "returns a string"
  value       = data.aws_identitystore_user.this.user_id
}

output "user_name" {
  description = "returns a string"
  value       = data.aws_identitystore_user.this.user_name
}

output "this" {
  value = aws_identitystore_user.this
}
```

[top](#index)