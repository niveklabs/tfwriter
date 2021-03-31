# exoscale_compute

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_compute" {
  source = "./modules/exoscale/r/exoscale_compute"

  # affinity_group_ids - (optional) is a type of set of string
  affinity_group_ids = []
  # affinity_groups - (optional) is a type of set of string
  affinity_groups = []
  # disk_size - (required) is a type of number
  disk_size = null
  # display_name - (optional) is a type of string
  display_name = null
  # hostname - (optional) is a type of string
  hostname = null
  # ip4 - (optional) is a type of bool
  ip4 = null
  # ip6 - (optional) is a type of bool
  ip6 = null
  # key_pair - (optional) is a type of string
  key_pair = null
  # keyboard - (optional) is a type of string
  keyboard = null
  # reverse_dns - (optional) is a type of string
  reverse_dns = null
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # size - (optional) is a type of string
  size = null
  # state - (optional) is a type of string
  state = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template - (optional) is a type of string
  template = null
  # template_id - (optional) is a type of string
  template_id = null
  # user_data - (optional) is a type of string
  user_data = null
  # zone - (required) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "affinity_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "affinity_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "disk_size" {
  description = "(required)"
  type        = number
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip4" {
  description = "(optional) - Request an IPv4 address on the default NIC"
  type        = bool
  default     = null
}

variable "ip6" {
  description = "(optional) - Request an IPv6 address on the default NIC"
  type        = bool
  default     = null
}

variable "key_pair" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "keyboard" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reverse_dns" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "security_groups" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Map of tags (key: value)"
  type        = map(string)
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional) - cloud-init configuration"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "exoscale_compute" "this" {
  affinity_group_ids = var.affinity_group_ids
  affinity_groups    = var.affinity_groups
  disk_size          = var.disk_size
  display_name       = var.display_name
  hostname           = var.hostname
  ip4                = var.ip4
  ip6                = var.ip6
  key_pair           = var.key_pair
  keyboard           = var.keyboard
  reverse_dns        = var.reverse_dns
  security_group_ids = var.security_group_ids
  security_groups    = var.security_groups
  size               = var.size
  state              = var.state
  tags               = var.tags
  template           = var.template
  template_id        = var.template_id
  user_data          = var.user_data
  zone               = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "affinity_group_ids" {
  description = "returns a set of string"
  value       = exoscale_compute.this.affinity_group_ids
}

output "affinity_groups" {
  description = "returns a set of string"
  value       = exoscale_compute.this.affinity_groups
}

output "display_name" {
  description = "returns a string"
  value       = exoscale_compute.this.display_name
}

output "gateway" {
  description = "returns a string"
  value       = exoscale_compute.this.gateway
}

output "hostname" {
  description = "returns a string"
  value       = exoscale_compute.this.hostname
}

output "id" {
  description = "returns a string"
  value       = exoscale_compute.this.id
}

output "ip6_address" {
  description = "returns a string"
  value       = exoscale_compute.this.ip6_address
}

output "ip6_cidr" {
  description = "returns a string"
  value       = exoscale_compute.this.ip6_cidr
}

output "ip_address" {
  description = "returns a string"
  value       = exoscale_compute.this.ip_address
}

output "name" {
  description = "returns a string"
  value       = exoscale_compute.this.name
}

output "password" {
  description = "returns a string"
  value       = exoscale_compute.this.password
  sensitive   = true
}

output "security_group_ids" {
  description = "returns a set of string"
  value       = exoscale_compute.this.security_group_ids
}

output "security_groups" {
  description = "returns a set of string"
  value       = exoscale_compute.this.security_groups
}

output "state" {
  description = "returns a string"
  value       = exoscale_compute.this.state
}

output "tags" {
  description = "returns a map of string"
  value       = exoscale_compute.this.tags
}

output "template" {
  description = "returns a string"
  value       = exoscale_compute.this.template
}

output "template_id" {
  description = "returns a string"
  value       = exoscale_compute.this.template_id
}

output "user_data_base64" {
  description = "returns a bool"
  value       = exoscale_compute.this.user_data_base64
}

output "username" {
  description = "returns a string"
  value       = exoscale_compute.this.username
}

output "this" {
  value = exoscale_compute.this
}
```

[top](#index)