# aws_media_store_container_policy

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_media_store_container_policy" {
  source = "./modules/aws/r/aws_media_store_container_policy"

  # container_name - (required) is a type of string
  container_name = null
  # policy - (required) is a type of string
  policy = null
}
```

[top](#index)

### Variables

```terraform
variable "container_name" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_media_store_container_policy" "this" {
  container_name = var.container_name
  policy         = var.policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_media_store_container_policy.this.id
}

output "this" {
  value = aws_media_store_container_policy.this
}
```

[top](#index)