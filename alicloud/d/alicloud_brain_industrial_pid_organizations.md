# alicloud_brain_industrial_pid_organizations

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_brain_industrial_pid_organizations" {
  source = "./modules/alicloud/d/alicloud_brain_industrial_pid_organizations"

  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # parent_organization_id - (optional) is a type of string
  parent_organization_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_organization_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_brain_industrial_pid_organizations" "this" {
  # ids - (optional) is a type of list of string
  ids = var.ids
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # output_file - (optional) is a type of string
  output_file = var.output_file
  # parent_organization_id - (optional) is a type of string
  parent_organization_id = var.parent_organization_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_brain_industrial_pid_organizations.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_brain_industrial_pid_organizations.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_brain_industrial_pid_organizations.this.names
}

output "organizations" {
  description = "returns a list of object"
  value       = data.alicloud_brain_industrial_pid_organizations.this.organizations
}

output "this" {
  value = alicloud_brain_industrial_pid_organizations.this
}
```

[top](#index)