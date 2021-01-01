# aws_storagegateway_cache

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_storagegateway_cache" {
  source = "./modules/aws/r/aws_storagegateway_cache"

  # disk_id - (required) is a type of string
  disk_id = null
  # gateway_arn - (required) is a type of string
  gateway_arn = null
}
```

[top](#index)

### Variables

```hcl
variable "disk_id" {
  description = "(required)"
  type        = string
}

variable "gateway_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_storagegateway_cache" "this" {
  disk_id     = var.disk_id
  gateway_arn = var.gateway_arn
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_storagegateway_cache.this.id
}

output "this" {
  value = aws_storagegateway_cache.this
}
```

[top](#index)