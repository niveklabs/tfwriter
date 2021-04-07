# nsxt_policy_transport_zone

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_transport_zone" {
  source = "./modules/nsxt/d/nsxt_policy_transport_zone"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # is_default - (optional) is a type of bool
  is_default = null
  # site_path - (optional) is a type of string
  site_path = null
  # transport_type - (optional) is a type of string
  transport_type = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of this resource"
  type        = string
  default     = null
}

variable "is_default" {
  description = "(optional) - Indicates whether the transport zone is default"
  type        = bool
  default     = null
}

variable "site_path" {
  description = "(optional) - Path of the site this Transport Zone belongs to"
  type        = string
  default     = null
}

variable "transport_type" {
  description = "(optional) - Type of Transport Zone"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_transport_zone" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # is_default - (optional) is a type of bool
  is_default = var.is_default
  # site_path - (optional) is a type of string
  site_path = var.site_path
  # transport_type - (optional) is a type of string
  transport_type = var.transport_type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_transport_zone.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_transport_zone.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_transport_zone.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = data.nsxt_policy_transport_zone.this.is_default
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_transport_zone.this.path
}

output "transport_type" {
  description = "returns a string"
  value       = data.nsxt_policy_transport_zone.this.transport_type
}

output "this" {
  value = nsxt_policy_transport_zone.this
}
```

[top](#index)