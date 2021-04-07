# bigip_net_tunnel

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_net_tunnel" {
  source = "./modules/bigip/r/bigip_net_tunnel"

  # app_service - (optional) is a type of string
  app_service = null
  # auto_last_hop - (optional) is a type of string
  auto_last_hop = null
  # description - (optional) is a type of string
  description = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # key - (optional) is a type of number
  key = null
  # local_address - (required) is a type of string
  local_address = null
  # mode - (optional) is a type of string
  mode = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
  # profile - (required) is a type of string
  profile = null
  # remote_address - (optional) is a type of string
  remote_address = null
  # secondary_address - (optional) is a type of string
  secondary_address = null
  # tos - (optional) is a type of string
  tos = null
  # traffic_group - (optional) is a type of string
  traffic_group = null
  # transparent - (optional) is a type of string
  transparent = null
  # use_pmtu - (optional) is a type of string
  use_pmtu = null
}
```

[top](#index)

### Variables

```terraform
variable "app_service" {
  description = "(optional) - The application service that the object belongs to"
  type        = string
  default     = null
}

variable "auto_last_hop" {
  description = "(optional) - Specifies whether auto lasthop is enabled or not"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - User defined description"
  type        = string
  default     = null
}

variable "idle_timeout" {
  description = "(optional) - Specifies an idle timeout for wildcard tunnels in seconds"
  type        = number
  default     = null
}

variable "key" {
  description = "(optional) - The key field may represent different values depending on the type of the tunnel"
  type        = number
  default     = null
}

variable "local_address" {
  description = "(required) - Specifies a local IP address. This option is required"
  type        = string
}

variable "mode" {
  description = "(optional) - Specifies how the tunnel carries traffic"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - Specifies the maximum transmission unit (MTU) of the tunnel"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the TUNNEL"
  type        = string
}

variable "partition" {
  description = "(optional) - Displays the admin-partition within which this component resides"
  type        = string
  default     = null
}

variable "profile" {
  description = "(required) - Specifies the profile that you want to associate with the tunnel"
  type        = string
}

variable "remote_address" {
  description = "(optional) - Specifies a remote IP address"
  type        = string
  default     = null
}

variable "secondary_address" {
  description = "(optional) - Specifies a secondary non-floating IP address when the local-address is set to a floating address"
  type        = string
  default     = null
}

variable "tos" {
  description = "(optional) - Specifies a value for insertion into the Type of Service (ToS) octet within the IP header of the encapsulating header of transmitted packets"
  type        = string
  default     = null
}

variable "traffic_group" {
  description = "(optional) - Specifies a traffic-group for use with the tunnel"
  type        = string
  default     = null
}

variable "transparent" {
  description = "(optional) - Enables or disables the tunnel to be transparent"
  type        = string
  default     = null
}

variable "use_pmtu" {
  description = "(optional) - Enables or disables the tunnel to use the PMTU (Path MTU) information provided by ICMP NeedFrag error messages"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_net_tunnel" "this" {
  # app_service - (optional) is a type of string
  app_service = var.app_service
  # auto_last_hop - (optional) is a type of string
  auto_last_hop = var.auto_last_hop
  # description - (optional) is a type of string
  description = var.description
  # idle_timeout - (optional) is a type of number
  idle_timeout = var.idle_timeout
  # key - (optional) is a type of number
  key = var.key
  # local_address - (required) is a type of string
  local_address = var.local_address
  # mode - (optional) is a type of string
  mode = var.mode
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # partition - (optional) is a type of string
  partition = var.partition
  # profile - (required) is a type of string
  profile = var.profile
  # remote_address - (optional) is a type of string
  remote_address = var.remote_address
  # secondary_address - (optional) is a type of string
  secondary_address = var.secondary_address
  # tos - (optional) is a type of string
  tos = var.tos
  # traffic_group - (optional) is a type of string
  traffic_group = var.traffic_group
  # transparent - (optional) is a type of string
  transparent = var.transparent
  # use_pmtu - (optional) is a type of string
  use_pmtu = var.use_pmtu
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_net_tunnel.this.id
}

output "this" {
  value = bigip_net_tunnel.this
}
```

[top](#index)