# alicloud_cr_ee_repos

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
module "alicloud_cr_ee_repos" {
  source = "./modules/alicloud/d/alicloud_cr_ee_repos"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # namespace - (optional) is a type of string
  namespace = null
  # output_file - (optional) is a type of string
  output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_details" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_cr_ee_repos" "this" {
  # enable_details - (optional) is a type of bool
  enable_details = var.enable_details
  # ids - (optional) is a type of list of string
  ids = var.ids
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # name_regex - (optional) is a type of string
  name_regex = var.name_regex
  # namespace - (optional) is a type of string
  namespace = var.namespace
  # output_file - (optional) is a type of string
  output_file = var.output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_cr_ee_repos.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_cr_ee_repos.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_cr_ee_repos.this.names
}

output "repos" {
  description = "returns a list of object"
  value       = data.alicloud_cr_ee_repos.this.repos
}

output "this" {
  value = alicloud_cr_ee_repos.this
}
```

[top](#index)