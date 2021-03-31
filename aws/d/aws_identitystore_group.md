# aws_identitystore_group

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_identitystore_group" {
  source = "./modules/aws/d/aws_identitystore_group"

  # group_id - (optional) is a type of string
  group_id = null
  # identity_store_id - (required) is a type of string
  identity_store_id = null

  filter = [{
    attribute_path  = null
    attribute_value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_store_id" {
  description = "(required)"
  type        = string
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
data "aws_identitystore_group" "this" {
  group_id          = var.group_id
  identity_store_id = var.identity_store_id

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
output "display_name" {
  description = "returns a string"
  value       = data.aws_identitystore_group.this.display_name
}

output "group_id" {
  description = "returns a string"
  value       = data.aws_identitystore_group.this.group_id
}

output "id" {
  description = "returns a string"
  value       = data.aws_identitystore_group.this.id
}

output "this" {
  value = aws_identitystore_group.this
}
```

[top](#index)