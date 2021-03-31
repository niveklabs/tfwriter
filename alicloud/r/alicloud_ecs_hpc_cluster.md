# alicloud_ecs_hpc_cluster

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ecs_hpc_cluster" {
  source = "./modules/alicloud/r/alicloud_ecs_hpc_cluster"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
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
```

[top](#index)

### Resource

```terraform
resource "alicloud_ecs_hpc_cluster" "this" {
  description = var.description
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ecs_hpc_cluster.this.id
}

output "this" {
  value = alicloud_ecs_hpc_cluster.this
}
```

[top](#index)