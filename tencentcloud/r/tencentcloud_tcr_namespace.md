# tencentcloud_tcr_namespace

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_tcr_namespace" {
  source = "./modules/tencentcloud/r/tencentcloud_tcr_namespace"

  # instance_id - (required) is a type of string
  instance_id = null
  # is_public - (optional) is a type of bool
  is_public = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - ID of the TCR instance."
  type        = string
}

variable "is_public" {
  description = "(optional) - Indicate that the namespace is public or not. Default is `false`."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the TCR namespace. Valid length is [2~30]. It can only contain lowercase letters, numbers and separators (`.`, `_`, `-`), and cannot start, end or continue with separators."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_tcr_namespace" "this" {
  instance_id = var.instance_id
  is_public   = var.is_public
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_tcr_namespace.this.id
}

output "this" {
  value = tencentcloud_tcr_namespace.this
}
```

[top](#index)