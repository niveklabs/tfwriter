# bigip_traffic_selector

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
module "bigip_traffic_selector" {
  source = "./modules/bigip/r/bigip_traffic_selector"

  # description - (optional) is a type of string
  description = null
  # destination_address - (required) is a type of string
  destination_address = null
  # destination_port - (optional) is a type of number
  destination_port = null
  # direction - (optional) is a type of string
  direction = null
  # ip_protocol - (optional) is a type of number
  ip_protocol = null
  # ipsec_policy - (optional) is a type of string
  ipsec_policy = null
  # name - (required) is a type of string
  name = null
  # order - (optional) is a type of number
  order = null
  # source_address - (required) is a type of string
  source_address = null
  # source_port - (optional) is a type of number
  source_port = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the traffic selector."
  type        = string
  default     = null
}

variable "destination_address" {
  description = "(required) - Specifies the host or network IP address to which the application traffic is destined.When creating a new traffic selector, this parameter is required"
  type        = string
}

variable "destination_port" {
  description = "(optional) - Specifies the IP port used by the application. The default value is All Ports"
  type        = number
  default     = null
}

variable "direction" {
  description = "(optional) - Specifies whether the traffic selector applies to inbound or outbound traffic, or both. The default value is Both."
  type        = string
  default     = null
}

variable "ip_protocol" {
  description = "(optional) - Specifies the network protocol to use for this traffic. The default value is All Protocols (255)"
  type        = number
  default     = null
}

variable "ipsec_policy" {
  description = "(optional) - Specifies the IPsec policy that tells the BIG-IP system how to handle the packets.When creating a new traffic selector, if this parameter is not specified, the default is default-ipsec-policy."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Specifies the name of the traffic selector"
  type        = string
}

variable "order" {
  description = "(optional) - Specifies the order in which traffic is matched, if traffic can be matched to multiple traffic selectors.Traffic is matched to the traffic selector with the highest priority (lowest order number).When creating a new traffic selector, if this parameter is not specified, the default is last."
  type        = number
  default     = null
}

variable "source_address" {
  description = "(required) - Specifies the host or network IP address from which the application traffic originates.When creating a new traffic selector, this parameter is required."
  type        = string
}

variable "source_port" {
  description = "(optional) - Specifies the IP port used by the application. The default value is All Ports"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_traffic_selector" "this" {
  description         = var.description
  destination_address = var.destination_address
  destination_port    = var.destination_port
  direction           = var.direction
  ip_protocol         = var.ip_protocol
  ipsec_policy        = var.ipsec_policy
  name                = var.name
  order               = var.order
  source_address      = var.source_address
  source_port         = var.source_port
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = bigip_traffic_selector.this.description
}

output "destination_port" {
  description = "returns a number"
  value       = bigip_traffic_selector.this.destination_port
}

output "direction" {
  description = "returns a string"
  value       = bigip_traffic_selector.this.direction
}

output "id" {
  description = "returns a string"
  value       = bigip_traffic_selector.this.id
}

output "ip_protocol" {
  description = "returns a number"
  value       = bigip_traffic_selector.this.ip_protocol
}

output "ipsec_policy" {
  description = "returns a string"
  value       = bigip_traffic_selector.this.ipsec_policy
}

output "order" {
  description = "returns a number"
  value       = bigip_traffic_selector.this.order
}

output "source_port" {
  description = "returns a number"
  value       = bigip_traffic_selector.this.source_port
}

output "this" {
  value = bigip_traffic_selector.this
}
```

[top](#index)