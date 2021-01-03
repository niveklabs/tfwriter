# alicloud_ecs_dedicated_hosts

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
module "alicloud_ecs_dedicated_hosts" {
  source = "./modules/alicloud/d/alicloud_ecs_dedicated_hosts"

  # dedicated_host_id - (optional) is a type of string
  dedicated_host_id = null
  # dedicated_host_name - (optional) is a type of string
  dedicated_host_name = null
  # dedicated_host_type - (optional) is a type of string
  dedicated_host_type = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dedicated_host_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dedicated_host_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dedicated_host_type" {
  description = "(optional)"
  type        = string
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_ecs_dedicated_hosts" "this" {
  dedicated_host_id   = var.dedicated_host_id
  dedicated_host_name = var.dedicated_host_name
  dedicated_host_type = var.dedicated_host_type
  ids                 = var.ids
  name_regex          = var.name_regex
  output_file         = var.output_file
  resource_group_id   = var.resource_group_id
  status              = var.status
  tags                = var.tags
  zone_id             = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "hosts" {
  description = "returns a list of object"
  value       = data.alicloud_ecs_dedicated_hosts.this.hosts
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_ecs_dedicated_hosts.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_dedicated_hosts.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_ecs_dedicated_hosts.this.names
}

output "this" {
  value = alicloud_ecs_dedicated_hosts.this
}
```

[top](#index)