# aviatrix_periodic_ping

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_periodic_ping" {
  source = "./modules/aviatrix/r/aviatrix_periodic_ping"

  # gw_name - (required) is a type of string
  gw_name = null
  # interval - (required) is a type of number
  interval = null
  # ip_address - (required) is a type of string
  ip_address = null
}
```

[top](#index)

### Variables

```terraform
variable "gw_name" {
  description = "(required) - Name of gateway."
  type        = string
}

variable "interval" {
  description = "(required) - Interval between pings in seconds."
  type        = number
}

variable "ip_address" {
  description = "(required) - IP Address to ping."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_periodic_ping" "this" {
  gw_name    = var.gw_name
  interval   = var.interval
  ip_address = var.ip_address
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_periodic_ping.this.id
}

output "this" {
  value = aviatrix_periodic_ping.this
}
```

[top](#index)