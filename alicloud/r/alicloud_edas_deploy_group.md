# alicloud_edas_deploy_group

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
module "alicloud_edas_deploy_group" {
  source = "./modules/alicloud/r/alicloud_edas_deploy_group"

  # app_id - (required) is a type of string
  app_id = null
  # group_name - (required) is a type of string
  group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "group_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_edas_deploy_group" "this" {
  app_id     = var.app_id
  group_name = var.group_name
}
```

[top](#index)

### Outputs

```terraform
output "group_type" {
  description = "returns a number"
  value       = alicloud_edas_deploy_group.this.group_type
}

output "id" {
  description = "returns a string"
  value       = alicloud_edas_deploy_group.this.id
}

output "this" {
  value = alicloud_edas_deploy_group.this
}
```

[top](#index)