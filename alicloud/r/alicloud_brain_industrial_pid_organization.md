# alicloud_brain_industrial_pid_organization

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_brain_industrial_pid_organization" {
  source = "./modules/alicloud/r/alicloud_brain_industrial_pid_organization"

  # parent_pid_organization_id - (optional) is a type of string
  parent_pid_organization_id = null
  # pid_organization_name - (required) is a type of string
  pid_organization_name = null
}
```

[top](#index)

### Variables

```terraform
variable "parent_pid_organization_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pid_organization_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_brain_industrial_pid_organization" "this" {
  parent_pid_organization_id = var.parent_pid_organization_id
  pid_organization_name      = var.pid_organization_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_brain_industrial_pid_organization.this.id
}

output "this" {
  value = alicloud_brain_industrial_pid_organization.this
}
```

[top](#index)