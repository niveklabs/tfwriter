# alicloud_dcdn_domains

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
module "alicloud_dcdn_domains" {
  source = "./modules/alicloud/d/alicloud_dcdn_domains"

  # change_end_time - (optional) is a type of string
  change_end_time = null
  # change_start_time - (optional) is a type of string
  change_start_time = null
  # check_domain_show - (optional) is a type of bool
  check_domain_show = null
  # domain_search_type - (optional) is a type of string
  domain_search_type = null
  # enable_details - (optional) is a type of bool
  enable_details = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_token - (optional) is a type of string
  security_token = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "change_end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "change_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "check_domain_show" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "domain_search_type" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_dcdn_domains" "this" {
  change_end_time    = var.change_end_time
  change_start_time  = var.change_start_time
  check_domain_show  = var.check_domain_show
  domain_search_type = var.domain_search_type
  enable_details     = var.enable_details
  ids                = var.ids
  name_regex         = var.name_regex
  output_file        = var.output_file
  resource_group_id  = var.resource_group_id
  security_token     = var.security_token
  status             = var.status
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a list of object"
  value       = data.alicloud_dcdn_domains.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_dcdn_domains.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_dcdn_domains.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_dcdn_domains.this.names
}

output "this" {
  value = alicloud_dcdn_domains.this
}
```

[top](#index)