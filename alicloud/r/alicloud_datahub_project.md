# alicloud_datahub_project

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
module "alicloud_datahub_project" {
  source = "./modules/alicloud/r/alicloud_datahub_project"

  # comment - (optional) is a type of string
  comment = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
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
resource "alicloud_datahub_project" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = alicloud_datahub_project.this.create_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_datahub_project.this.id
}

output "last_modify_time" {
  description = "returns a string"
  value       = alicloud_datahub_project.this.last_modify_time
}

output "this" {
  value = alicloud_datahub_project.this
}
```

[top](#index)