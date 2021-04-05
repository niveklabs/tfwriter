# panos_panorama_bgp_peer_group

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_bgp_peer_group" {
  source = "./modules/panos/r/panos_panorama_bgp_peer_group"

  # aggregated_confed_as_path - (optional) is a type of bool
  aggregated_confed_as_path = null
  # enable - (optional) is a type of bool
  enable = null
  # export_next_hop - (optional) is a type of string
  export_next_hop = null
  # import_next_hop - (optional) is a type of string
  import_next_hop = null
  # name - (required) is a type of string
  name = null
  # remove_private_as - (optional) is a type of bool
  remove_private_as = null
  # soft_reset_with_stored_info - (optional) is a type of bool
  soft_reset_with_stored_info = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # type - (optional) is a type of string
  type = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "aggregated_confed_as_path" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "export_next_hop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "import_next_hop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "remove_private_as" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "soft_reset_with_stored_info" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_bgp_peer_group" "this" {
  aggregated_confed_as_path   = var.aggregated_confed_as_path
  enable                      = var.enable
  export_next_hop             = var.export_next_hop
  import_next_hop             = var.import_next_hop
  name                        = var.name
  remove_private_as           = var.remove_private_as
  soft_reset_with_stored_info = var.soft_reset_with_stored_info
  template                    = var.template
  template_stack              = var.template_stack
  type                        = var.type
  virtual_router              = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_bgp_peer_group.this.id
}

output "this" {
  value = panos_panorama_bgp_peer_group.this
}
```

[top](#index)