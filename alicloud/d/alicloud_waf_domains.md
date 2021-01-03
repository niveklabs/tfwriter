# alicloud_waf_domains

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_waf_domains" {
  source = "./modules/alicloud/d/alicloud_waf_domains"

  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # instance_id - (required) is a type of string
  instance_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
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

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_waf_domains" "this" {
  enable_details    = var.enable_details
  ids               = var.ids
  instance_id       = var.instance_id
  name_regex        = var.name_regex
  output_file       = var.output_file
  resource_group_id = var.resource_group_id
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a list of object"
  value       = data.alicloud_waf_domains.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_waf_domains.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_waf_domains.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_waf_domains.this.names
}

output "this" {
  value = alicloud_waf_domains.this
}
```

[top](#index)