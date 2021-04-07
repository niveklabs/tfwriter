# scaleway_instance_server

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_server" {
  source = "./modules/scaleway/r/scaleway_instance_server"

  # additional_volume_ids - (optional) is a type of list of string
  additional_volume_ids = []
  # boot_type - (optional) is a type of string
  boot_type = null
  # bootscript_id - (optional) is a type of string
  bootscript_id = null
  # cloud_init - (optional) is a type of string
  cloud_init = null
  # enable_dynamic_ip - (optional) is a type of bool
  enable_dynamic_ip = null
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = null
  # image - (required) is a type of string
  image = null
  # ip_id - (optional) is a type of string
  ip_id = null
  # name - (optional) is a type of string
  name = null
  # placement_group_id - (optional) is a type of string
  placement_group_id = null
  # project_id - (optional) is a type of string
  project_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # state - (optional) is a type of string
  state = null
  # tags - (optional) is a type of list of string
  tags = []
  # type - (required) is a type of string
  type = null
  # user_data - (optional) is a type of map of string
  user_data = {}
  # zone - (optional) is a type of string
  zone = null

  root_volume = [{
    delete_on_termination = null
    size_in_gb            = null
    volume_id             = null
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "additional_volume_ids" {
  description = "(optional) - The additional volumes attached to the server"
  type        = list(string)
  default     = null
}

variable "boot_type" {
  description = "(optional) - The boot type of the server"
  type        = string
  default     = null
}

variable "bootscript_id" {
  description = "(optional) - ID of the target bootscript (set boot_type to bootscript)"
  type        = string
  default     = null
}

variable "cloud_init" {
  description = "(optional) - The cloud init script associated with this server"
  type        = string
  default     = null
}

variable "enable_dynamic_ip" {
  description = "(optional) - Enable dynamic IP on the server"
  type        = bool
  default     = null
}

variable "enable_ipv6" {
  description = "(optional) - Determines if IPv6 is enabled for the server"
  type        = bool
  default     = null
}

variable "image" {
  description = "(required) - The UUID or the label of the base image used by the server"
  type        = string
}

variable "ip_id" {
  description = "(optional) - The ID of the reserved IP for the server"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the server"
  type        = string
  default     = null
}

variable "placement_group_id" {
  description = "(optional) - The placement group the server is attached to"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional) - The security group the server is attached to"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional) - The state of the server should be: started, stopped, standby"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags associated with the server"
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(required) - The instance type of the server"
  type        = string
}

variable "user_data" {
  description = "(optional) - The user data associated with the server"
  type        = map(string)
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "root_volume" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_on_termination = bool
      size_in_gb            = number
      volume_id             = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_instance_server" "this" {
  # additional_volume_ids - (optional) is a type of list of string
  additional_volume_ids = var.additional_volume_ids
  # boot_type - (optional) is a type of string
  boot_type = var.boot_type
  # bootscript_id - (optional) is a type of string
  bootscript_id = var.bootscript_id
  # cloud_init - (optional) is a type of string
  cloud_init = var.cloud_init
  # enable_dynamic_ip - (optional) is a type of bool
  enable_dynamic_ip = var.enable_dynamic_ip
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = var.enable_ipv6
  # image - (required) is a type of string
  image = var.image
  # ip_id - (optional) is a type of string
  ip_id = var.ip_id
  # name - (optional) is a type of string
  name = var.name
  # placement_group_id - (optional) is a type of string
  placement_group_id = var.placement_group_id
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # state - (optional) is a type of string
  state = var.state
  # tags - (optional) is a type of list of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type
  # user_data - (optional) is a type of map of string
  user_data = var.user_data
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "root_volume" {
    for_each = var.root_volume
    content {
      # delete_on_termination - (optional) is a type of bool
      delete_on_termination = root_volume.value["delete_on_termination"]
      # size_in_gb - (optional) is a type of number
      size_in_gb = root_volume.value["size_in_gb"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bootscript_id" {
  description = "returns a string"
  value       = scaleway_instance_server.this.bootscript_id
}

output "id" {
  description = "returns a string"
  value       = scaleway_instance_server.this.id
}

output "ipv6_address" {
  description = "returns a string"
  value       = scaleway_instance_server.this.ipv6_address
}

output "ipv6_gateway" {
  description = "returns a string"
  value       = scaleway_instance_server.this.ipv6_gateway
}

output "ipv6_prefix_length" {
  description = "returns a number"
  value       = scaleway_instance_server.this.ipv6_prefix_length
}

output "name" {
  description = "returns a string"
  value       = scaleway_instance_server.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_instance_server.this.organization_id
}

output "placement_group_policy_respected" {
  description = "returns a bool"
  value       = scaleway_instance_server.this.placement_group_policy_respected
}

output "private_ip" {
  description = "returns a string"
  value       = scaleway_instance_server.this.private_ip
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_instance_server.this.project_id
}

output "public_ip" {
  description = "returns a string"
  value       = scaleway_instance_server.this.public_ip
}

output "security_group_id" {
  description = "returns a string"
  value       = scaleway_instance_server.this.security_group_id
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_server.this.zone
}

output "this" {
  value = scaleway_instance_server.this
}
```

[top](#index)