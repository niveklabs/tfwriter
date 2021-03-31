# alicloud_ga_bandwidth_packages

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ga_bandwidth_packages" {
  source = "./modules/alicloud/d/alicloud_ga_bandwidth_packages"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
  # type - (optional) is a type of string
  type = null
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ga_bandwidth_packages" "this" {
  enable_details = var.enable_details
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
  status         = var.status
  type           = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.alicloud_ga_bandwidth_packages.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ga_bandwidth_packages.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ga_bandwidth_packages.this.names
}

output "packages" {
  description = "returns a list of object"
  value       = data.alicloud_ga_bandwidth_packages.this.packages
}

output "this" {
  value = alicloud_ga_bandwidth_packages.this
}
```

[top](#index)